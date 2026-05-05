
.. _section3.1.1:

3.1.1 - Set Request Control Information
=================================


.. _SC:

Action Option -**SC** (-**SetControl**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

creates or modifies request control information in
GDEXDB for given datasets, groups, and request types. One or more records
can be processed per call.

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
     - writes information to GDEXDB regardless of whether the specialist running **dsrqst** owns the dataset
   * - :ref:`-(NC|NewControl) <NC>`
     - adds a new request control record to GDEXDB for the given dataset, group index, and request type

If a request control record already exists in GDEXDB for the given control
index, that record is modified; otherwise, a new record is added when the
control index is 0 and :ref:`Mode option <section4>` :ref:`-NC <NC>` (-NewControl) is present. A group
index of 0 means the request control applies to the whole dataset.
The combination of dataset number, group index, and request type must be
unique for each request control record.

Partitions divide a large request, involving many files, into smaller
pieces (up to 64). All partitions can be processed concurrently if enough
compute resources are available. To enable partition support for a request
control configuration, a DECS specialist must:

.. list-table::
   :widths: auto
   :header-rows: 1
 1. In the customized ProcessCommand specified for the request control, process the whole request and generate all the file records in table wfrqst without physically processing the individual data files; instead, fill the field wfrqst.command with the per-file subset/format-conversion command (executed later in the partition process). 2. Set either the partition limit or the partition size via :ref:`-PL <PL>` (-PartitionLimit) or :ref:`-PZ <PZ>` (-PartitionSize). 3. Optionally set the command call flag via :ref:`-PF <PF>` (-PartitionFlag) to control how the request control command is invoked. The partition flag defaults to N, meaning the request control command is called once in the form 'CustomizedCommand RequestIndex' to generate the wfrqst file records, after which DSRQST handles the partitioning and the per-file builds. Set the flag to P for DSRQST to call the command again for each partition process in the form 'CustomizedCommand RequestIndex RequestDirectory PartitionIndex', which makes the per-file wfrqst.command optional. If the flag is F, the request control command is called one final time in the form 'CustomizedCommand RequestIndex RequestDirectory' after all partitions have completed successfully. Set the flag to B when both P and F are required.

If a DECS specialist other than the primary dataset owner is set in a
request control record, that specialist takes responsibility for the
dataset's data requests instead of the primary owner.


.. _3.1.1_e1:

**EXAMPLE 1. Set the request control information for d540006 from the input file 'd540006.ctl':**

| **dsrqst** :ref:`SC <SC>` :ref:`-NC <NC>` -IF d540006.ctl

Content of input file d540006.ctl:

.. code-block:: none

 ControlIndex<:>Dataset<:>GroupIndex<:>RequestType<:>ControlMode<:>Specialist<:>
 0<:>d540006<:>0<:>M<:>S<:>zji<:>



| :ref:`Back to Top <section3.1.1>`
| :ref:`Back to Table of Contents <index>`
