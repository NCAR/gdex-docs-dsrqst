
.. _section3.3.4:

3.3.4 - Change Purge Time
=================================


.. _RP:

Action Option -**RP** (-**ResetPurge**) (Aliases: -**ResetPurgeTime**, -**RePublish**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -ResetPurgeTime|-RePublish) changes the purge
date/time for a request so it is purged sooner or later. Without a new
purge date/time, this action simply re-publishes the request file list.

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
     - forces an email to the requester after the file list is republished

Use this action, rather than :ref:`-SR <SR>` (-SetRequest), when changing the purge
date/time also requires updating the purge date/time displayed on the
webpage for the temporarily staged online data files.



| :ref:`Back to Top <section3.3.4>`
| :ref:`Back to Table of Contents <index>`
