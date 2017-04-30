# Raspberry Pi 1 (Model B)

![RPi1B](https://res.cloudinary.com/dyxk2h3df/image/upload/t_300px/Raspberry-Pi-3-top-down-web_bkachm.jpg)

If you want to emulate 8 or 16-bit systems, you can still do it on the old Pi 1. The Pi Zero is presumably just a bit faster than the original Pi. Knowing this I went back to my old Pi, booted up Lakka and found the performance and sound really lacking. Only Turbo Graphx 16 games ran smoothly. Watching videos of the Zero just stumped me even more because I saw no noticable framerate or sound issues. So what's the answer?

## Overclocking

To run emulators smoothly you must overclock. Add this to your `config.txt`:

```
arm_freq=1000
sdram_freq=500
core_freq=500
over_voltage=6
temp_limit=75
boot_delay=0
disable_splash=1
```

These are safe settings that people claim not to need to use heatsinks.

Source:

https://haydenjames.io/raspberry-pi-safe-overclocking-settings/
