Timing
============

.. contents:: 
   :local:

Timing and synchronization are mainly done with two Stanford DG645 timing generators, located in the control rack outside of the hutch.  Both units can be controlled using EPICS remotely from the control station.  Note that the DG645, unlike the earlier DG535, has fixed input (1 M-ohm) and output (50 ohm) impedances, so use 50 ohm terminators where appropriate.  

To further facilitate timing and synchronization, the beamline has an instance of softGlue, a simplified EPICS FPGA interface.  The controls for softGlue can be found on the 7-BM-B control screen.  By using softGlue, several low-level electronics functions can be implemented, such as counters, logical gates, decimation of signals, etc.

Synchronization with the pulse structure of APS is done using a signal from the Machine Status Link, located near the top of the control rack.  The P0 signal from the MSL is synchronized to the electron beam.  To trigger from the MSL, use a +2.0 V threshold, falling edge with 50 ohm termination.

When the storage ring is topped up, the electron beam is unstable for a few tens of ms afterward.  This can be problematic for time-resolved radiography measurements.  There is an EPICS PV that indicates when top-up occurs, but it has significant latency.  To have a hardware signal, the accelerator group ported down the top-up signal from their IOC on the mezzanine over fiber to 7bmb1 and installed a fiber to copper adapter card in the crate. The card produces a TTL signal that goes high 20 ms before the top-up event and goes low 10 ms after top-up. The signal expects 50 ohm termination. The complement of this signal is also available on the card.  We often use this signal as an inhibit on one of the DG645 timing generators to avoid taking data during top-up.
