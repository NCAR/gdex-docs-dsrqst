
.. _section3.1.1:

3.1.1 - Set Request Control Information
=================================


.. _SC:

Action Option -**SC** (-**SetControl**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

creates and modifies request control information in
GDEXDB for given datasets, groups, and request types. One or multiple records
can be processed each time.

| **dsrqst** -(SC|SetControl) [:ref:`Mode Options <mode3.1.1>`]
|          [:ref:`-(CI|ControlIndex) <CI>` RequestControlIndices]
|           :ref:`-(DS|Dataset) <DS>` dNNNNNN
|          [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|          [:ref:`-(RT|RequestType) <RT>` RequestTypes]
|          [:ref:`-(CM|ControlMode) <CM>` ControlMode]
|          [:ref:`-(VP|ValidPeriod) <VP>`  NumberDaysDataAvailable]
|          [:ref:`-(LM|RequestLimit) <LM>` RequestLimitInGB]
|          [:ref:`-(MP|MaxPeriod) <MP>` MaximumRequestPeriod]
|          [:ref:`-(PL|PartitionLimit) <PL>`  PartitionFileCountLimit]
|          [:ref:`-(PZ|PartitionsiZe) <PZ>`  PartitionDataSizeLimit]
|          [:ref:`-(PF|PartitionFlag) <PF>`  PartitionCommandCallFlag]
|          [:ref:`-(DF|DataFormat) <DF>`  DefaultDataFormat]
|          [:ref:`-(TF|ToFormat) <TF>`  DataOutputFormats]
|          [:ref:`-(AF|ArchiveFormat) <AF>`  DefaultArchiveFormat]
|          [:ref:`-(TA|TArflag) <TA>` TarFlag]
|          [:ref:`-(SN|Specialist) <SN>` DECSSpecialists]
|          [:ref:`-(PC|Command) <PC>`  ProcessCommand]
|          [:ref:`-(MR|MaxRequest) <MR>`  MaxNumberOfOutstandingRequests]
|          [:ref:`-(EO|EmptyOutput) <EO>` EmptyOutputFlag]
|          [:ref:`-(UA|URL) <UA>` URLLinks]
|          [:ref:`-(HN|HostName) <HN>`  HostMachineNames]
|          [:ref:`-(MO|Modules) <MO>`  ModuleList]
|          [:ref:`-(EV|Environments) <EV>`  EnvironmentPairList]
|          [:ref:`-(QS|QsubOptions) <QS>`  PBSBatchOptions]
|          [:ref:`-(EN|EmailNotice) <EN>` EmailNoticeTemplateFile]
|          [:ref:`-(CC|CarbonCopy) <CC>` CarbonCopyEmails]
|          [:ref:`-(DE|Description) <DE>` ControlDescription]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(MD|MyDataset) <MD>`
     - sets information into GDEXDB no matter the specialist who runs **dsrqst** owns the dataset or not
   * - :ref:`-(NC|NewControl) <NC>`
     - sets a new request control record into GDEXDB for given dataset, group index, and request type

If a request control record already exists in GDEXDB for a given request
control index, the record is modified; otherwise, a new record is added if
control index is 0 and :ref:`Mode option <section4>` :ref:`-NC <NC>` (-NewControl) is present. A group
index of 0 means the request control applies to the whole dataset.
Combination of dataset number, group index and request type must be unique
for each request control record.

Partitions divide a large request, involving many files, into smaller
partitions (maximum 64). All partitions may be processed concurrently
if enough compute resources are available. To enable partition functionality
for a request control configuration, DECS specialists need to: 1. in the
customized ProcessCommand specified for the request control, process the
whole request and generate all the file records in table wfrqst without
processing individual data files physically, and instead fill the field
wfrqst.command with one command for subset/format conversion of each
individual file (executed in the later partition process); 2. set either
Partition Limit or Size via :ref:`-PL <PL>` (-PartitionLimit) or :ref:`-PZ <PZ>` (-PartitionSize);
3. optionally set the command call flag via :ref:`-PF <PF>` (-PartitionFlag) to control
how the request control command is called. The partition flag defaults to N,
meaning the request control command is called once in the form
'CustomizedCommand RequestIndex' to generate the wfrqst file records, after
which DSRQST handles partitioning and building individual files. Set the
flag to P for DSRQST to call the command again for each partition process in
the form 'CustomizedCommand RequestIndex RequestDirectory PartitionIndex',
making the per-file wfrqst.command optional for flag value P. If the
partition flag is F, the request control command is called finally in the
form 'CustomizedCommand RequestIndex RequestDirectory' after all partitions
are processed successfully. Set the flag to B if both P and F are required.

If a DECS specialist other than the primary dataset owner is set for a
request control record, that specialist takes responsibility for data
requests of the dataset instead of the primary owner.


.. _3.1.1_e1:

**EXAMPLE 1. Set request control information of d540006 via input file 'd540006.ctl':**

| **dsrqst** :ref:`SC <SC>` :ref:`-NC <NC>` :ref:`-IF <IF>` d540006.ctl

Content of input file d540006.ctl:

.. code-block:: none

 ControlIndex<:>Dataset<:>GroupIndex<:>RequestType<:>ControlMode<:>Specialist<:>
 0<:>d540006<:>0<:>M<:>S<:>zji<:>



| :ref:`Back to Top <section3.1.1>`
| :ref:`Back to Table of Contents <index>`
