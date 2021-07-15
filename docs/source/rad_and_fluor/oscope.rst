Measurements with Oscilloscope
================================

.. contents:: 
   :local:

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
