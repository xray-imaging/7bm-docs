===============
Data Management
===============

This page summarizes the DM (APS Data Management) status for 7-BM datasets.

Convention: **Done** means the dataset was permanently moved from ``/data2/7-BM`` or
``/data3/7-BM`` to ``/gdata/dm/7BM`` and the original copies were deleted.
**Pending** means the dataset still lives on one of the local disks and has not yet
been fully archived / deletion authorization is not yet given.

.. contents:: On this page
   :local:
   :depth: 2


Done — permanently on DM
========================

.. list-table::
   :header-rows: 1
   :widths: auto

   * - Dataset
     - Size
     - Removed from
     - DM location
   * - ``2026-04-Morris-1011300`` (raw + rec)
     - 44 G
     - /data2/7-BM/2026-04-Morris-1011300{,/_rec}
     - /gdata/dm/7BM/2026-04/2026-04-Morris-1011300/data/  *(mixed)*
   * - ``2026-06-Boyanov-1009244`` (raw only, no rec)
     - 3.9 T
     - /data2/7-BM/2026-06-Boyanov-1009244
     - /gdata/dm/7BM/2026-06/2026-06-Boyanov-1009244/data/
   * - ``2026-06-Liu-1021361`` (raw + rec)
     - 5.5 T
     - /data2/7-BM/2026-06-Liu-1021361{,_rec}
     - /gdata/dm/7BM/2026-06/2026-06-Liu-1021361/{data,analysis}/
   * - ``2026-07-Jin-1018828`` (raw + rec)
     - 1.5 T
     - /data2/7-BM/2026-07-Jin-1018828{,_rec}
     - /gdata/dm/7BM/2026-07/2026-07-Jin-1018828/data/  *(mixed)*
   * - ``2026-07-Li-1020257`` (raw + rec)
     - 2.4 T
     - /data2/7-BM/2026-07-Li-1020257{,_rec}
     - /gdata/dm/7BM/2026-07/2026-07-Li-1020257/data/  *(mixed)*
   * - ``2026-07-Meng-1015468`` (raw + rec)
     - 8.7 T
     - /data2/7-BM/2026-07-Meng-1015468{,_rec}
     - /gdata/dm/7BM/2026-07/2026-07-Meng-1015468/data/  *(mixed)*
   * - ``2026-07-Pathak-1019957`` (raw + rec)
     - 8.3 T
     - /data2/7-BM/2026-07-Pathak-1019957{,_rec}
     - /gdata/dm/7BM/2026-07/2026-07-Pathak-1019957/{data,analysis}/
   * - ``2026-07-Smertenko-1011414`` (raw + rec)
     - 15.9 T
     - /data2/7-BM/2026-07-Smertenko-1011414{,_rec}
     - /gdata/dm/7BM/2026-07/2026-07-Smertenko-1011414/{data,analysis}/


Pending — still on local disk, not fully archived
=================================================

.. note::

   Rows with an **approve →** link are already verified on DM and ready to
   delete. Click the link to send a pre-filled approval email to Francesco
   De Carlo (decarlo@anl.gov). If your browser has no email client
   configured, copy the path/size info from the row and send it via Slack
   or any other channel instead. The dataset will be moved to DM once
   approval is received.

