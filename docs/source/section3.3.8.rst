
.. _section3.3.8:

3.3.8 - Interrupt Partitions
=================================


.. _IP:

Action Option -**IP** (-**InterruptParition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

interrupts request partitions that are currently
queued by changing their status to 'I', for Interrupted, and kills recursively
all the child processes that are running to process the partitions.

| **dsrqst** -(IP|InterruptPartition) [:ref:`Mode Option <mode3.3.8>`]
|            :ref:`-(PI|PartitionIndex) <PI>` PartitionIndices
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.3.8:

:ref:`Mode option <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(FI|ForceInterrupt) <FI>`
     - it must be present for this action to interrupt a partition that is under processing.

It is mandatory to provide a partition index to interrupt it.



| :ref:`Back to Top <section3.3.8>`
| :ref:`Back to Table of Contents <index>`
