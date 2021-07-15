High-Speed Imaging
==================

High-speed imaging at 7-BM is done with the white x-ray beam, with optional filters to reduce x-ray exposure.  An important consideration in these experiments is that the heat load from the white beam can quickly cause both radiation and thermal damage to both samples and the scintillator crystal used for x-ray imaging.  

Cameras
-------

The beamline is equipped with several single-frame machine vision cameras, which are capable of frame rates approaching 100 Hz.  See the Detectors page for more information on these cameras.  The beamline can also borrow high-speed Photron cameras (an SA4 easily and an SA-Z with more difficulty) for imaging high-speed movies.  These cameras are controlled using the Photron software from a Windows workstation at the user station.  The RJ-45 patch panels are used to connect these cameras to the computer.

Rotary Chopper
--------------

The beamline is equipped with a rotary chopper to reduce x-ray exposure onto samples and detectors.  This is particularly relevant for studies with white beam, since prolonged white beam exposure on the scintillator crystals used for imaging can cause thermal cracking.  

The chopper consists of two notched copper disks bolted to each other and driven by a stepper motor.  Motor 27 is preconfigured to run the chopper.  Each disk has two notches, so x-rays are transmitted twice for every rotation of the chopper wheel.  The two disks can be manually rotated with respect to each other to change the duty cycle of the chopper by removing the aluminum cover over the disk, making sure to disconnect the motor first.

.. image:: img/chopper.png
   :width: 320px
   :align: center
   :alt: Image of chopper

To operate the chopper, the stepper motor is simply spun for a fixed number of rotations.  For continuous operation, this number of rotations can be set to an arbitrarily large number.  For timing, the chopper is also equipped with a photoeye.  This photoeye is supplied with 12 VDC and outputs a 12 V signal when the chopper opening is at the photoeye.  The photoeye will be triggered approximately 1/6 of a rotation before the x-rays are allowed through.

**NOTE**: keep in mind that the chopper can only reduce x-ray exposure on components if it is either moving or if it is stopped at a point where the x-rays are being blocked.  A good way to ensure this is to index the chopper motor to start chopper motion at an orientation where the beam is blocked and move in integer rotations of the chopper. 

Optical setup
--------------

A typical high-speed imaging setup is shown below.  The scintillator is mounted to a 30 mm Thorlabs turning mirror cube, which is in turn mounted on an optical rail carriage.  The imaging cube is mounted to an adjustment motor that moves the cube along the rail to allow the camera to be focused.  The camera is fixed to the optical rail; the exact mounting scheme depends on the camera.  The optical system shown here is one that works well for high-speed imaging.  I uses two camera lenses coupled on their filter rings.  It gives a roughly 2x image with a high degree of light capture.

.. image:: img/high_speed_imaging_eg.png
   :width: 640px
   :align: center
   :alt: Typical high-speed imaging optical setup

.. contents:: 
   :local:

