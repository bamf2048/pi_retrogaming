# Configuration

Most of the following things can be done using `raspi-config` or using the Retropie section. 
But if you're confortable editing files and navigating a Linux filesystem... 
or perhaps you'd like to script all these settings for multiple Pi's...


## Set hostname

By default you can access the Pi by retropie.local on your network. 
Personally **I strongly suggest you change the hostname** especially if you have more than one Retropie running.
Change it by editing these two files and entering the same name you wish to use: 

- `sudo nano /etc/hostname`
- `sudo nano /etc/hosts`


## Set keyboard language

The keyboard is pre-set to UK (because the Retropie Team are from the UK).

Example set to US keyboard: 

`sudo nano /etc/default/keyboard`, change `gb` to `us`

Reboot!


## Set monitor resolution

Example for a 1024x600 monitor:

Add to `/boot/config.txt`

```
overscan_scale=1
hdmi_force_hotplug=1
hdmi_group=2
hdmi_mode=87
hdmi_cvt=1024 600 60
```

Reboot!

---

# Emulationstation


## Favourites, Recent Menus

1. In Emulationstation, press Start to open the Main Menu
2. Select Game Collection Settings
3. Choose Automatic Game Collections
4. Check the options you would like to appear


## Show game art in screensaver

1. In Emulationstation, press Start to open the Main Menu
2. Choose UI Settings
3. Select Screensaver Settings
4. Choose Screensaver Behavior 
5. Press left/right and choose Slideshow (or Random Videos)


## Scrape and get videos, marquees 

Use Selph's scraper: https://www.youtube.com/watch?v=rj1841sL8ro&feature=youtu.be

---

# Controllers


## Set default controllers for a console

If you want to *not* use the default controler for player 1...

- Run a game for the console you want to change
- Select + X to open Retroarch GUI
- Change player 1 controller
- Change the rest of the player controllers otherwise one controller may be set or more than one player
- Save Config (will save only for the open system)


## Remove/delete all controllers

```
rm /home/pi/.emulationstation/es_input.cfg
```

---

# Using a SDD 

Mount ssd on every boot:
https://www.raspberrypi.org/documentation/configuration/external-storage.md

Boot from sd and then ssd (if ssd dies, edit /boot/command.txt to restore booting from ssd:

- https://retropie.org.uk/docs/Running-ROMs-from-a-USB-drive/#manual-mount
- https://www.raspberrypi.org/forums/viewtopic.php?t=202890
- https://jamesachambers.com/raspberry-pi-4-usb-boot-config-guide-for-ssd-flash-drives/

?> Tags: Hardware
