# Retropie Enhancements

These are enhancments that aren't installed by default but that I think pretty cool.

## Add more emulators and ports

**Retropie-Extra** is a collection of unofficial installation scripts for emulators, ports and libretrocores not included in Retropie.

!> Retropie-Extra is no longer mantained but still works.

```
cd ~
git clone https://github.com/zerojay/RetroPie-Extra.git
cd RetroPie-Extra/
./install-extras.sh
cd ~/RetroPie-Setup
sudo ./retropie_setup.sh
```

Source: https://github.com/zerojay/RetroPie-Extra


## Demo mode

This script plays a random games like a slideshow.

https://retropie.org.uk/forum/topic/25551/demo-mode-random-starting-of-games-for-es-retropie-menu


## Play Retropie in a browser from another computer

Install on a Pie, connect to your network via ethernet and play on a browser on your PC.

http://www.linux-projects.org/uv4l/tutorials/play-retropie-in-browser/


## Add "Pixel" Desktop

This is a full graphic UI with Chromium. You might find it easier to manage files using this.

In Emulationstation, go to Retropie Setup > Configuration / Tools > Raspbiantools > Install Pixel Desktop Environment.

You can go to the desktop in the Ports menu in Emulationstation or type `startx` from the terminal.


### Add Synaptic to Pixel Desktop

Allows you to easily install desktop applications. Synaptic is the App Store before there was the App Store.

```
sudo apt install synaptic
```
