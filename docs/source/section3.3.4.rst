
.. _section3.3.4:

3.3.4 - Change Purge Time
=================================


.. _RP:

Action Option -**RP** (-**ResetPurge**) (Aliases: -**ResetPurgeTime**, -**RePublish**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

changes the purging
date/time for a request to purge it either sooner or later. Without providing
new purge date/time, the action simply re-publishes the request filelist.

| **dsrqst** -(RP|ResetPurge) [:ref:`Mode Option <mode3.3.4>`]
|           :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|          [:ref:`-(RN|RequestName) <RN>` RequestNames]
|          [:ref:`-(DP|DatePurge) <DP>` DateDuePurge]
|          [:ref:`-(TP|TimePurge) <TP>` TimeDuePurge]
|          [:ref:`-(LN|LoginName) <LN>` SpecialistLoginName]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(GZ|GMTZone) <GZ>`
     - uses GMT dates/times as controlling times
   * - :ref:`-(WE|WithEmail) <WE>`
     - forces sending email to requester after the filelist is republished

Use this action, rather than :ref:`-SR <SR>` (-SetRequest), to change the purge date/time
when the purge date/time shown on the web page for temporarily staged online
data files also needs to be updated.



| :ref:`Back to Top <section3.3.4>`
| :ref:`Back to Table of Contents <index>`
