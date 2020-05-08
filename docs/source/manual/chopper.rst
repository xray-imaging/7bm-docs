Rotary Chopper
================

.. contents:: 
   :local:

The beamline is equipped with a rotary chopper to reduce x-ray exposure onto samples and detectors.  This is particularly relevant for studies with white beam, since prolonged white beam exposure on the scintillator crystals used for imaging can cause thermal cracking.  

The chopper consists of two notched copper disks bolted to each other and driven by a stepper motor.  Motor 27 is preconfigured to run the chopper.  Each disk has two notches, so x-rays are transmitted twice for every rotation of the chopper wheel.  The two disks can be manually rotated with respect to each other to change the duty cycle of the chopper by removing the aluminum cover over the disk, making sure to disconnect the motor first.

To operate the chopper, the stepper motor is simply spun for a fixed number of rotations.  For continuous operation, this number of rotations can be set to an arbitrarily large number.  For timing, the chopper is also equipped with a photoeye.  This photoeye is supplied with 12 VDC and outputs a 12 V signal when the chopper opening is at the photoeye.  The photoeye will be triggered approximately 1/6 of a rotation before the x-rays are allowed through.

**NOTE**: keep in mind that the chopper can only reduce x-ray exposure on components if it is either moving or if it is stopped at a point where the x-rays are being blocked.  A good way to ensure this is to index the chopper motor to start chopper motion at an orientation where the beam is blocked and move in integer rotations of the chopper. 
