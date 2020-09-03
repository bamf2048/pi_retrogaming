# Overclocking (Pi 4)

Personally the only benefits to overflocking was improved performance in Sega Saturn (lr-yabause). Even then the games I tried were not playable at an enjoyable level (Nights into Dreams and Panzeer Dragoon).

Stable for me:

```sudo nano /boot/config.txt
over_voltage=6
arm_freq=2000
```

Did not get past the Retropie splashscreen:

```sudo nano /boot/config.txt
over_voltage=6
arm_freq=2147
gpu_freq=750
```

!> If your Pi fails to boot after editing the config.txt hold the Shift key while booting to ignore overclock settings **or**  plugin your card/usb into another device to edit your config.txt

## Guides

- https://magpi.raspberrypi.org/articles/how-to-overclock-raspberry-pi-4