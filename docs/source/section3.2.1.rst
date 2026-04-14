
.. _section3.2.1:

3.2.1 - Get Request Information
=================================


.. _GR:

Action Option -**GR** (-**GetRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves data request information for specified requests
if the request indices are provided. Without a specified condition, requests
owned by the specialist who executes this Action are retrieved.

| **dsrqst** -(GR|GetRequest) [:ref:`Mode Options <mode3.2.1>`]
|          [:ref:`-(FN|FieldNames) <FN>` FieldNameString]
|          [:ref:`-(RI|RequestIndex) <RI>` RequestIndices]
|          [:ref:`-(RN|RequestName) <RN>` RequestNames]
|          [:ref:`-(DS|Dataset) <DS>` dNNNNNN]
|          [:ref:`-(EM|Email) <EM>` UserEmailAddresses]
|          [:ref:`-(RT|RequestType) <RT>` RequestTypes]
|          [:ref:`-(RS|RequestStatus) <RS>` RequestStatus]
|          [:ref:`-(TA|TArflag) <TA>` TarFlag]
|          [:ref:`-(DQ|DateRequest) <DQ>` DateRequestSubmit]
|          [:ref:`-(DR|DateReady) <DR>`   DateRequestProcess]
|          [:ref:`-(DP|DatePurge) <DP>` DateRequestPurge]
|          [:ref:`-(DF|DataFormat) <DF>`  DefaultDataFormat]
|          [:ref:`-(AF|ArchiveFormat) <AF>`  DefaultArchiveFormat]
|          [:ref:`-(SN|Specialist) <SN>` Specialists]
|          [:ref:`-(HN|HostName) <HN>`  HostMachineNames]
|          [:ref:`-(OF|OutputFile) <OF>` OutputFileName]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(CS|CheckStatus) <CS>`
     - check and show more detailed information on request status
   * - :ref:`-(FO|FormatOutput) <FO>`
     - format the column output with a fixed width for all values of a given field

Use :ref:`Info option <section5>` :ref:`-FN <FN>` (-FieldNames) to specify which request fields to retrieve.
It defaults to 'REBTIOCJUXAGSH' if :ref:`-FN <FN>` is not provided. Request information
of all available fields is retrieved if :ref:`-FN <FN>` ALL is given.

Valid field names of requests and their corresponding :ref:`Info option <section5>` names:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - R
     - :ref:`-(RI|RequestIndex) <RI>`
     - data request index
   * - Q
     - :ref:`-(RN|RequestName) <RN>`
     - request name/ID
   * - E
     - :ref:`-(EM|Email) <EM>`
     - email of the user who submitted the request
   * - B
     - :ref:`-(DS|Dataset) <DS>`
     - dataset name/ID, dNNNNNN
   * - I
     - :ref:`-(GI|GroupIndex) <GI>`
     - group index defined in table dsgroup
   * - T
     - :ref:`-(RT|RequestType) <RT>`
     - request type; Subset, Format conversion
   * - O
     - :ref:`-(SQ|SizeRequest) <SQ>`
     - size of data files requested
   * - W
     - :ref:`-(SI|SizeInput) <SI>`
     - size of original data files needed
   * - C
     - :ref:`-(FC|FileCount) <FC>`
     - number of data files requested
   * - J
     - :ref:`-(DQ|DateRequest) <DQ>`
     - date request submitted
   * - K
     - :ref:`-(TQ|TimeRequest) <TQ>`
     - time request submitted
   * - U
     - :ref:`-(DR|DateReady) <DR>`
     - date request processed
   * - V
     - :ref:`-(TR|TimeReady) <TR>`
     - time request processed
   * - X
     - :ref:`-(DP|DatePurge) <DP>`
     - date request to be purged
   * - Y
     - :ref:`-(TP|TimePurge) <TP>`
     - time request to be purged
   * - A
     - :ref:`-(RS|RequestStatus) <RS>`
     - request status
   * - G
     - :ref:`-(TA|TArflag) <TA>`
     - Y to tar small request files
   * - P
     - :ref:`-(PO|Priority) <PO>`
     - process priority of a Queued request
   * - N
     - :ref:`-(DF|DataFormat) <DF>`
     - default data format for the output data
   * - M
     - :ref:`-(AF|ArchiveFormat) <AF>`
     - default archive format for the output data
   * - S
     - :ref:`-(SN|Specialist) <SN>`
     - DECS specialist who owns the request record
   * - L
     - :ref:`-(RL|RequestLocation) <RL>`
     - specified path to stage the request result
   * - H
     - :ref:`-(HN|HostName) <HN>`
     - machine name a request can be processed on
   * - Z
     - :ref:`-(EN|EmailNotice) <EN>`
     - email notice file link, instead of default one
   * - D
     - :ref:`-(DE|Description) <DE>`
     - readable request description
   * - F
     - :ref:`-(RF|RequestDesc) <RF>`
     - additional request information

Data request information can be retrieved for specified request indices per
option :ref:`-RI <RI>` (-RequestIndex). :ref:`Info option <section5>` :ref:`-RN <RN>` (-RequestName) can also identify
request indices. Option :ref:`-RN <RN>` accepts wildcard input of '%' for matching any
number of characters.

If no dataset or request is specified, request records owned by the specialist
who issues this Action are retrieved.


.. _3.2.1_e3:

**EXAMPLE 3. To get the request information for default fields owned by specialist login name 'zji':**

| **dsrqst** :ref:`GR <GR>` :ref:`-SN <SN>` zji

Content of the output:

.. code-block:: none

 RequestIndex<:>Email<:>Dataset<:>RequestType<:>SizeRequest<:>FileCount<:>DateRequest<:>DateReady<:>DatePurge<:>RequestStatus<:>Specialist<:>
 42<:>zaihuaji@gmail.com<:>d540006<:>M<:>5917241626<:>69<:>2009-06-15<:><:><:>W<:>zji<:>
 ...



| :ref:`Back to Top <section3.2.1>`
| :ref:`Back to Table of Contents <index>`
