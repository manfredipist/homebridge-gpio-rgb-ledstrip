# homebridge-gpio-rgb-ledstrip
[RPi](https://www.raspberrypi.org) GPIO based LED Strip plugin for [Homebridge](https://github.com/nfarina/homebridge)

Due to all the changes and updated that have occured in Homebridge since the original release of this plugin, i decided to replace its core to extend its usability and compatibility.
This plugin now relies on pi-blaster.js which you need to install beforehand.


Originally inspired by [GiniaE/homebridge-gpio-ledstrip](https://github.com/GiniaE/homebridge-gpio-ledstrip)

# Installation

1. Install [pi-blaster](https://github.com/sarfata/pi-blaster).
2. Update pi-blaster DAEMON_OPTS configuration under the path /etc/default/pi-blaster to enable your specific pin layout ([instructions](https://github.com/sarfata/pi-blaster#warnings-and-other-caveats)).
3. Install [homebridge-gpio-rgb-ledstrip] directly from Homebridge Plugin Page or by running sudo npm install -g homebridge-gpio-rgb-ledstrip.
4. Update your configuration file. See sample config.json snippet below. Remember to use BCM GPIO layout.

To identify the correct pin configuration, have a look at the following layout

![pi-blaster pinout](https://github.com/manfredipist/homebridge-gpio-rgb-ledstrip/blob/master/images/pinout.xyz.png?raw=true)

P.S: if pi-blaster seems not to work (e.g running the command 'echo "$PIN=1" > /dev/pi-blaster' doesn't yield the desired output), try restarting manually the service with root privileges

# Configuration

Configuration sample:

 ```
    "accessories": [
      {
        "accessory": "SmartLedStrip",
        "name": "Bedroom LedStrip",
        "rPin": 22,
        "gPin": 27,
        "bPin": 17
      }
    ]
```

Fields:

* "accessory": Must always be "SmartLedStrip" (required)
* "name": Can be anything (required)ß
* "rPin": GPIO pin that is used to set red value (required)
* "gPin": GPIO pin that is used to set green value (required)
* "bPin": GPIO pin that is used to set blue value (required)
