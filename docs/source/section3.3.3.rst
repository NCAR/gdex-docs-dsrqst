
.. _section3.3.3:

3.3.3 - Purge Individual Requests
=================================


.. _PR:

Action Option -**PR** (-**PurgeRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

purges one or more requests by removing the
temporarily staged online data (when not shared by other requests),
deleting the request and data file records, and recording request and data
usage information for special order metrics.

| **dsrqst** -(PR|PurgeRequest) [:ref:`Mode Options <mode3.3.3>`]
|           :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|          [:ref:`-(RN|RequestName) <RN>` RequestNames]
|          [:ref:`-(BP|BatchProcess) <BP>` [BatchProcessHosts]]
|          [:ref:`-(LN|LoginName) <LN>` SpecialistLoginName]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(AW|AnyWhere) <AW>`
     - works with :ref:`Info option <section5>` :ref:`-BP <BP>` (-BatchProcess) to allow the recorded **dsrqst** command to be started anywhere
   * - :ref:`-(BG|BackGround) <BG>`
     - background process; turns off screen display for both standard output and standard error
   * - :ref:`-(FP|ForcePurge) <FP>`
     - required to purge a request whose data are online but not yet due

A request must be in status 'P' (Ready for Purge), or 'O' (Data Online)
with a due purge time, before it can be purged. For requests in status 'O'
that are not yet due, :ref:`Mode option <section4>` :ref:`-FP <FP>` (-ForcePurge) must be present. The
DECS specialist running the action must own the request.

To purge a request owned by another specialist, use :ref:`Info option <section5>` :ref:`-LN <LN>`
(-LoginName) to provide that specialist's login name.



| :ref:`Back to Top <section3.3.3>`
| :ref:`Back to Table of Contents <index>`
