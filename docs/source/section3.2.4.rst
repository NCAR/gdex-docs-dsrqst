
.. _section3.2.4:

3.2.4 - Get Partition Information
=================================


.. _GP:

Action Option -**GP** (-**GetPartition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves request partition information for specified
partitions or requests when partition or request indices are provided. If
no condition is given, the partitions owned by the specialist running this
action are returned.

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

Use :ref:`Info option <section5>` :ref:`-FN <FN>` (-FieldNames) to choose which partition fields to
retrieve. If :ref:`-FN <FN>` is not provided, all available fields are returned.

Valid partition field names and their corresponding :ref:`Info option <section5>` names:

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

Partition information can be retrieved for the request indices given via
option :ref:`-RI <RI>` (-RequestIndex). If no dataset or partition is specified, the
partition records owned by the specialist running this action are
returned.


.. _3.2.4_e6:

**EXAMPLE 6. To get the default-field partition information owned by the specialist with login name 'zji':**

| **dsrqst** :ref:`GP <GP>` :ref:`-SN <SN>` zji

Content of the output:

.. code-block:: none

 PartitionIndex<:>RequestIndex<:>Dataset<:>PartitionStatus<:>DisplayOrder<:>FileCount<:>Specialist<:>
 12<:>61160<:>d277006<:>O<:>1<:>41<:>zji<:>
 ...



| :ref:`Back to Top <section3.2.4>`
| :ref:`Back to Table of Contents <index>`
