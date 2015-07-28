---
layout: post
title: !binary |-
  VHVybmluZyBPTi9PRkYgd2lyZWxlc3Mgb24gQVNVUyBLNTJq
joomla_id: 90
joomla_url: !binary |-
  dHVybmluZy1vbm9mZi13aXJlbGVzcy1vbi1hc3VzLWs1Mmo=
date: 2011-03-31 21:31:42.000000000 +03:00
tags: [Asus, K52j, Slackware, Linux, wireless]
---
Here's a quick fix to enable/disable wireless using Fn+F2 on Slackware Linux on ASUS K52j and also the LED to indicate the status of the wireless.
First you need to create this file: `/etc/acpi/events/etc/acpi/events/asus-wireless-switch`
This file will contain the hotkey and the path to the script which is setting the wireless ON/OFF.
The `/etc/acpi/events/etc/acpi/events/asus-wireless-switch` content will be:

```
#Enable the Fn-F2 button to turn on/off wireless
#/etc/acpi/events/default
event=hotkey ATKD 0000005d
action=/etc/acpi/asus-wireless-switch.sh
```

Then create another one: `/etc/acpi/asus-wireless-switch.sh`

With this script in it:

```
#/etc/acpi/asus-wireless-switch.sh
#based on http://ubuntuforums.org/archive/index.php/t-1460790.html
#!/bin/sh
WLANSTATUS=`cat /sys/class/ieee80211/phy0/rfkill*/state`

test -z $WLANSTATUS && exit 1

if [ $WLANSTATUS = 0 ]; then
        echo 0 > /sys/devices/platform/asus_laptop/wlan
        echo 1 > /sys/class/ieee80211/phy0/rfkill*/state
elif [ $WLANSTATUS = 1 ]; then
        echo 1 > /sys/devices/platform/asus_laptop/wlan
        echo 0 > /sys/class/ieee80211/phy0/rfkill*/state
fi
```
