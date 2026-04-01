
.. _section3.2.4:

3.2.4 - Get Partition Information
=================================


.. _GP:

Action Option -**GP** (-**GetPartition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves request partition information for specified
partitions or requests if the partition or request indices are provided,
respectively. Without specified condition, the information of partitions,
owned by the current specialist who execute this  Action of **dsrqst**, are
retrieved.

| **dsrqst** -(GP|GetPartition) [:ref:`Mode Options <mode3.2.4>`]
|          [:ref:`-(FN|FieldNames) <FN>` FieldNameString]
|          [:ref:`-(PI|PartititonIndex) <PI>` PartitionIndices]
|          [:ref:`-(RI|RequestIndex) <RI>` RequestIndices]
|          [:ref:`-(DS|Dataset) <DS>` dsnnn.n]
|          [:ref:`-(RS|RequestStatus) <RS>` RequestStatus]
|          [:ref:`-(SN|Specialist) <SN>` Specialists]
|          [:ref:`-(OF|OutputFile) <OF>` OutputFileName]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.2.4:

:ref:`Mode options <section4>` that can be specified for getting partition Action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(CS|CheckStatus) <CS>`
     - check and show more detailed information on partition status
   * - :ref:`-(FO|FormatOutput) <FO>`
     - format the column output with a fix width for all values of a given field

Use :ref:`Info option <section5>` :ref:`-FN <FN>` (-FieldNames) to specify what partition fields to be
retrieved. It defaults all available fields.

Valid field names of requests and their corresponding :ref:`Info option <section5>` names:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - P
     - :ref:`-(PI|PartitionIndex) <PI>`
     - request partition index
   * - R
     - :ref:`-(RI|ReuqstIndex) <RI>`
     - data request index
   * - B
     - :ref:`-(DS|Dataset) <DS>`
     - dataset name/ID, dsnnn.n
   * - A
     - :ref:`-(PS|PartitonStatus) <PS>`
     - request partition status
   * - O
     - :ref:`-(DO|DisplayOrder) <DO>`
     - partition display order for a given request
   * - C
     - :ref:`-(FC|FileCount) <FC>`
     - number of data files in a partition
   * - S
     - :ref:`-(SN|Specialist) <SN>`
     - DSS specialist who owns the request record

Request partition information can be retrieved for specified request indices per
option :ref:`-RI <RI>` (-RequestIndex). If dataset and partition are not specified,
partition records, owned by the specialist who issue getting partition Action
of **dsrqst**, are retrieved.


.. _3.2.4_e6:

**EXAMPLE 6. To get the partition information for default fields and owned by specialist login name 'zji':**

| **dsrqst** :ref:`GP <GP>` :ref:`-SN <SN>` zji

Content of the output:

.. code-block:: none

 PartitionIndex<:>RequestIndex<:>Dataset<:>PartitionStatus<:>DisplayOrder<:>FileCount<:>Specialist<:>
 12<:>61160<:>d277006<:>O<:>1<:>41<:>zji<:>
 ...



| :ref:`Back to Top <section3.2.4>`
| :ref:`Back to Table of Contents <index>`
