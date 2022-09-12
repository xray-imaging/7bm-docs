============================
Radiography
============================

Radiography is typically performed with a focused beam at 8 keV, though other energies can be used.  The typical detector is a PIN diode, the output of which is amplified with a transimpedance amplifier.  Readout is now typically done with a high-speed digitizer and custom Python program.  Traditionally, this was done with a oscilloscope and a custom Java program, DataGrabber.


PIN Diodes
-----------------

The beamline is equipped with several PIN diodes for measuring beam intensity.  These PIN diodes are silicon Hamamatsu x-ray photodiodes in a brass casing designed by the APS Detector Pool.  The diodes are covered with electrically-conductive Kapton film to seal out ambient light.  There are three diodes with 10 x 10 mm active area (S3590-09, 300 micron thick) and one diode with 28 x 28 mm active area (S3584-09, 300 microns thick).  


Digitizer and Python Acquisition
--------------------------------

The main digitizer for the beamline is a Teledyne SPD ADQ14.  This digitizer is 14-bit, 500 MHz with four channels.  To run the digitizer, connect the power, then hook up the fiber network connection to the blue fiber connection dangling from the cable tray in 7-BM-B.  This connects the digitizer to prandtl.  On prandtl, start the digitizer with::
    
    [7bmb@prandtl]: ~/bin/softIOC ADQ start

To start the control screens for the digitizer, look under Analog I/O on the 7-BM-B control screen.  One must click the "ON" button to activate the digitizer.  Use "OFF" to reset the digitizer or to apply changes to the channel settings.  Click "RUN" to activate acquisition and "STOP" to abort.

To activate the Python script the controls the acquisition and interfaces between the scan record and the digitizer, do the following::

    [7bmb@karman]: cd /home/beams/7BMB/Python/adq14_scripts
    [7bmb@karman]: python scan_script2.py

Data are saved in HDF5 format, with each acquistion saved separately (i.e., not averaged in hardware).  To view the data, use hdfview or::

    [7bmb@karman]: cd /home/beams/7BMB/Python/adq14_scripts
    [7bmb@karman]: python scan_view.py

Some notes for the digitizer:

* The digitizer can be the only soft IOC running on prandtl.  Turn off all other soft IOCs (e.g., cameras) before starting the digitizer IOC.

* The digitizer support is not incredibly stable.  If the digitizer throws a fault, attempt to reset it by turning the digitizer off, then on again in the control screen. If this doesn't work, it may need to be power cycled.  Due to this fact, it is useful to put the digitizer on an outlet that can be controlled automatically.


Oscilloscope
------------

The main digital oscilloscope for 7-BM is a Yokogawa DLM2054 oscilloscope.  This oscilloscope is 4-channels with 8 bits of vertical resolution.  Some points to keep in mind when using the oscilloscope:

* There is an external trigger in terminal on the back panel of the oscilloscope.  Using this terminal for a TTL trigger in not only saves a channel for data but tends to result in less cross-talk between the trigger signal and data signals.
* The display on the front panel of the scope shows eight vertical divisions.  The scope will actually record one division above and below the range of the display.
* If a user is filtering a channel on the oscilloscope, it is essential that the entire trace fit into the vertical range of the oscilloscope **before** filtering.  Simply checking that no clipping is occurring on the filtered data *is not* sufficient and may result in corrupted data.
 
DataGrabber
-----------

To use this to take time-resolved radiography data, we use a Java program called DataGrabber, written by Chris Powell from Argonne's Energy Systems division.  DataGrabber is run from the Windows workstation at the user station.  It controls the oscilloscope and records the oscilloscope traces and meta data to a binary or ASCII data file.  While DataGrabber can be used to manually control the oscilloscope and record data, it is most commonly used to automate the recording of time-resolved data.

DataGrabber uses an EPICS busy record (7bmb1:rad:get_data) to handshake between EPICS and DataGrabber.  DataGrabber watches for the record to change to "Busy".  It then triggers the oscilloscope to take a trace.  When the oscilloscope is finished, DataGrabber will download the data from the oscilloscope and record it to file.  When the file is written, DataGrabber will set the busy record to "Done".  This provides the signal to an EPICS scan that the point in question is finished.

To start DataGrabber:

* Double-click on the "DataGrabber" icon on the Windows workstation desktop.
* Connect to APS EPICS to enable monitoring of EPICS PVs.
* Connect to the oscilloscope, named "Yoko4".  This will display a dialog box to set which channels to display and save.  Each one will display in a separate tab in the DataGrabber interface.
* Set names for the tabs.  These will be recorded in the data file meta data.
* Set the destination for files.
* Turn on automatic control using the "Be a Slave" button in the bottom left corner of the display.

Notes when using DataGrabber:

* DataGrabber must be in Slave mode to automatically control the scope.  Click on the "Be a Slave" button in the bottom left corner of the DataGrabber window to toggle slave mode status.  

* When DataGrabber is in Slave mode, the controls on the scope front panel are locked.  You must take DataGrabber out of slave mode to change scope settings.  It is highly recommended to take at least one trace with the new settings (to make sure they are properly read by DataGrabber) before returning to Slave mode.

* For rapid data acquisition, carefully optimize the trigger frequency.  If a trigger signal is received by the oscilloscope while it is transferring data, it will be ignored.  Thus, a slower repetition rate where the scope triggers on every trigger can at times be faster than using a faster repetition rate where the scope only records every other trigger. 
