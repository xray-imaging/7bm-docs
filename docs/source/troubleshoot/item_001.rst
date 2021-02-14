Starting Control Screens
========================

.. contents:: 
   :local:

If the beamline computer needs to be rebooted for some reason, or if the main window for the control screens gets closed, you will need to restart them manually.  The easiest way to do this is to go to a terminal on the Linux control computer type::

    $ cd ~/bin
    $ ./start_epics_auto

If this works properly, it should start a basic set of control screens.  If for some reason this doesn't work, you can use a more basic script, run by entering at the terminal::

    $ start_epics
