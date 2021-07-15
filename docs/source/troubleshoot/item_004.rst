The sample motors stopped working!
==================================

.. contents:: 
   :local:

The main Aerotech sample stages (X, Y, and for tomography theta) are servo stages.  The servo drivers will disable the motors if they either hit a limit switch or if the motor current limits are exceeded.  This can often happen for the X and theta stages if too much force or torque are applied to the motors.  

To correct this, open the motor debug screens (found on the yellow window with the motor controls).  Near the bottom right corner of this window, there is a control to enable or disable the motor.  Toggle this to disable, then enable.  This often corrects the problem.


.. image:: img/tomo_motor_ctrl.png
   :width: 320px
   :align: center
   :alt: control screen for sample motors

.. image:: img/motor_debug.png
   :width: 320px
   :align: center
   :alt: motor debug screen


