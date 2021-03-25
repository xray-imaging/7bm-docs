Saving experiment configurations
=============

It is often desirable to save the setup of a portion of an experiment (scan, motor, userCalc, delay generator settings) either for later use or to copy.  While the autosave module can be used to restore a record, it is more awkward to copy a record with autosave.  An alternative is to use a Python program, RecordSaver, to save and restore records.  

To use RecordSaver, 

Data sets are distributed using a `Globus <https://www.globus.org>`_, to use it you need to create 
a `Globus Account <https://docs.globus.org/how-to/get-started/>`_  and set up you computer as 
a `Globus EndPoint <https://www.globus.org/globus-connect-personal>`_.


Manual
------
**Note** This only applies if your data were stored on the APS data management system.

If you do not get the email with the direct link to your data, please follow these steps:

- login into Globus (with your personal globus credential)
- go to "Collection/Search" and search for the aps data select aps#data
- login in the the APS data management system using the same badge number/password combination that use to access the APS poroposal system but put a "d" in front of the badge number.  For example, if your badge number is 12345, you would enter d12345 as your user name.
- if you forgot your password you can reset it `here <https://beam.aps.anl.gov/pls/apsweb/forgot_password.start_process>`_
- go to /gdata/dm/7BM/ then seach for your data by year-month/PI last name
- set an end point on your computer (see `Globus EndPoint <https://www.globus.org/globus-connect-personal>`_) 
- download the data!


Raw Data Viewer 
---------------

To view the tomographic raw data we suggest to install `Fiji <https://imagej.net/Fiji>`_ and add 
the `HDF plugin <https://github.com/paulscherrerinstitute/ch.psi.imagej.hdf5>`_

Other options are `hdfview <https://support.hdfgroup.org/products/java/hdfview/>`_ or 
`argos <https://github.com/titusjan/argos>`_

Radiography and fluorescence data are generally stored in HDF5 format, which can be accessed through Matlab, Python, or other programming languages.
