
.. _section3.2.11:

3.2.11 - Email Request Status
=================================


.. _ER:

Action Option -**ER** (-**EmailRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sends an email to the specialist who executes **dsrqst** for the
current status of a list of requests.

| **dsrqst** -(ER|EmailRequest)
|          [:ref:`-(RI|RequestIndex) <RI>` RequestIndices]
|          [:ref:`-(RN|RequestName) <RN>` RequestNames]
|          [:ref:`-(DS|Dataset) <DS>` dsnnn.n]
|          [:ref:`-(EM|Email) <EM>` UserEmailAddresses]
|          [:ref:`-(RT|ReuqestType) <RT>` RequestTypes]
|          [:ref:`-(RS|RequestStatus) <RS>` RequestStatus]
|          [:ref:`-(DQ|DateReuqest) <DQ>` DateRequestSubmit]
|          [:ref:`-(DR|DateReady) <DR>`   DateRequestProcess]
|          [:ref:`-(DP|DatePurge) <DP>` DateRequestPurge]
|          [:ref:`-(DF|DataFormat) <DF>`  DefaultDataFormat]
|          [:ref:`-(AF|ArchiveFormat) <AF>`  DefaultArchiveFormat]
|          [:ref:`-(SN|Specialist) <SN>` Specialists]
|          [:ref:`-(EL|EmailLimit) <EL>` MaximumChecks]
|          [:ref:`-(CC|CarbonCopy) <CC>` Cc'dEmailAddresses]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

As default, status of up to 20 requests are included in an email. To include
more requests you change the limit via :ref:`Info option <section5>` :ref:`-EL <EL>` (-EmailLimit).



| :ref:`Back to Top <section3.2.11>`
| :ref:`Back to Table of Contents <index>`
