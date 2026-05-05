
.. _section3.3.6:

3.3.6 - Unlock Request Information
=================================


.. _UL:

Action Option -**UL** (-**UnLock**) (Aliases: -**UnLockRequest**, -**UnLockParition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -UnLock) unlocks requests whose build
processes aborted abnormally. The process ID and host name are saved in a
request record while the request is being processed. If the build process
aborts abnormally, the PID and host name are not cleared. Use this action
to clear that information so the request can be rebuilt on a different
host.

| **dsrqst** -(UL|UnLockRequest)
|            :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

A request index is mandatory.



| :ref:`Back to Top <section3.3.6>`
| :ref:`Back to Table of Contents <index>`
