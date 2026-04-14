
.. _section3.3.9:

3.3.9 - Restore Purged Requests
=================================


.. _RR:

Action Option -**RR** (-**RestoreRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

restores one or multiple purged requests so they can
be reprocessed.

dsrqst  :ref:`-(RR|RestoreRequest) <RR>`
:ref:`-(RI|RequestIndex) <RI>` RequestIndices
[:ref:`-(RS|RequestStatus) <RS>` RequestStatus]
[:ref:`-(DB|Debug) <DB>` DebugModeInfo]

The restored request records are set to status 'W' (Wait) by default, and
can be set to another value, such as 'Q' (Queue), if provided on the command
line.



| :ref:`Back to Top <section3.3.9>`
| :ref:`Back to Table of Contents <index>`
