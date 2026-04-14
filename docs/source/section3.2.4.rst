
.. _section3.2.4:

3.2.4 - Get Partition Information
=================================


.. _GP:

Action Option -**GP** (-**GetPartition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves request partition information for specified
partitions or requests if the partition or request indices are provided,
respectively. Without a specified condition, partitions owned by the
specialist who executes this Action are retrieved.

| **dsrqst** -(GP|GetPartition) [:ref:`Mode Options <mode3.2.4>`]
|          [:ref:`-(FN|FieldNames) <FN>` FieldNameString]
|          [:ref:`-(PI|PartitionIndex) <PI>` PartitionIndices]
|          [:ref:`-(RI|RequestIndex) <RI>` RequestIndices]
|          [:ref:`-(DS|Dataset) <DS>` dNNNNNN]
|          [:ref:`-(RS|RequestStatus) <RS>` RequestStatus]
|          [:ref:`-(SN|Specialist) <SN>` Specialists]
|          [:ref:`-(OF|OutputFile) <OF>` OutputFileName]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(CS|CheckStatus) <CS>`
     - check and show more detailed information on partition status
   * - :ref:`-(FO|FormatOutput) <FO>`
     - format the column output with a fixed width for all values of a given field

Use :ref:`Info option <section5>` :ref:`-FN <FN>` (-FieldNames) to specify which partition fields to
retrieve. It defaults to all available fields.

Valid field names of partitions and their corresponding :ref:`Info option <section5>` names:

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
     - :ref:`-(RI|RequestIndex) <RI>`
     - data request index
   * - B
     - :ref:`-(DS|Dataset) <DS>`
     - dataset name/ID, dNNNNNN
   * - A
     - :ref:`-(PS|PartitionStatus) <PS>`
     - request partition status
   * - O
     - :ref:`-(DO|DisplayOrder) <DO>`
     - partition display order for a given request
   * - C
     - :ref:`-(FC|FileCount) <FC>`
     - number of data files in a partition
   * - S
     - :ref:`-(SN|Specialist) <SN>`
     - DECS specialist who owns the request record

Partition information can be retrieved for specified request indices per
option :ref:`-RI <RI>` (-RequestIndex). If no dataset or partition is specified,
partition records owned by the specialist who issues this Action are
retrieved.


.. _3.2.4_e6:

**EXAMPLE 6. To get the partition information for default fields owned by specialist login name 'zji':**

| **dsrqst** :ref:`GP <GP>` :ref:`-SN <SN>` zji

Content of the output:

.. code-block:: none

 PartitionIndex<:>RequestIndex<:>Dataset<:>PartitionStatus<:>DisplayOrder<:>FileCount<:>Specialist<:>
 12<:>61160<:>d277006<:>O<:>1<:>41<:>zji<:>
 ...



| :ref:`Back to Top <section3.2.4>`
| :ref:`Back to Table of Contents <index>`
