===============
Data Management
===============

.. warning::

   **2026-08-14 — tomodata2 disk-array failure:** the ``/data2`` mount was
   totally lost. Any ``/data2/7-BM`` content that had **not** yet been
   mirrored to DM is permanently gone. ``/data3/7-BM`` was unaffected.
   The "Lost to 2026-08-14 tomodata2 failure" section below lists the 7-BM
   items that were not on DM at the time.

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
   * - ``2025-10-Kastengren-000000``
     - 134 G
     - /data3/7-BM/2025-10-Kastengren-000000
     - /gdata/dm/7BM/2025-10/2025-10-Kastengren-000000/data/
   * - ``2025-10-Liu-0000000`` (raw + rec)
     - 1.75 T
     - /data3/7-BM/2025-10-Liu-0000000{,_rec}
     - /gdata/dm/7BM/2025-10/2025-10-Liu-0000000/data/  *(mixed)*
   * - ``BeamMotion`` → ``2025-11-Kastengren-0``
     - 2.0 T
     - /data3/7-BM/BeamMotion
     - /gdata/dm/7BM/2025-11/2025-11-Kastengren-0/data/
   * - ``2026-02-Kastengren-000000`` (raw + rec)
     - 5.9 T
     - /data3/7-BM/2026-02-Kastengren-000000{,_rec}
     - /gdata/dm/7BM/2026-02/2026-02-Kastengren-000000/data/  *(mixed)*
   * - ``2026-02-Pathak-1018638``
     - 7.5 T
     - /data3/7-BM/2026-02-Pathak-1018638
     - /gdata/dm/7BM/2026-02/2026-02-Pathak-1018638/data/
   * - ``2026-02-Zhang-1017934``
     - 5.7 T
     - /data3/7-BM/2026-02-Zhang-1017934
     - /gdata/dm/7BM/2026-02/2026-02-Zhang-1017934/data/
   * - ``2026-04-Morris-1011300`` (raw + rec)
     - 44 G
     - /data2/7-BM/2026-04-Morris-1011300{,/_rec}
     - /gdata/dm/7BM/2026-04/2026-04-Morris-1011300/data/  *(mixed)*
   * - ``2026-08-Allen-1010550`` (raw + rec)
     - 5.7 T
     - /data2/7-BM/2026-08-Allen-1010550{,_rec}
     - /gdata/dm/7BM/2026-08/2026-08-Allen-1010550/{data,analysis}/
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
   * - ``/data3/7-BM/2025-11-Kastengren-000000``
     - 907 G
     - **not on DM**
     - upload to DM (needs DM experiment first)
     - —
   * - ``/data3/7-BM/test_tomocupy``
     - 125 G
     - undated, no DM lookup
     - assess necessity
     - —

Lost to 2026-08-14 tomodata2 failure
====================================

The following ``/data2/7-BM`` content had NOT been mirrored to DM at the time of
the disk-array failure and is permanently unrecoverable:

.. list-table::
   :header-rows: 1
   :widths: auto

   * - Dataset / Path
     - Size
     - Notes
   * - ``/data2/7-BM/2026-02-Kastengren-000000``
     - 53 G
     - dev workspace (Jerling helical h5 + notebooks); never on DM
   * - ``/data2/7-BM/2026-04-Liu-0000000``
     - 2.0 T
     - no DM folder ever existed
   * - ``/data2/7-BM/2026-06-Kastengren-000000`` + ``_rec``
     - 280 G + 228 G
     - 5 raw files + entire rec were unbacked
   * - ``/data2/7-BM/2026-06-Varga-1016693``
     - 767 G
     - no DM folder
   * - ``/data2/7-BM/2026-07-Liu-1021361`` + ``_rec`` (small variant)
     - 63 G (16 + 47)
     - no DM folder (distinct from the archived 2026-06-Liu-1021361)

Total lost on /data2/7-BM: ~3.4 T. Notify Alan Kastengren, Liu (7-BM), Varga.
