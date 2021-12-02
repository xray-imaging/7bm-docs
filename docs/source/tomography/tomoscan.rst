TomoScan
===============


.. _EPICS_NTNDA_Viewer: https://cars9.uchicago.edu/software/epics/areaDetectorViewers.html
.. _tomoScan: https://tomoscan.readthedocs.io/en/latest/index.html
.. _tomoScanStream: https://tomoscan.readthedocs.io/en/latest/api/tomoscan_stream_2bm.html
.. _tomoStream: https://tomostream.readthedocs.io/en/latest/about.html
.. _PVaccess: https://epics-controls.org/resources-and-support/documents/pvaccess/
.. _Data Exchange: https://dxfile.readthedocs.io/en/latest/source/xraytomo.html

TomoScan
--------

Tomography scans are managed by tomoScan, a tomography scanning engine developed by Mark Rivers from GSE-CARS and Francesco DeCarlo from the Imaging group to control tomography data acquisition.  

Starting tomoscan
-------------------


The tomography scans are managed by `tomoScan`_. Please refer to the `tomoScan`_ documentation for details.

To configure a single tomographic scan enter the acquistion parameters at:

.. image:: ../img/tomoScan.png
   :width: 480px
   :align: center
   :alt: tomoScan


To run a single scan with the parameters set in the tomoScan screen press the green **Start Scan** button. To collect the same from the command line interface::

    [user@workstation]$ tomoscan single

tomoscan supports also vertical, horizontal and mosaic tomographic scans with::

    [user@workstation]$ tomoscan vertical
    [user@workstation]$ tomoscan horizontal
    [user@workstation]$ tomoscan mosaic

to run a vertical scan::

    $ [user@workstation]$ tomoscan vertical --vertical-start 0 --vertical-step-size 0.1 --vertical-steps 2

    2020-05-29 16:54:03,354 - vertical scan start
    2020-05-29 16:54:03,356 - vertical positions (mm): [0.  0.1]
    2020-05-29 16:54:03,358 - SampleInY stage start position: 0.000 mm
    2020-05-29 16:54:03,362 - single scan start
    2020-05-29 16:54:51,653 - single scan time: 0.805 minutes
    2020-05-29 16:54:51,654 - SampleInY stage start position: 0.100 mm
    2020-05-29 16:54:51,658 - single scan start
    2020-05-29 16:55:47,607 - single scan time: 0.932 minutes
    2020-05-29 16:55:47,607 - vertical scan time: 1.738 minutes
    2020-05-29 16:55:47,608 - vertical scan end


to run a series of vertical scans starting from different locations::

    [user@workstation]$ for k in {0,5.2,10.4,15.6,20.8,26}; do tomoscan vertical --vertical-start $k --vertical-step-size 1.3 --vertical-steps 4; done

this will run::

        [user@workstation]$ tomoscan vertical --vertical-start 0 --vertical-step-size 1.3 --vertical-steps 4
        [user@workstation]$ tomoscan vertical --vertical-start 5.2 --vertical-step-size 1.3 --vertical-steps 4
        [user@workstation]$ tomoscan vertical --vertical-start 10.4 --vertical-step-size 1.3 --vertical-steps 4
        [user@workstation]$ tomoscan vertical --vertical-start 15.6 --vertical-step-size 1.3 --vertical-steps 4
        [user@workstation]$ tomoscan vertical --vertical-start 20.8 --vertical-step-size 1.3 --vertical-steps 4
        [user@workstation]$ tomoscan vertical --vertical-start 26 --vertical-step-size 1.3 --vertical-steps 4

please check the `command line manual  <https://tomoscan.readthedocs.io/en/latest/demo.html#using-the-tomoscan-cli>`_ for more details. 

Raw Data Viewer 
===============

To view the tomographic raw data we suggest to install `Fiji <https://imagej.net/Fiji>`_ and add `this HDF plugin <https://github.com/paulscherrerinstitute/ch.psi.imagej.hdf5>`_.

Other options are `hdfview <https://support.hdfgroup.org/products/java/hdfview/>`_ or 
`argos <https://github.com/titusjan/argos>`_.
