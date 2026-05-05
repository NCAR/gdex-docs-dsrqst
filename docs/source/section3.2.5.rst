
.. _section3.2.5:

3.2.5 - Set Partition Information
=================================


.. _SP:

Action Option -**SP** (-**SetPartition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

adds or modifies request partition information for a
given request. One or more records can be processed per call.

| **dsrqst** -(SP|SetPartition) [:ref:`Mode Options <mode3.2.5>`]
|          [:ref:`-(PI|PartitionIndex) <PI>` PartitionIndices]
|          [:ref:`-(RI|RequestIndex) <RI>` RequestIndices]
|          [:ref:`-(DS|Dataset) <DS>` dNNNNNN]
|          [:ref:`-(FC|FileCount) <FC>` FileCount]
|          [:ref:`-(PS|PartitionStatus) <PS>` PartitionStatus]
|          [:ref:`-(DO|DisplayOrder) <DO>` PartitionDisplayOrder]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(MD|MyDataset) <MD>`
     - writes information to GDEXDB regardless of whether the specialist running **dsrqst** owns the dataset
   * - :ref:`-(NP|NewPartition) <NP>`
     - adds new partition records to GDEXDB for a given request

Partitions cannot be added again if partition information for the request
already exists. Specify the request index via option :ref:`-RI <RI>` (-RequestIndex)
together with :ref:`Mode option <section4>` :ref:`-NP <NP>` (-NewPartition) to add partitions.



| :ref:`Back to Top <section3.2.5>`
| :ref:`Back to Table of Contents <index>`
