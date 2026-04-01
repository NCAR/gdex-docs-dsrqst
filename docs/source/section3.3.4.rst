
.. _section3.3.4:

3.3.4 - Change Purge Time
=================================


.. _RP:

Action Option -**RP** (-**ResetPurge**) (Aliases: -**ResetPurgeTime**, -**RePublish**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

an action to change purging
date/time for a request to purge it either sooner or later. Without providing new
purge date/time, the action simply re-publishes the request filelist.

| **dsrqst** -(RP|ResetPurge) [:ref:`Mode Option <mode3.3.4>`]
|           :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|          [:ref:`-(RN|RequestName) <RN>` RequestNames]
|          [:ref:`-(DP|DatePurge) <DP>` DateDuePurge]
|          [:ref:`-(TP|TimePurge) <TP>` TimeDuePurge]
|          [-(:ref:`LN <LN>`|LoginName SpecialistLoginName)
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.3.4:

:ref:`Mode option <section4>` that can be specified for purging request Action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(GZ|GMTZone) <GZ>`
     - uses GMT dates/times as controlling times
   * - :ref:`-(WE|WithEmail) <WE>`
     - forces to send email to requester after the filelist being republished

Use this action, rather than :ref:`-SR <SR>` (-SetRequest), to change the purge date/time
when the purge date/time shown on web page for the data files staged
temporarily online need to be modified too.



| :ref:`Back to Top <section3.3.4>`
| :ref:`Back to Table of Contents <index>`
