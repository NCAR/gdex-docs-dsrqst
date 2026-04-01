
.. _section3.3.9:

3.3.9 - Restore Purged Requests
=================================


.. _RR:

Action Option -**RR** (-**RestoreRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

restores one or multiple requests that are purged already
for them to be reprocessed.

dsrqst  :ref:`-(RR|RestoreRequest) <RR>`
:ref:`-(RI|RequestIndex) <RI>` RequestIndices
[:ref:`-(RS|RequestStatus) <RS>` RequestStatus]
[:ref:`-(DB|Debug) <DB>` DebugModeInfo]

The request status of the restored request records is set to 'W' for Wait as
default, and it can be set to an other value, such as 'Q' for Queue, if provided
on the command line.



| :ref:`Back to Top <section3.3.9>`
| :ref:`Back to Table of Contents <index>`
