
.. _section3.2.5:

3.2.5 - Set Partition Information
=================================


.. _SP:

Action Option -**SP** (-**SetPartition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

adds and modifies request partition information
for a given request. One or multiple records can be processed each time.

| **dsrqst** -(SP|SetPartition) [:ref:`Mode Options <mode3.2.5>`]
|          [:ref:`-(PI|PartitionIndex) <PI>` PartitionIndices]
|          [:ref:`-(RI|RequestIndex) <RI>` RequestIndices]
|          [:ref:`-(DS|Dataset) <DS>` dsnnn.n]
|          [:ref:`-(FC|FileCount) <FC>` FileCount]
|          [:ref:`-(PS|PartitionStatus) <PS>` PartitionStatus]
|          [:ref:`-(DO|Displayrder) <DO>` PartitionDisplayOrder]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.2.5:

:ref:`Mode option <section4>` that can be specified for setting request Action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(MD|MyDataset) <MD>`
     - sets information into RDADB no matter the specialist who runs **dsrqst** owns the dataset or not
   * - :ref:`-(NP|NewPartition) <NP>`
     - adds new partition records into RDADB for given request

Partitions cannot be added again if parttion information of a request exists
already. Specify request index per option :ref:`-RI <RI>` (-RequestIndex) and :ref:`Mode <section4>` option
:ref:`-NP <NP>` (-NewPartition) to add partitions.



| :ref:`Back to Top <section3.2.5>`
| :ref:`Back to Table of Contents <index>`
