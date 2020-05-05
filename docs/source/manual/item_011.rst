Viewing Data 
===============

Imaging and tomography 
----------------------

To view the images from cameras at the beamline, use ImageJ with the EPICS ADViewer plugin.  To start ImageJ, select ImageJ from the Tools menu on the bottom of the 7-BM-B control screen.

To open the ADViewer plugin, in ImageJ, go to Plugins -> EPICS_areaDetector -> EPICS AD Viewer.  If you have the correct camera IOC name in the PVPrefix field of the viewer window that pops up, the camera IOC is running.  Click the Start button to start displaying images.  Note that no images will be displayed until the camera starts streaming images.

Tomography projection data is stored in `Data Exchange <https://dxfile.readthedocs.io/en/latest/source/xraytomo.html>`_ format, which is based on HDF5 format.  The easiest way to view these data, including metadata, is to use `hdfview <https://support.hdfgroup.org/products/java/hdfview/>`.  To open hdfview, select HDFView from the Tools menu on the bottom of the 7-BM-B control screen.

Tomography reconstruction data are typically stored as TIFF stacks.  To view these, ImageJ is the easiest choice.  Try using File -> Import -> Image Sequence to load the data.  Keep in mind that large datasets may take considerable time to load.

Time-Averaged Point Scan Data
-------------------------------

To view the data files written by the scan record, use dview, a tool written by Dohn Arms from APS BCDA.  Select dview from the Tools menu on the bottom of the 7-BM-B control screen.  This program allows fast flipping through different scan files, visualizing multiple variables at once, and 2D visualizations for multidimensional scans.  It also allows for applying arbitrary functions to the data, allowing simple conversions for data visualization.
