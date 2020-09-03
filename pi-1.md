# Pi 1/Zero

![RPi1B](https://res.cloudinary.com/bamf2048/image/upload/t_300px/Raspberry-Pi-3-top-down-web_bkachm.jpg)

Pi 1 and Zero should be able to run 8/16 bit consoles. SNES SuperFX and GBA may not be full-speed. That said, **I**, personally, don't recommend using either one even though the Pi Zero is so damned cute.

## Increase performance by overclocking

To run emulators smoothly you must overclock. Add this to your `config.txt`:

```sudo nano /boot/config.txt
arm_freq=1000
sdram_freq=500
core_freq=500
over_voltage=6
temp_limit=75
boot_delay=0
disable_splash=1
```

These are safe settings that people claim not to need to use heatsinks.

Source: https://haydenjames.io/raspberry-pi-safe-overclocking-settings/


## Pi Zero Performance

- set to 720p:

```sudo nano /boot/config.txt
hdmi_group=1
hdmi_mode=4
```

- make sure your usb hub isn't drawing too much power (compare speeds by unplugging/plugging in)
- make sure you have a good power supply - do you get the lighting bolt in the top right corner?

### Overclock the Pi Zero

Check out [ETA Prime's Tip](https://www.youtube.com/watch?v=3ndgLXz4e90) and use a heat sink!


## Pi1: USB Wifi not working?

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