.. list-table::
   :header-rows: 1
   :widths: auto

   * - Dataset / Path
     - Size
     - DM status
     - Action needed
     - Confirm to move
   * - ``/data2/7-BM/2026-08-Allen-1010550`` + ``_rec``
     - 5.7 T
     - fully on DM (1 disposable 42 MB scratch tiff differs)
     - safe to ``rm -rf``; awaiting user confirmation
     - `approve → <mailto:decarlo@anl.gov?subject=DM%20delete%20approval%3A%20%2Fdata2%2F7-BM%2F2026-08-Allen-1010550&body=I%20approve%20deletion%20of%20%2Fdata2%2F7-BM%2F2026-08-Allen-1010550%20and%20_rec%20(5.7%20T%2C%20fully%20on%20DM%20except%20a%20single%2042%20MB%20scratch%20tiff).>`__
   * - ``/data2/7-BM/2026-02-Kastengren-000000``
     - 53 G
     - not on DM — dev workspace (notebooks + Jerling helical h5)
     - decide if archival worthwhile
     - —
   * - ``/data2/7-BM/2026-04-Liu-0000000``
     - 2.0 T
     - no DM folder at all
     - upload to DM before delete
     - —
   * - ``/data2/7-BM/2026-06-Kastengren-000000`` + ``_rec``
     - 280 G + 228 G
     - not on DM (5 raw files + entire rec unbacked)
     - upload to DM
     - —
   * - ``/data2/7-BM/2026-06-Varga-1016693``
     - 767 G
     - no DM folder at all
     - upload to DM
     - —
   * - ``/data2/7-BM/2026-07-Liu-1021361`` + ``_rec`` (small)
     - 63 G (16 + 47)
     - no DM folder at all (distinct from 2026-06-Liu)
     - upload to DM
     - —
   * - ``/data3/7-BM/2026-02-Kastengren-000000`` + ``_rec``
     - 5.9 T
     - fully on DM (mixed under /data)
     - awaiting Alan approval to ``rm``
     - `approve → <mailto:decarlo@anl.gov?subject=DM%20delete%20approval%3A%20%2Fdata3%2F7-BM%2F2026-02-Kastengren-000000&body=I%20approve%20deletion%20of%20%2Fdata3%2F7-BM%2F2026-02-Kastengren-000000%20and%20_rec%20(5.9%20T%2C%20fully%20on%20DM%20mixed%20layout).>`__
   * - ``/data3/7-BM/2026-02-Pathak-1018638``
     - 7.5 T
     - fully on DM
     - awaiting Alan approval to ``rm``
     - `approve → <mailto:decarlo@anl.gov?subject=DM%20delete%20approval%3A%20%2Fdata3%2F7-BM%2F2026-02-Pathak-1018638&body=I%20approve%20deletion%20of%20%2Fdata3%2F7-BM%2F2026-02-Pathak-1018638%20(7.5%20T%2C%20fully%20on%20DM).>`__
   * - ``/data3/7-BM/2026-02-Zhang-1017934``
     - 5.7 T
     - fully on DM
     - awaiting Alan approval to ``rm``
     - `approve → <mailto:decarlo@anl.gov?subject=DM%20delete%20approval%3A%20%2Fdata3%2F7-BM%2F2026-02-Zhang-1017934&body=I%20approve%20deletion%20of%20%2Fdata3%2F7-BM%2F2026-02-Zhang-1017934%20(5.7%20T%2C%20fully%20on%20DM).>`__
   * - ``/data3/7-BM/2025-10-Kastengren-000000``
     - 134 G
     - on DM (loses 2 KB ``tomocupy.conf``)
     - awaiting Alan approval to ``rm``
     - `approve → <mailto:decarlo@anl.gov?subject=DM%20delete%20approval%3A%20%2Fdata3%2F7-BM%2F2025-10-Kastengren-000000&body=I%20approve%20deletion%20of%20%2Fdata3%2F7-BM%2F2025-10-Kastengren-000000%20(134%20G%2C%20on%20DM%20except%20a%202%20KB%20tomocupy.conf).>`__
   * - ``/data3/7-BM/2025-10-Liu-0000000`` + ``_rec``
     - 1.75 T
     - fully on DM (mixed under /data)
     - awaiting Alan approval to ``rm``
     - `approve → <mailto:decarlo@anl.gov?subject=DM%20delete%20approval%3A%20%2Fdata3%2F7-BM%2F2025-10-Liu-0000000&body=I%20approve%20deletion%20of%20%2Fdata3%2F7-BM%2F2025-10-Liu-0000000%20and%20_rec%20(1.75%20T%2C%20fully%20on%20DM).>`__
   * - ``/data3/7-BM/2025-11-Kastengren-000000``
     - 907 G
     - **not on DM**
     - upload to DM (needs DM experiment first)
     - —
   * - ``/data3/7-BM/BeamMotion``
     - 2.0 T
     - fully on DM as ``2025-11-Kastengren-0/data/`` (create-manual)
     - awaiting Alan approval to ``rm``
     - `approve → <mailto:decarlo@anl.gov?subject=DM%20delete%20approval%3A%20%2Fdata3%2F7-BM%2FBeamMotion&body=I%20approve%20deletion%20of%20%2Fdata3%2F7-BM%2FBeamMotion%20(2.0%20T%2C%20fully%20on%20DM%20as%202025-11-Kastengren-0%2Fdata%2F).>`__
   * - ``/data3/7-BM/test_tomocupy``
     - 125 G
     - undated, no DM lookup
     - assess necessity
     - —
