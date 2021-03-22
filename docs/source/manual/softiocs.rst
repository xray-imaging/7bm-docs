EPICS Control IOCs
===================

Overview
----------

To control equipment via EPICS, an EPICS IOC must be set up on a computer to host the EPICS PVs for the equipment.  The IOC for most of the basic beamline equipment (motors, slits, delay generators) is hosted on the VME crates for the two hutches.  The IOCs for several pieces of equipment, however, including the single frame cameras and the MW100 data acquisition board, are programs running on the beamline Linux workstations.

Beamline staff have written a program called *softIOC* to allow users to 
start, stop, and restart IOCs easily.  It automatically places the IOC programs in Linux screen sessions, which allows them to run in the background.

To use the program, simply open a terminal on one of the beamline Linux workstations::

    [7bmb@karman ~] softIOC

This will provide a brief explanation of how the program is used.  Current equipment whose IOCs can be controlled this way include the MW100 data acquisition board in 7-BM-B and the Prosilica camera used for alignment.
