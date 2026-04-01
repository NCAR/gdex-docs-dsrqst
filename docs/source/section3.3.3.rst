
.. _section3.3.3:

3.3.3 - Purge Individual Requests
=================================


.. _PR:

Action Option -**PR** (-**PurgeRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

an action to purge one or multiple requests by removing
the temporarily staged online data, if not shared by other requests,
associated to the requests; delete request records and their data file
records; and record the request and data usage information for special order
metrics.

| **dsrqst** -(PR|PurgeRequest) [:ref:`Mode Options <mode3.3.3>`]
|           :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|          [:ref:`-(RN|RequestName) <RN>` RequestNames]
|          [:ref:`-(BP|BatchProcess) <BP>` [BatchProcessHosts]]
|          [:ref:`-(LN|LoginName) <LN>` SpecialistLoginName]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.3.3:

:ref:`Mode options <section4>` that can be specified for this action include:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(AW|AnyWhere) <AW>`
     - works with :ref:`Info option <section5>` :ref:`-BP <BP>` (-BatchProcess) to allow the recorded "dsrqst' command be started anywhere.
   * - :ref:`-(BG|BackGround) <BG>`
     - background process to turn off screen display for both standard outputs and errors
   * - :ref:`-(FP|ForcePurge) <FP>`
     - it must be present for this action to purge a request with data online but not due to be purged yet

A request must be in status of either "P" (Ready for Purge) or "O" (Data
Online) with due purging time when it can be purged. For requests with status
"O" but not due yet, :ref:`Mode option <section4>` :ref:`-FP <FP>` (-ForcePurge) must be present for them
to be purged. To purge a request, DSS specialist must also be the owner of the
request.

In case a specialist tries to purge a request owned by another specialist, use
:ref:`Info option <section5>` :ref:`-LN <LN>` (-LoginName) to provide that specialist login name.



| :ref:`Back to Top <section3.3.3>`
| :ref:`Back to Table of Contents <index>`
