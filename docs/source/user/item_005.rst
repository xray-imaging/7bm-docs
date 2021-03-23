Data collection
===============


.. _EPICS_NTNDA_Viewer: https://cars9.uchicago.edu/software/epics/areaDetectorViewers.html
.. _tomoScan: https://tomoscan.readthedocs.io/en/latest/index.html
.. _tomoScanStream: https://tomoscan.readthedocs.io/en/latest/api/tomoscan_stream_2bm.html
.. _tomoStream: https://tomostream.readthedocs.io/en/latest/about.html
.. _PVaccess: https://epics-controls.org/resources-and-support/documents/pvaccess/
.. _Data Exchange: https://dxfile.readthedocs.io/en/latest/source/xraytomo.html

TomoScan
--------

The tomography scans are managed by `tomoScan`_. Please refer to the `tomoScan`_ documentation for details.

To configure a single tomographic scan enter the acquistion parameters at:

.. image:: ../img/tomoScan.png
   :width: 480px
   :align: center
   :alt: tomoScan


To run a single scan with the parameters set in the tomoScan screen press the gree **Start Scan** button. To collect the same from the command line interface::

    [user2bmb@pg10ge]$ tomoscan single

tomoscan supports also vertical, horizontal and mosaic tomographic scans with::

    [user2bmb@pg10ge]$ tomoscan vertical
    [user2bmb@pg10ge]$ tomoscan horizontal
    [user2bmb@pg10ge]$ tomoscan mosaic

to run a vertical scan::

    $ [user2bmb@pg10ge]$ tomoscan vertical --vertical-start 0 --vertical-step-size 0.1 --vertical-steps 2

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

    [user2bmb@pg10ge]$ for k in {0,5.2,10.4,15.6,20.8,26}; do tomoscan vertical --vertical-start $k --vertical-step-size 1.3 --vertical-steps 4; done

this will run::

        [user2bmb@pg10ge]$ tomoscan vertical --vertical-start 0 --vertical-step-size 1.3 --vertical-steps 4
        [user2bmb@pg10ge]$ tomoscan vertical --vertical-start 5.2 --vertical-step-size 1.3 --vertical-steps 4
        [user2bmb@pg10ge]$ tomoscan vertical --vertical-start 10.4 --vertical-step-size 1.3 --vertical-steps 4
        [user2bmb@pg10ge]$ tomoscan vertical --vertical-start 15.6 --vertical-step-size 1.3 --vertical-steps 4
        [user2bmb@pg10ge]$ tomoscan vertical --vertical-start 20.8 --vertical-step-size 1.3 --vertical-steps 4
        [user2bmb@pg10ge]$ tomoscan vertical --vertical-start 26 --vertical-step-size 1.3 --vertical-steps 4

please check the `command line manual  <https://tomoscan.readthedocs.io/en/latest/demo.html#using-the-tomoscan-cli>`_ for more details. 


Streaming data collection
-------------------------

`tomoScan`_ provides also support for *streaming data collection* (see `tomoScanStream`_ documentation for details). When collecting data in streaming mode, projections, 
dark and flat images are broadcasted using `PVaccess`_ and can be retrieved as EPICS PVs. 

**Streaming data collection** features are:

- Projection, dark and flat image broadcast as PV access variables
- On-demand retake of dark-flat field images
- On-demand data capturing with saving in a standard `Data Exchange`_ hdf5file
- Set a number of projectons ("Pre count") collected before a triggered data capturing event to be also saved in the same hdf5 file

All TomoScanStream functionalies can be controlled from the Streaming Control section of:

.. image:: ../img/tomoScanStream.png
    :width: 70%
    :align: center

Streaming data reconstruction
-----------------------------

The projection, dark and flat image broadcast provided by `tomoScanStream`_ can be used to reconstruct in real-time 3 orthogonal slices. This task is accomplished by `tomoStream`_.

**Streaming data reconstruction** features are:

- Streaming reconstruction of 3 (X-Y-Z) ortho-slices through the sample

- On demand adjustment of the

    - X Y Z ortho-slice positions
    - reconstruction rotation center
    - reconstruction filter

All `tomoStream`_ functionalies can be controlled from the tomoStream user interface:

.. image:: ../img/tomoStream.png
    :width: 60%
    :align: center

The output of **tomostream** is a live reconstruction diplaying in ImageJ using the `EPICS_NTNDA_Viewer`_ plug-in:

.. image:: ../img/tomoStreamRecon.png
    :width: 70%
    :align: center
    
While the sample is rotating is possible to optimize instrument (alignment, focus, sample to detector distance etc.) and  beamline (energy etc.) conditions and monitor the effect live on the 3 orthogonal slices. It is also possible to automatically trigger data capturing based on events occurring in the sample and its environment as a result of segmentation or machine learning.


Bluesky
-------

.. contents:: 
   :local:

To operate 2-BM using bluesky (currently in beta test in 2-BM-B) type::

    user2bmb@lyra$ use_bluesky.sh 2bmb

Once in the ipython shell type::

    RE(user_tomo_scan(), comment="my tomo fly scan", sample="wood stick")

or::

    RE(user_tomo_scan(acquire_time=0.1), comment="my tomo fly scan", sample="wood stick")
    RE(user_tomo_scan(acquire_time=0.1, iteration=10), comment="my tomo fly scan", sample="wood stick")


Raw Data Viewer 
===============

To view the tomographic raw data we suggest to install `Fiji <https://imagej.net/Fiji>`_ and add `this HDF plugin <https://github.com/paulscherrerinstitute/ch.psi.imagej.hdf5>`_.

Other options are `hdfview <https://support.hdfgroup.org/products/java/hdfview/>`_ or 
`argos <https://github.com/titusjan/argos>`_.
