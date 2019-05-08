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
+          +---------------+-------------------------------------+----------------------------------------+------+
|          | 17.3R3.9      | show system snapshot                | request system snapshot recovery       |  N   |
+----------+---------------+-------------------------------------+----------------------------------------+------+
| EX2200   | 15.1R5.5      | show system snapshot media internal | request system snapshot media internal |  O   |
+----------+---------------+-------------------------------------+----------------------------------------+------+
| EX2300   | 15.1X53-D57.3 | show system snapshot media internal | request system snapshot media internal |  N   |
+----------+---------------+-------------------------------------+----------------------------------------+------+
| EX3400   | 15.1X53-D58.3 | show system snapshot                | request system snapshot                |  N   |
+----------+---------------+-------------------------------------+----------------------------------------+------+
| EX4300   | 13.2X51-D26.2 | show system snapshot media internal | request system snapshot media internal |  O   |
+----------+---------------+-------------------------------------+----------------------------------------+------+
| QFX5100  | 14.1X53-D42.3 | show system snapshot                | request system snapshot                |  O   |
+----------+---------------+-------------------------------------+----------------------------------------+------+
| QFX5200  | 15.1X53-D233.1| show system snapshot                | request system snapshot recovery       |  N   +
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


We can distinguish between two flavours of display formats, which we'll call
"new format" noticed often on newer Junos distributions, and "old format"
usually returned by older Junos distributions.

Old format (O)
~~~~~~~~~~~~~~

Sample output from the show command:

.. code-block:: text

    Doing the initial labeling...
    Information for snapshot on internal (da1s1)
    Creation date: Aug 8 09:58:12 2017
    JUNOS version on snapshot:
      jbase  : ppc-15.1R6.7
      jcrypto: ppc-15.1R6.7
      jdocs  : 15.1R6.7
      jkernel: ppc-15.1R6.7
      jmacsec: 15.1R6.7
      jpfe   : MX80-15.1R6.7
      jroute : ppc-15.1R6.7
      jweb   : ppc-15.1R6.7

New format (N)
~~~~~~~~~~~~~~

Sample output from the show command:

.. code-block:: text

    Recovery Snapshots:
    Snapshots available on the OAM volume:
    recovery.ufs
    Date created: Wed Aug 15 10:50:42 UTC 2018
    Junos version: 15.1X53-D66.8

    Total recovery snapshots: 1

Of course, generally, this format is only delivered as text even though you'd
like to get an XML document, e.g.,


.. code-block:: bash

    mircea@router> show system snapshot | display xml
    <rpc-reply xmlns:junos="http://xml.juniper.net/junos/17.3R3/junos">
        <output>
            Recovery Snapshots:
            Snapshots available on the OAM volume:
            recovery.ufs
            Date created: Wed Aug 15 10:50:42 UTC 2018
            Junos version: 15.1X53-D66.8

            Total recovery snapshots: 1
        </output>
        <cli>
            <banner>{master}</banner>
        </cli>
    </rpc-reply>

Thank you, Juniper!
