Data reconstruction
===================

At the APS
----------

Your raw data are automatically copied from the detector to the analysis computer (handyn in this example) under the folder /local/data/YYYY-MM/PI_lastName. 


Login at the beamline Linux machine and then type::

    [user@workstation ~]$ tomopy recon -h


for help. More detailed instruction are at https://github.com/tomography/tomopy-cli

To do a test reconstruction just type::

    [user@workstation ~]$ tomopy recon --hdf-file /local/data/YYYY-MM/PI_lastName/file.h5 


At your home institution
------------------------

Please follow `these instrutions <https://docs2bm.readthedocs.io/en/latest/source/user/item_006.html>`_