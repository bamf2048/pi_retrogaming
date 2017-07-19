# Self-hosted Dropbox on your Retropie Using Syncthing

----

TLDR version of this: https://www.htpcguides.com/install-syncthing-raspberry-pi-bittorrent-sync-alternative/

----

I needed a way to sync my games across a few Retropies. Obviously not wanting to use 
Dropbox, Google Drive, Onedrive for privacy reasons. **Syncthing** is decentralized 
and fits my needs. Install, tweak settings, and via web browser, choose folders and 
machines to sync with.

Download the key:

`wget -O - https://syncthing.net/release-key.txt | sudo apt-key add -`

Add the repository:

`echo "deb http://apt.syncthing.net/ syncthing release" | sudo tee -a /etc/apt/sources.list.d/syncthing-release.list`

Install:

```
sudo apt-get update
sudo apt-get install syncthing -y
```

Run it once:

`syncthing`

Once it settles down stop it with `ctrl-c`.

Edit Syncthing settings:

`nano /home/pi/.config/syncthing/config.xml`

Add this (replace with your ip but leave the :port):

```
<gui enabled="true" tls="false">
 <address>0.0.0.0:8384</address>
 <apikey>VbsKT2fCELYldTI74Tk4BKCbJP8Frlij</apikey>
</gui>
```

You'll be able to access the gui by visiting http://retropie.local:8384 or via it's ip address:8384.

Autostart on boot:

`sudo nano /etc/init.d/syncthing`

Add this:

```
#!/bin/sh
### BEGIN INIT INFO
# Provides:          Syncthing
# Required-Start:    $local_fs $remote_fs $network
# Required-Stop:     $local_fs $remote_fs $network
# Default-Start:     2 3 4 5
# Default-Stop:      0 1 6
# Short-Description: Syncthing
# Description:       Syncthing is for backups
### END INIT INFO
 
 
# Documentation available at
# http://refspecs.linuxfoundation.org/LSB_3.1.0/LSB-Core-generic/LSB-Core-generic/iniscrptfunc.html
# Debian provides some extra functions though
. /lib/lsb/init-functions
 
 
DAEMON_NAME="syncthing"
DAEMON_USER=pi
DAEMON_PATH="/usr/bin/syncthing"
DAEMON_OPTS=""
DAEMON_PWD="${PWD}"
DAEMON_DESC=$(get_lsb_header_val $0 "Short-Description")
DAEMON_PID="/var/run/${DAEMON_NAME}.pid"
DAEMON_NICE=0
DAEMON_LOG='/var/log/syncthing'
 
[ -r "/etc/default/${DAEMON_NAME}" ] && . "/etc/default/${DAEMON_NAME}"
 
do_start() {
  local result
 
	pidofproc -p "${DAEMON_PID}" "${DAEMON_PATH}" > /dev/null
	if [ $? -eq 0 ]; then
		log_warning_msg "${DAEMON_NAME} is already started"
		result=0
	else
		log_daemon_msg "Starting ${DAEMON_DESC}" "${DAEMON_NAME}"
		touch "${DAEMON_LOG}"
		chown $DAEMON_USER "${DAEMON_LOG}"
		chmod u+rw "${DAEMON_LOG}"
		if [ -z "${DAEMON_USER}" ]; then
			start-stop-daemon --start --quiet --oknodo --background \
				--nicelevel $DAEMON_NICE \
				--chdir "${DAEMON_PWD}" \
				--pidfile "${DAEMON_PID}" --make-pidfile \
				--exec "${DAEMON_PATH}" -- $DAEMON_OPTS
			result=$?
		else
			start-stop-daemon --start --quiet --oknodo --background \
				--nicelevel $DAEMON_NICE \
				--chdir "${DAEMON_PWD}" \
				--pidfile "${DAEMON_PID}" --make-pidfile \
				--chuid "${DAEMON_USER}" \
				--exec "${DAEMON_PATH}" -- $DAEMON_OPTS
			result=$?
		fi
		log_end_msg $result
	fi
	return $result
}
 
do_stop() {
	local result
 
	pidofproc -p "${DAEMON_PID}" "${DAEMON_PATH}" > /dev/null
	if [ $? -ne 0 ]; then
		log_warning_msg "${DAEMON_NAME} is not started"
		result=0
	else
		log_daemon_msg "Stopping ${DAEMON_DESC}" "${DAEMON_NAME}"
		killproc -p "${DAEMON_PID}" "${DAEMON_PATH}"
		result=$?
		log_end_msg $result
		rm "${DAEMON_PID}"
	fi
	return $result
}
 
do_restart() {
	local result
	do_stop
	result=$?
	if [ $result = 0 ]; then
		do_start
		result=$?
	fi
	return $result
}
 
do_status() {
	local result
	status_of_proc -p "${DAEMON_PID}" "${DAEMON_PATH}" "${DAEMON_NAME}"
	result=$?
	return $result
}
 
do_usage() {
	echo $"Usage: $0 {start | stop | restart | status}"
	exit 1
}
 
case "$1" in
start)   do_start;   exit $? ;;
stop)    do_stop;    exit $? ;;
restart) do_restart; exit $? ;;
status)  do_status;  exit $? ;;
*)       do_usage;   exit  1 ;;
esac
```

Set permissions to run:

`sudo chmod +x /etc/init.d/syncthing`

Tell system to run on boot:

`sudo update-rc.d syncthing defaults`

If you need to run syncthing:

`sudo service syncthing start`

Admin your Syncthing on your Pi: 

`http://192.168.1.69:8384`
