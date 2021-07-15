Saving experiment configurations
================================

It is often desirable to save the setup of a portion of an experiment (scan, motor, userCalc, delay generator settings) either for later use or to copy.  While the autosave module can be used to restore a record, it is more awkward to copy a record with autosave.  An alternative is to use a Python program, RecordSaver, to save and restore records.  

To use RecordSaver, at the terminal on the beamline workstation, simply type::

    [user@workstation ~] RecordSaver

This will show the main RecordSaver window shown below. 

.. image:: img/recordsaver.png
   :width: 640px
   :align: center
   :alt: RecordSaver main window

To save a record, type the PV prefix into the record name field.  For example, for motor 1 this would be 7bmb1:m1.  Next, select the record type, which in this case would be Motor.  Click "Save Record".  This will bring up a dialog box to save the record.  Select an appropriate name and directory, then click save.  NOTE: do not give the name of the database a file extension, the program will add this during the saving process.  After a few seconds, the record will be saved.  

To restore a record, again enter the PV prefix name and record type.  Click "Restore Record" to bring up a dialog box of which file to open.  Select the saved record you wish to load, then click "Open" to fill in this record with the saved values.

.. contents:: 
   :local:
