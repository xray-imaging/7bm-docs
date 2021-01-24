My Scan is Stuck!
=================


.. contents:: 
   :local:

If you attempt to run a scan and it isn't working, there are a few things you can check.

* Look in the upper area of the scan window to read the scan status.  If there is a problem that prevents the scan record from running (for example, the scan range falls outside the motor soft limits), it will be listed here.

* If you are performing scans with the oscilloscope, make sure that DataGrabber is in Slave mode.  Also, check the handshake busy record (found in the window with the sample stages).  Make sure it is set to "Done" before the scan starts.

* If you are doing fluorescence scans, make sure that the count time is set correctly on the fluorescence pulse processor.
