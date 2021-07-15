Data analysis
=============

At the APS
----------

Your raw data are automatically copied from the detector to the analysis computer (handyn in this example) under the folder /local/data/YYYY-MM/PI_lastName. 

Manual
~~~~~~

To manually reconstruct a data set, use the `tomopy cli <https://github.com/tomography/tomopy-cli>`_. 

For help::

    [tomo@handyn,~]$ tomopy recon -h

To do a test reconstruction type::

    [tomo@handyn,~]$ tomopy recon --file-name /local/data/YYYY-MM/PI_lastName/file.h5 

More detailed instruction are at `tomopy cli <https://github.com/tomography/tomopy-cli>`_.


Automatic
~~~~~~~~~

To setup a reconstruction to start automatically type::

    [tomo@handyn,~]$ bash
    [tomo@handyn,~]$ auto_rec /local/data/YYYY-MM/PI_lastName/

auto_rec runs tomopy recon for each newly transferred data set with the following options::

    tomopy recon --reconstruction-type try --file-name /local/data/YYYY-MM/PI_lastName/data.h5


At your home institution
------------------------

Install the following::

    Conda: https://www.anaconda.com/download/
    tomopy: https://tomopy.readthedocs.io/en/latest/
    tomopy-cli: https://github.com/tomography/tomopy-cli

then you can run reconstrutions with::

    $ tomopy recon --file-name /data/file.h5

More detailed instruction are at `tomopy cli <https://github.com/tomography/tomopy-cli>`_.

