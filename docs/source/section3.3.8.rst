
.. _section3.3.8:

3.3.8 - Interrupt Partitions
=================================


.. _IP:

Action Option -**IP** (-**InterruptParition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

interrupts request partitions that are currently
queued by changing their status to 'I' (Interrupted) and recursively killing
all child processes running to process the partitions.

| **dsrqst** -(IP|InterruptPartition) [:ref:`Mode Option <mode3.3.8>`]
|            :ref:`-(PI|PartitionIndex) <PI>` PartitionIndices
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode option:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(FI|ForceInterrupt) <FI>`
     - must be present to interrupt a partition that is currently under processing.

A partition index is mandatory.



| :ref:`Back to Top <section3.3.8>`
| :ref:`Back to Table of Contents <index>`
