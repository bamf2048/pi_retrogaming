# Pi 1

Pi 1 and Zero should be able to run 8/16 bit consoles. SNES SuperFX and GBA may not be full-speed.

# Not Retropie related...

## USB Wifi not working?

Raspian Stretch removed support for some USB Wifi chips. Try installing new drivers with this script that tries
to autodetect your hardware and os:

```
sudo wget http://downloads.fars-robotics.net/wifi-drivers/install-wifi -O /usr/bin/install-wifi
sudo chmod +x /usr/bin/install-wifi
sudo install-wifi
```

<details>
<summary>What does this do?</summary>

1. download script to /usr/bin
2. make it executable
3. run it

</details>

From https://www.raspberrypi.org/forums/viewtopic.php?f=28&t=62371