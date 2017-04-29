# Raspberry Pi 1 (Model B)

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


## Green flickering lines on your display?

```
config_hdmi_boost=4
```

Sources:

https://www.raspberrypi.org/forums/viewtopic.php?f=28&t=7137
