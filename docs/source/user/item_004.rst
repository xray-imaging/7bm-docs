Sample
======

.. contents:: 
   :local:


Mounting
--------

Samples are mounted on a `custom tip <https://anl.app.box.com/folder/123584924093>`_ as shown below:

.. image:: ../img/sample_kinematic.png 
   :width: 140px
   :align: center
   :alt: tomo_user

this is mounted on the rotary stage using a `KBT25 <http://www.thorlabs.com/thorProduct.cfm?partNumber=KBT25/M>`_/`KBB25 <http://www.thorlabs.com/thorProduct.cfm?partNumber=KBB25/M>`_ pair. New `KBT25T kinematic <http://www.thorlabs.com/thorProduct.cfm?partNumber=KBT25T/M>`_ could also be used.

Alignment
---------

| In order to align the sample on the center of rotation of the rotary stage 4 motorized axis are needed:
|
| • **Sample Y** (vertical motion)
| • **Sample X** (horizontal motion perpendicular to the beam)
| • **Sample top X** (horizontal motion above the rotary stage)
| • **Sample top Z** (horizontal motion normal to "sample top X" above the rotary stage)


.. image:: ../img/tomo_refs.png 
   :width: 480px
   :align: center
   :alt: tomo_user

Load the sample on the kinematic mount (if using the automatic alignemt cli `Adjust <https://github.com/xray-imaging/adjust>`_ use the `tungsten sphere <https://www.vxb.com/0-5mm-Tungsten-Carbide-One-0-0197-inch-Dia-p/0-5mmtungstenballs.htm>`_ as sample) then using:

.. image:: ../img/tomo_admin.png 
   :width: 720px
   :align: center
   :alt: tomo_user


move the sample up/down by adjusting Tomo_Sam_Y in the positive/negative direction until the sample is in the field of view of detector. 


Automatic
~~~~~~~~~

`Adjust <https://github.com/xray-imaging/adjust>`_ is a python script that automates all tomography instrument alignemt taks.

`Adjust <https://github.com/xray-imaging/adjust>`_  works in combination with a 0.5 mm `tungsten sphere <https://www.vxb.com/0-5mm-Tungsten-Carbide-One-0-0197-inch-Dia-p/0-5mmtungstenballs.htm>`_ that needs to be installed as a sample on top of the rotary stage making sure is in the field of view at least when the rotation axis is at 0 and 10 degrees.

`Adjust <https://github.com/xray-imaging/adjust>`_'s funtions include automatic finding of:

- detector pixel size
- scintillator focus location
- rotation axis location
- centering of the sample on the rotation axis
- rotation axis pitch and roll

First step is to mesaure the image pixel size by running::

    user2bmb@pg10ge $ adjust resolution

then::

    user2bmb@pg10ge $ adjust focus
    user2bmb@pg10ge $ adjust center
    user2bmb@pg10ge $ adjust roll
    user2bmb@pg10ge $ adjust pitch

Manual 
~~~~~~

To center the sample on the rotation axis move the rotary stage Tomo_Rot at 0\ :sup:`o` then by adjusting the motor called "Tomo@0deg" (which is the sample stage on top of the rotary stage moving in the X director when the rotary stage at 0\ :sup:`o`) move the sample towards the center of the field of view. Finally move the Tomo_Rot at 180\ :sup:`o` then by adjusting the motor called "Tomo@1800deg" (which is the sample stage on top of the rotary stage moving in the X director when the rotary stage at 180\ :sup:`o`) move again the sample towards the center. The same process is described in the 4 steps below:

.. image:: ../img/sample_alignment.png
   :width: 1200px
   :align: center
   :alt: project

| **Note**: "Tomo_Sam_X" is used to align the center of rotation in respect to the beam, not to align samples on the rotation axis. While moving the sample vertically with Tomo_Sam_Y, some parasitic motions might detune "Tomo_Sam_X" by few μm. Therefore, it is expected to realign Tomo_Sam_X from one sample to another but only within few μm range.

