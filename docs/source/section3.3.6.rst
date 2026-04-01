
.. _section3.3.6:

3.3.6 - Unlock Request Information
=================================


.. _UL:

Action Option -**UL** (-**UnLock**) (Aliases: -**UnLockRequest**, -**UnLockParition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

unlocks requests whose building
processes aborted abnormally. Process ID and computer hostname are saved in a
request record temporarily when the request is under process. If the building
process aborts abnormally, the PID and hostname are not cleaned. Use this action
to clean up the PID information to allow the request to be rebuilt on a different
host.

| **dsrqst** -(UL|UnLockRequest)
|            :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

It is mandatory to provide a request index to remove the lock on it.



| :ref:`Back to Top <section3.3.6>`
| :ref:`Back to Table of Contents <index>`
