Detector Startup
================

Cameras  
-------

All single-frame cameras at the beamline use areaDetector, allowing an easy interface with other EPICS applications.

The areaDetector IOCs used to run the camera are set up to run in Linux screen sessions.  To check which detectors might 
be running on a given computer, either look at the control screens (they should mostly be white if the IOC 
is not working), or type::

    $ screen -ls

The output from this command will give the name of each screen session.  To connect to a screen session named,
for example, *ioc7bm_pg1*, type::

    $ screen -r ioc7bm_pg1

To start the areaDetector IOC for the Prosilica camera, used for beam focusing and alignment, type::

    $ ~/bin/start_Prosilica_IOC

Likewise, to stop this IOC (for example, before powering it off), type::

    $ ~/bin/stop_Prosilica_IOC

For the FLIR (Point Grey) cameras, the number of the camera (1-4) is on a label on the camera.  These cameras are
USB3, which means that the IOC must run on the computer to which the camera is physically connected.
To start the areaDetector IOC for camera 1, for example, type::

    $ ~/bin/start_IOC_pg1

To stop the IOC, type::

    $ ~/bin/stop_IOC_pg*n*
