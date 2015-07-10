Bluetooth audio sink on Raspberry pi.
-------------------------------------
With these scripts and a Bluetooth adapter you can make your RasPi work as Bluetooth audio sink (wireless speakers).

Dependecies
-----------
bluez
pulseaudio-module-bluetooth
python-gobject
bluez-tools

Disclamer
---------
Installing will modify your bluez and pulseaudio configurations! This can lead to unexpected behaviour.
Backups of original configs are stored to this project's path. You've been warned!

Install
-------
$ ./configure

$ ./install

Improvements
------------

This method relies on PulseAudio which doesn't really like to work without user session. 
This can be circumvented by adding automatic login to inittab.

Replace line containing something like this:
  1:2345:respawn:/sbin/getty --noclear 38400 tty1
With:
  1:2345:respawn:/sbin/agetty -a pi --noclear 38400 tty1 linux


Credits
-------
Daniel Gillespie <danielg@danielgillespie.net> for gathering most of the information to his Instructables article.

