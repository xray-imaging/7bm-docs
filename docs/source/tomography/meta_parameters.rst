Meta Data Parameters
=====================

The tomography data files are in HDF5 format.  HDF5 files have a tree structure of groups and datsets.  While a great deal of meta data are saved in each file automatically by the scan engine, the locations of the most important parameters can be difficult to find.  Below is a translation of parameters to their locations in the HDF5 file.


================================      ==================================================================
Parameter                             HDF5 location
================================      ==================================================================
Projection data                       /exchange/data
Dark fields                           /exchange/data_dark
Flat fields                           /exchange/data_white
Angles                                /exchange/theta
Magnification                         /measurement/instrument/detection_system/objective/magnification
Pixel resolution                      /measurement/instrument/detection_system/objective/resolution
Exposure time                         /measurement/instrument/detector/exposure_time
Equal flat and data exposures?        /process/acquisition/flat_fields/different_flat_exposure
Flat exposure time                    /process/acquisition/flat_fields/flat_exposure_time
Sample X location                     /measurement/instrument/sample_motor_stack/setup/x
Sample Y location                     /measurement/instrument/sample_motor_stack/setup/y
================================      =================================================================

