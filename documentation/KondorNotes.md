This is a place to make notes about what makes Kondor tick.

https://github.com/kondor3d/kondor

It looks like the whole app is started with the /home/pi/run.sh script.  It is not clear to me how this automatically gets run at boot.
I did not see anything in rc.local, etc.

* It uses "Printrun" which seems to be part of the Pronterface project. Is that the gcode interpreter?
  * https://github.com/kliment/Printrun
  * https://www.pronterface.com/

* Printrun in turn, uses Flask as an http service to map http URLs to python functions in "printserver.py".  It looks like this controls
some type of file uploader via http POST, and possibly what the touchscreen UI is triggering.
  * https://flask.palletsprojects.com/en/1.1.x/

* The HDMI resolution is simply set with the max_framebuffer_height/width options in /boot/config.txt.  Nothing special there, we get
that "for free" because it's a Pi with a very decent, but proprietary GPU and driver.

* Config.txt also reveals that the 3.5" touchscreen is running via the waveshare35a overlay driver.  I've played with that software 
before, and I believe it's this LCD_Show tarball at the wiki below.  THis screen is configured as the (only) X display.
The hires screen does not appear to be controlled through X windows - it stays a console window the whole time.
  * https://www.waveshare.com/wiki/3.5inch_RPi_LCD_(C)

* The last app that gets started by the run.sh script is something called FonterControler.  I believe this is the main Qt/cpp program
at thegithub.  It must do the work of reading the files, displaying the layers, commanding the Z-axis, etc.  There is a thing called
Projector with writeFramBuffer() calls. So I guess the hires screen is just a dumb framebuffer.
