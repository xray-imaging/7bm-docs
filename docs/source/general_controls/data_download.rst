Data download
=============

Automatic
---------

At the beginning of the beamtime all users listed in the proposal receive an email with a direct link and instructions on how to download data from the APS.

Data sets are distributed using a `Globus <https://www.globus.org>`_, to use it you need to create 
a `Globus Account <https://docs.globus.org/how-to/get-started/>`_  and set up you computer as 
a `Globus EndPoint <https://www.globus.org/globus-connect-personal>`_.


Manual
------
**Note** This only applies if your data were stored on the APS data management system.

If you do not get the email with the direct link to your data, please follow these steps:

- login into Globus (with your personal globus credential)
- go to "Collection/Search" and search for the aps data select APS:DM:7BM
- login in the the APS data management system using the same badge number/password combination that use to access the APS poroposal system 
- if you forgot your password you can reset it `here <https://beam.aps.anl.gov/pls/apsweb/forgot_password.start_process>`_
- go to / then seach for your data by year-month/PI last name
- Activate an end point on your computer (see `Globus EndPoint <https://www.globus.org/globus-connect-personal>`_) 
- Transfer the data to your computer.  Note that the APS data volumes are read only through the Globus Online interface.

Another resource with instructions regarding retrieval of data saved with the APS data management system can be found `here <https://git.aps.anl.gov/DM/dm-docs/-/wikis/DM/HowTos/Getting-Data-From-Globus>`_ 


Raw Data Viewer 
---------------

To view the tomographic raw data we suggest to install `Fiji <https://imagej.net/Fiji>`_ and add 
the `HDF plugin <https://github.com/paulscherrerinstitute/ch.psi.imagej.hdf5>`_

Other options are `hdfview <https://support.hdfgroup.org/products/java/hdfview/>`_ or 
`argos <https://github.com/titusjan/argos>`_

Radiography and fluorescence data are generally stored in HDF5 format, which can be accessed through Matlab, Python, or other programming languages.
