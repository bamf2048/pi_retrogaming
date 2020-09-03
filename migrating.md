# Migrating to new Pi

!> You cannot use the same SD card when migrating from a Pi Zero/1 to Pi 2/3 or Pi 4. Each one these groups has it own image to download on the Retrpie site. 

Copy the following folders:

```
/etc/emulationstation  
/opt/retropie/configs  
/home/pi/RetroPie/BIOS  
/home/pi/RetroPie/roms 
```

You might also want to copy ports but I had trouble with Heboris working properly.

```
/opt/retropie/ports
```

Also recommmended by Reddit:

- `/boot/config.txt` -- The main boot command that tells Raspberry Pi how to act. Configures overclock settings.
- `/opt/retropie/configs/all/emulationstation/collections` -- The folder that contain all your custom collections
- `/opt/retropie/configs/all/retroarch/autoconfig` -- Controller configuration files.
- `/opt/retropie/` -- I personally back up all my retropie config files because I have overlays added for handhelds, and all lr- sstems really. If I accidentally screw up a RetroArch config, I always have these to fall back on.
- `/opt/retropie/configs/all/emulationstation` -- If you've moved your es_settings.cfg to this location don't forget about it! Tis keeps your es_settings.cfg file permanent until you manually change it. I personally use this.
- `/home/pi/.local/share/mupen64plus/hires_texture` -- N64 Hi-Res textures if you have them.
- `/opt/retropie/configs/scummvm/scummvm.ini` -- can be helpful if you change your save location for scummvm. Default is on the S card, I personally move it to my roms/scummvm/saves/ folder on my USB.
- `/opt/retropie/configs/all/retroarch/overlay/` -- Gotta save those overlays and configs!