
.. _section3.3.6:

3.3.6 - Unlock Request Information
=================================


.. _UL:

Action Option -**UL** (-**UnLock**) (Aliases: -**UnLockRequest**, -**UnLockParition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

unlocks requests whose building
processes aborted abnormally. Process ID and computer hostname are saved in a
request record while the request is under process. If the building process
aborts abnormally, the PID and hostname are not cleaned. Use this action to
clean up the PID information and allow the request to be rebuilt on a different
host.

| **dsrqst** -(UL|UnLockRequest)
|            :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

A request index is mandatory.



| :ref:`Back to Top <section3.3.6>`
| :ref:`Back to Table of Contents <index>`
