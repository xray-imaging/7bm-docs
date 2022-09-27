============================================
Energy Dispersive Diffraction and Scattering
============================================

Energy dispersive diffraction (EDD) is used either alone or in conjunction with tomography to probe the crystal structure of materials.  The basic idea is simple.  Bragg's Law shows the relationship between  x-ray wavelength, scattering angle, and crystal 2d spacing.  In standard angle-dispersive diffraction, the x-ray energy is fixed by using monochromatic beam, and angle is related to the scattering vector q.

:math:`q = \frac{4 \pi}{\lambda}\sin(\frac{\theta}{2})`

In EDD, the scattering angle is fixed with a set of pinholes or slits.  A polychromatic beam (in practice, filtred white beam) illuminates the sample and an energy dispersive detector (in practice, a Ge detector) records the energy of each photon that is absorbed in the detector.  Using Bragg's Law, the energy can be transformed to scattering vector.  With appropriate corrections for filtering and the incident spectrum, a semi-quantitative measure of diffraction or scattering can be made.  Note that the limited energy resolution of the Ge detector (roughly 1% :math:`\Delta E / E`) limits the achievable resolution.


Optical setup
-----------------------------

The EDD setup consists of two sets of slits mounted on a tube to shield the detector from all x-rays except those from a well-defined gauge volume and at a well-defined angle.  The slits are made of two tungsten carbide blocks 5 mm thick with the edges fabricated by EDM.  The centers of the slits are placed 511 mm apart.  The slit edges are curved to match scattering at a 3 degree full scattering angle with a 150 mm working distance from the sample.  This geometry can work simultaneously with tomography using the Optique Peter optics.  The detector for all such measurements is a Ge detector.

Alignment and Calibration
-------------------------

   * Place the 30 mm Telfon cylinder in the beam.  Scan the EDD setup vertically and horizontally to find the beam.
   * Place a combined W/Mo foil in the beam, using fluorescence from the foils to calibrate the energy scale for detector.  Scan the EDD setup vertically and horizontally to find the beam more precisely.  Note that one may get diffraction from the W and Mo foils as well as fluorescence.  
   * Optionally, use a radioactive check source to calibrate the energy scale of the detector.
   * With the energy scale defined, place a :math:`LaB_6` in the beam.  One will see both La fluorescence and regularly spaced diffraction lines.  Use these data to compute the :math:`2\theta` angle of the EDD setup.
