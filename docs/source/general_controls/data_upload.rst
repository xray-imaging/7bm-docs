Data Uploading
==============

Data are normally uploaded to voyager, the main APS data storage site, using the APS Data Management tools.  Two programs have been written to facilitate setting up automated data transfers, dmagic and globus.

DMagic
-----------
`DMagic <https://github.com/aps-7bm/DMagic>`_ is a python program that queries the APS scheduling system and fills in PVs with user information.  These PVs are read by globus (see below) to set up the experiment in the Data Management system.

To use DMagic, first make sure TomoScan is running, since that is where the relevant PVs are stored.  Then,follow the directions `here <https://dmagic.readthedocs.io/en/latest/source/usage.html>`_.

globus
-------
`globus <https://github.com/xray-imaging/globus>`_ is a python script that automatically creates a directory on a globus server as "year-month/pi_last_name" (or any other preset path) and sends a customizable notification email to "pi_email" that includes the URL to the shared folder.

To use globus, follow `this directions <https://github.com/xray-imaging/globus>`_
