# Backup 

## Image remotely

```
ssh pi@{ip or hostname} "sudo dd if=/dev/{yourdevice} bs=1M" | gzip - | dd of=~/Desktop/pibackup.gz
```

Press `ctrl T` to get the status while the command is running.

`{yourdevivce}` should look like `mmcblk0` or `sda`. To figure this out, ssh into your machine and type the command `lsblk -p` for output like this:

```
pi@raspberrypi:~ $ lsblk -p
NAME MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
/dev/mmcblk0 179:0 0 29.9G 0 disk
\u251c\u2500/dev/mmcblk0p1 179:1 0 60M 0 part /boot
\u2514\u2500/dev/mmcblk0p2 179:2 0 3.7G 0 part /
```

To restore on a Mac (not sure about Linux...):

```
diskutil unmountDisk /dev/disk#
gzip -dc ~/Desktop/pibackup.gz | sudo dd of=/dev/rdisk# bs=1m conv=noerror,sync
```

## Rsync remotely

Backup `roms` into current directory

```
rsync -tvuaz -e ssh pi@icade4.local:/home/pi/RetroPie/roms ./
```

Suggest you use `screen` (`apt-get install screen`), run the rsync above and press `ctrl-a`, `ctrl-d` to let it continue. Then `screen list` or `screen -r` to get back in.
 
Sources: 
- https://www.reddit.com/r/RetroPie/comments/2y1lzb/a_simple_script_to_keep_romssaves_synced_between/
- https://stackoverflow.com/questions/15817583/rsync-multiple-remote-directories-to-local-machine-preserving-directory-paths
- https://raspi.tv/2012/using-screen-with-raspberry-pi-to-avoid-leaving-ssh-sessions-open