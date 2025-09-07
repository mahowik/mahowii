
===================================
MahoWii rev 2.4 
===================================

Hi guys!

Here is the latest revision of my favorite hobby project based on Multiwii project.
In two words: it's pretty stable, improved and extended version of Multiwii.

Changes:
- INS (inertial navigation system) integrated with GPS and Baro
- predefined PIDs to fly out of the box for frames 330 and bigger

- completely different precise althold integrated with INS
- right altitude management by setting desired vario (vertical speed) with throttle stick
- single PID controller for hovering and altitude management
- stable hovering trottle estimator/corrector by I-part of alt PID controller
- smart land detector
- reduced effect of air-cushion to avoid incorrect raw baro values and jumps near the ground accordingly (integrated with INS)
- controllable by desired vario (vertical speed) landing 
- new SAFE_ALT_DURING_AH define. It helps to protect descending less than specified in define altitude. Activated when SAFE_ALT box activated in GUI.

- precise, rapid, sensitive to external perturbations (wind, pushes) GPS-INS position hold (INS_PH_NAV_ON define)
- possibility to fly with activated position hold and stop at predicted point on stick release (tunable by Pos-I value at GUI)
- wait for target altitude at RTH and WP navigation
- skip whole RTH cycle if distance less than RTH_RADIUS meters and make a landing
- safe and soft takeoff on RTH and WP Navigation
- for safety prevent arm if RTH or NAV switched on
- new auto config defines for UBLOX and MTK3339 modules

- precised gyro calibration + 3 axis acel calibration + filtered mag calibration to avoid min/max noise values
- frsky telemetry adopted for er9x-frsky TX firmware 
- 50hz PID output for althold, gps modes
- cycle time independent final PID controller 
- optimized math
- a lot of fixes 

For more details please read release_note.txt, see config.h and also here http://forum.rcdesign.ru/blogs/83206/blog22332.html

Tips and tricks:
- for INS it's better to use u-blox modules with revision from 6 to 8 (although 7th was not tested). With MTK modules position hold is less precise but in general it's ok also, where PID parameters has to be ~20% less for its.
- for INS it's good to have calibrated accel in 3 axises with +/-512 for each axis with error +/-(1-3)
- for configuration the best tool is https://play.google.com/store/apps/details?id=com.ezio.multiwii
- for this release arduino 1.6.7 was used https://www.arduino.cc/en/Main/OldSoftwareReleases
- before 1st upload clean eeprom http://forum.rcdesign.ru/f123/thread283798-74.html#post4263236

This firmware was optimized for AIOP (ALL IN ONE PRO Flight Controller), or other with Atmega1280/2560 + mpu6050 + ms5611 + hmc5883 (but take care about pinout). But you can try to play with other sensors also.

Videos from my friend's youtube channel: 
https://www.youtube.com/user/artnesterof/videos

Blogs:
- https://www.rcgroups.com/forums/showthread.php?t=2787668
- http://www.multiwii.com/forum/viewtopic.php?f=8&t=7877
- http://forum.rcdesign.ru/blogs/83206/

Enjoy! ;)  

[![Donate](https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif)](https://paypal.me/arhutich)


