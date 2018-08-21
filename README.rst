Junos system snapshot
=====================

This page refers to
`Junos system snapshot <https://www.juniper.net/documentation/en_US/junos/topics/reference/command-summary/request-system-snapshot.html>`_.

Although Junos can sometimes be consistent cross platforms (as physical boxes)
and Junos versions, system snapshot is not one of those features.

+----------+---------------+-------------------------------------+----------------------------------------+------+
| Platform | Junos Version | Show command                        | Request command                        | Note |
+==========+===============+=====================================+========================================+======+
| MX80     | 15.1R6.7      | show system snapshot                | request system snapshot                |  O   |
+----------+---------------+-------------------------------------+----------------------------------------+------+
| MX480    | 15.1F7.3      | show system snapshot                | request system snapshot recovery       |  N   |
+          +---------------+-------------------------------------+----------------------------------------+------+
|          | 14.2R6.5      | show system snapshot                | request system snapshot                |  O   |
+----------+---------------+-------------------------------------+----------------------------------------+------+
| EX2200   | 15.1R5.5      | show system snapshot media internal | request system snapshot media internal |  O   |
+----------+---------------+-------------------------------------+----------------------------------------+------+
| EX2300   | 15.1X53-D57.3 | show system snapshot media internal | request system snapshot media internal |  N   |
+----------+---------------+-------------------------------------+----------------------------------------+------+
| QFX100002| 15.1X53-D65.3 | show system snapshot                | request system snapshot recovery       |  N   |
+          +---------------+-------------------------------------+----------------------------------------+------+
|          | 15.1X53-D66.8 | show system snapshot                | request system snapshot recovery       |  N   |
+          +---------------+-------------------------------------+----------------------------------------+------+
|          | 15.1X53-D61.7 | show system snapshot                | request system snapshot recovery       |  O   |
+----------+---------------+-------------------------------------+----------------------------------------+------+
| QFX100008| 15.1X53-D66.8 | show system snapshot                | request system snapshot recovery       |  N   |
+          +---------------+-------------------------------------+----------------------------------------+------+
|          | 17.3R2-S1.2   | N/A                                 | N/A                                    |  ✝   |
+----------+---------------+-------------------------------------+----------------------------------------+------+

Legend:

N = New output format
O = Old output format
✝ = No longer supported, see https://www.juniper.net/documentation/en_US/junos/topics/reference/command-summary/request-system-snapshot-qfx-series.html for further details.

Display formats
---------------

Here we distinguish between two types of output formats for the show command:

Old format
^^^^^^^^^^


New format
^^^^^^^^^^
