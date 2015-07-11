Bluetooth audio sink on Raspberry pi.
-------------------------------------
With these scripts and a Bluetooth adapter you can make your RasPi work as Bluetooth audio sink (wireless speakers).


Dependecies
-----------
bluez
pulseaudio-module-bluetooth
python-gobject
bluez-tools


Important
---------
These scripts will modify your system. This can lead to unexpected behaviour on your installation.
Backups of original configs are stored to this project's path. You've been warned!


Install
-------
Configure your system:
```
$ ./configure
```
Install scripts:
```
$ ./install
```

Improvements
------------

This method relies on PulseAudio which doesn't really like to work without user session. 
This can be circumvented by adding automatic login to inittab.

Replace line containing something like this:
```
  1:2345:respawn:/sbin/getty --noclear 38400 tty1
```
With:
```
  1:2345:respawn:/sbin/agetty -a pi --noclear 38400 tty1 linux
```

Bluetooth audio source devices have to be paired and added to trusted devices on RasPi side. This could be automated to naively trust all pairers 
instead of manually running 
```
$ sudo bluez-test-device trusted xx:xx:xx:xx:xx:xx yes
```
everytime you want to add a new device to sources.
 
Credits
-------
Daniel Gillespie for gathering most of the information from various sources to his Instructables article http://www.instructables.com/id/Turn-your-Raspberry-Pi-into-a-Portable-Bluetooth-A/?ALLSTEPS

