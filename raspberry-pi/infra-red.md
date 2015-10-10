# How to configure infrared sensor

### Raspberry Pi Model B+
### IR sensor - TSOP38238

In order to check how this was configured, read the `/etc/modules` file in this repo in addition to following these instructions.

1. Connect the IR sensor's power to 5V pin, ground to ground and data to *GPIO 18*
2. `sudo apt-get install lirc-dev`
3. edit `/etc/modules` to look similar to the one in this repo.
4. Open `/boot/config.txt` and make sure that *lirc-rpi* is not commented.

..*`dtoverlay=lirc-rpi`

Now run the following commands in exactly this order

1. `sudo modprobe lirc_rpi` (this should run successfully - no output to stdout)
2. `mode2 -d /dev/lirc0`
