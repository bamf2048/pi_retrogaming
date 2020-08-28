# Before first-time boot

Here are some things that you can set before booting. You don't need to but it can be handy later on but you'll have to dig through a bunch of menus.

After imaging, your sd card, usb stick or ssd will have two partitions. The boot partition can be read by Windows, Mac and Linux. You can edit/add files to configure how the system will boot.


## Enable SSH

Add an empty ssh file to `/boot`. After booting you will be able to access the Pi by *IP address* or *hostname*. After booting you can change the [hostname](#set-hostname).


## Connect to WiFi

Create a `wpa_supplicant.conf` file on your /boot with these contents.

```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=<Insert 2 letter ISO 3166-1 country code here>
network={
  ssid="<Name of your wireless LAN>"
  psk="<Password for your wireless LAN>"
}
```

More: https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md