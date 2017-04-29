# Pi Retrogaming

Retrogaming on the Raspberry Pi

## Mac: Find SDCard from Terminal

The instructions from Lakka are incorrect.

`diskutil list`

### Unmount (not eject)

If you card is disk4:

`diskutil unmountDisk /dev/disk4`

### Write the image to the SD card with dd

`dd if=/path/to/image.img of=/dev/rdisk4 bs=1m`
