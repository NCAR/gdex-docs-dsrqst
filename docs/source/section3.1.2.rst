
.. _section3.1.2:

3.1.2 - Get Request Control Information
=================================


.. _GC:

Action Option -**GC** (-**GetControl**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves request control information for the given
datasets, groups, or request types. If specialist login names are provided,
records owned by those specialists are retrieved. If no condition is
given, the records owned by the specialist running **dsrqst** are retrieved.

| **dsrqst** -(GC|GetControl) [:ref:`Mode Options <mode3.1.2>`]
|          [:ref:`-(FN|FieldNames) <FN>` FieldNameString]
|          [:ref:`-(CI|ControlIndex) <CI>` controlIndices]
|          [:ref:`-(DS|Dataset) <DS>` dNNNNNN]
|          [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|          [:ref:`-(RT|RequestType) <RT>` RequestTypes]
|          [:ref:`-(CM|ControlMode) <CM>` ControlMode]
|          [:ref:`-(SN|Specialist) <SN>` DECSSpecialists]
|          [:ref:`-(PC|Command) <PC>`  ProcessCommand]
|          [:ref:`-(EO|EmptyOutput) <EO>` EmptyOutputFlag]
|          [:ref:`-(UA|URL) <UA>` URLLinks]
|          [:ref:`-(HN|HostName) <HN>`  HostMachineNames]
|          [:ref:`-(OF|OutputFile) <OF>` OutputFileName]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode option:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(FO|FormatOutput) <FO>`
     - format the column output with a fixed width for all values of a given field

Use :ref:`Info option <section5>` :ref:`-FN <FN>` (-FieldNames) to choose which request control fields
to retrieve. If :ref:`-FN <FN>` is not provided, it defaults to 'CTIRWGSPOUH'. Use
:ref:`-FN <FN>` ALL to retrieve every available field.

Valid request control field names and their corresponding :ref:`Info <section5>` option
names:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - C
     - :ref:`-(CI|ControlIndex) <CI>`
     - request control index
   * - T
     - :ref:`-(DS|Dataset) <DS>`
     - Dataset number/ID
   * - I
     - :ref:`-(GI|GroupIndex) <GI>`
     - group index
   * - R
     - :ref:`-(RT|RequestType) <RT>`
     - S - subset, F - format conversion, D - CDP
   * - W
     - :ref:`-(CM|ControlMode) <CM>`
     - S - specialist controlled, A - automated
   * - V
     - :ref:`-(VP|ValidPeriod) <VP>`
     - number of days the data are available
   * - J
     - :ref:`-(LM|RequestLimit) <LM>`
     - upper request limit (GB) of data to be requested each time
   * - K
     - :ref:`-(MP|MaxPeriod) <MP>`
     - maximum default request period
   * - L
     - :ref:`-(PL|PartitionLimit) <PL>`
     - upper limit of file count in each partition
   * - Z
     - :ref:`-(PZ|PartitionSize) <PZ>`
     - upper limit of data size in each partition
   * - F
     - :ref:`-(PF|PartitionFlag) <PF>`
     - partition command call flag, N, P, F and B
   * - D
     - :ref:`-(DF|DataFormat) <DF>`
     - default data format for the output data
   * - A
     - :ref:`-(AF|ArchiveFormat) <AF>`
     - default archive format for the output data
   * - X
     - :ref:`-(TF|ToFormat) <TF>`
     - to format for data output; GRIB:NETCDF
   * - G
     - :ref:`-(TA|TArflag) <TA>`
     - Y to tar small request files
   * - S
     - :ref:`-(SN|Specialist) <SN>`
     - DECS specialist who controls the requests
   * - P
     - :ref:`-(PC|Command) <PC>`
     - processing command provided by specialist
   * - N
     - :ref:`-(MR|MaxRequest) <MR>`
     - max number of outstanding requests allowed
   * - O
     - :ref:`-(EO|EmptyOutput) <EO>`
     - Y - sends email to user for empty output, default is N
   * - U
     - :ref:`-(UA|URL) <UA>`
     - specified URL links for the requests
   * - H
     - :ref:`-(HN|HostName) <HN>`
     - machines on which requests should or should not be processed
   * - M
     - :ref:`-(MO|Modules) <MO>`
     - include modules to load to batch job script
   * - B
     - :ref:`-(EV|Environments) <EV>`
     - environment variables to load in batch job script
   * - Q
     - :ref:`-(QS|QsubOptions) <QS>`
     - additional PBS batch options for qsub
   * - E
     - :ref:`-(EN|EmailNotice) <EN>`
     - email notice template file, instead of the default one
   * - Y
     - :ref:`-(CC|CarbonCopy) <CC>`
     - Carbon copy emails; S - specialist only

Request control information can be retrieved for specified datasets via
option :ref:`-DS <DS>` (-Dataset), with optional additional conditions. :ref:`Info <section5>` option
:ref:`-DS <DS>` accepts the wildcard '%' to match any number of characters.

If no dataset number is given, only the request control records owned by
the specialist running this action are returned. To view records owned by
another specialist, specify :ref:`Info option <section5>` :ref:`-SN <SN>` (-Specialist) for that
specialist. To view all request control records, supply :ref:`-SN <SN>` with the value
'ALL'.


.. _3.1.2_e2:

**EXAMPLE 2. To get every field of every request control under your control:**

| **dsrqst** :ref:`GC <GC>` :ref:`-FN <FN>` ALL



| :ref:`Back to Top <section3.1.2>`
| :ref:`Back to Table of Contents <index>`
