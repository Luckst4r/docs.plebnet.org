# Backup Power

#### Add a Backup Power Supply

A UPS \(uninterruptible power supply\) ensures that your node continue to function through minor power fluctuations and power outages.

If you don't shut your Raspberry Pi down properly this is essentually the same as pulling the power cord out of your desktop computer every time you want to shut it down. When this happens, you risk corrupting your device's SD card, as well as data on your hard drive.

The solution is to you plug your device into a high-output power bank. This is basically a juiced-up version of what you might use to charge your phone while camping. The battery pack gets plugged into the wall and your device gets plugged into the battery pack.

A UPS should only be relied on to provide you with enough time to safely shut down your node until your power is restored. You should not connect your router or modem to the UPS due to potential data corruption that may occur if your node is in the process of writing to the disk when a power outage occurs.

Many UPS devices have a loud audible alert that will be triggered when the power goes out.

Here are some options to consider:

* [https://amzn.com/B01FWAZEIU](https://amzn.com/B01FWAZEIU)
* [https://amzn.com/B00DBAA696](https://amzn.com/B00DBAA696)
* [https://amzn.com/B07BXZPF99](https://amzn.com/B07BXZPF99)
* [https://amzn.com/B073Q3BSPG](https://amzn.com/B073Q3BSPG)

**Advanced UPS Setup**

If you want to automate a graceful shutdown for the node once the UPS power capacity goes to a minimum level, you can connect the UPS Serial port \(via USB\) to the Raspberry Pi or PC and have it communicate with the UPS once configuring the UPS daemon in the Pi or you Linux setup correctly, it will initiate a graceful shutdown if the capacity hits 5%

The following steps should be run via SSH:

```text
sudo apt-get install apcupsd
sudo nano /etc/default/apcupsd
```

In /etc/default/apcupsd change 'ISCONFIGURED=no' to 'ISCONFIGURED=yes'

```text
sudo nano  /etc/apcupsd/apcupsd.conf
```

Change the values as below, make sure the DEVICE field is empty, the default is /dev/ttyS0 and should be cleared.

```text
UPSNAME myups
UPSCABLE usb
UPSTYPE usb
DEVICE
```

Note - Make sure the Restart apcupsd

```text
sudo apcupsd restart
```

Check UPS status:

```text
apcaccess status
```

output example:

```text
$ apcaccess status
APC      : 001,035,0900
DATE     : 2021-06-14 02:13:51 +0000
HOSTNAME : umbrelmavic
VERSION  : 3.14.14 (31 May 2016) debian
UPSNAME  : myups
CABLE    : USB Cable
DRIVER   : USB UPS Driver
UPSMODE  : Stand Alone
STARTTIME: 2021-06-13 01:38:35 +0000
MODEL    : Back-UPS ES 350
STATUS   : ONLINE
LINEV    : 120.0 Volts
LOADPCT  : 0.0 Percent
BCHARGE  : 100.0 Percent
TIMELEFT : 36.4 Minutes
MBATTCHG : 5 Percent
MINTIMEL : 3 Minutes
MAXTIME  : 0 Seconds
SENSE    : High
LOTRANS  : 88.0 Volts
HITRANS  : 139.0 Volts
ALARMDEL : 30 Seconds
BATTV    : 13.7 Volts
LASTXFER : Unacceptable line voltage changes
NUMXFERS : 1
XONBATT  : 2021-06-13 01:50:34 +0000
TONBATT  : 0 Seconds
CUMONBATT: 251 Seconds
XOFFBATT : 2021-06-13 01:54:45 +0000
STATFLAG : 0x05000008
SERIALNO : XXXXXXXXXXXX
BATTDATE : 2007-06-08
NOMINV   : 120 Volts
NOMBATTV : 12.0 Volts
FIRMWARE : 823.B1.D USB FW:B1
END APC  : 2021-06-14 02:13:55 +0000
```

Once the output looks correct, specifically the STATUS shows as ONLINE, you can test the setup by disconnecting the UPS from the main power, watch the message prompts on the terminal and and let the battery drain until the point that a showdown will be initiated, this will confirm that your setup is correct.

