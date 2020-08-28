# Other Cool Shit

## Motioneye

Motioneye is a security camera system with web interface. You can connect multiple webcams/cameras, detect motion to capture photos or videos. Motioneye runs in the background.

```
sudo -i
apt-get update
apt-get install ffmpeg libmariadb3 libpq5 libmicrohttpd12
wget https://github.com/Motion-Project/motion/releases/download/release-4.2.2/pi_buster_motion_4.2.2-1_armhf.deb
dpkg -i pi_buster_motion_4.2.2-1_armhf.deb
apt-get install python-pip python-dev libssl-dev libcurl4-openssl-dev libjpeg-dev libz-dev
pip install motioneye
```

Note: If pillow installation fails (it always does...), you can try installing it from official repos using `apt-get install python-pillow`.

```
mkdir -p /etc/motioneye
cp /usr/local/share/motioneye/extra/motioneye.conf.sample /etc/motioneye/motioneye.conf
mkdir -p /var/lib/motioneye
cp /usr/local/share/motioneye/extra/motioneye.systemd-unit-local /etc/systemd/system/motioneye.service
systemctl daemon-reload
systemctl enable motioneye
systemctl start motioneye
```

Media will be stored in `/var/lib/motioneye`

Now visit by ip or hostname in your browser: `retropie.local:8765`. Plugin some usb webcams and add them by logging in as `admin`. You can also add other Motioneye Pi as a camera.

Upgrade:

```
pip install motioneye --upgrade
systemctl restart motioneye
```

https://github.com/ccrisan/motioneye/wiki/Install-On-Raspbian

## Take remote screenshots

Install:

```
git clone https://github.com/AndrewFromMelbourne/raspi2png
sudo cp -a raspi2png/raspi2png /usr/local/bin
```

From your Pi terminal or via SSH and type:

```
raspi2png -p SCREENSHOTNAME.png
```

https://retropie.org.uk/forum/topic/8896/taking-screenshots-from-emulationstation-s-menus/6

## Display images from terminal

Install: 

```
sudo apt-get update
sudo apt-get -y install fbi
```

Usage:

```
fbi -a myphoto.jpg
fbi -a *.jpg
fbi -a -t 5 *.jpg
```

https://www.raspberrypi-spy.co.uk/2017/02/how-to-display-images-on-raspbian-command-line-with-fbi/

## Print Server

Turns you printer into a wireless network printer. All of you computers can print to it.

https://www.makeuseof.com/tag/make-wireless-printer-raspberry-pi/

### Add Airprint

Airprint lets you print from your iPhone or Android device.

https://www.makeuseof.com/tag/add-airprint-support-raspberry-pi-print-server/


## Pixel Desktop

## Miscellaneous Bash 

- scan wifi networks: `sudo iwlist wlan0 scan | grep ESSID`
- show your Pi temp and diskspace: `retropie_welcome`