
.. _section3.3.7:

3.3.7 - Interrupt Requests
=================================


.. _IR:

Action Option -**IR** (-**InterruptRequest**) (Alias: -**InterRupt**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

interrupts requests that are currently queued by
changing their status to 'I', for Interrupted, and kills recursively all
the child processes that are running to build the requests.

| **dsrqst** -(IR|InterruptRequest) [:ref:`Mode Option <mode3.3.7>`]
|            :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.3.7:

:ref:`Mode option <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(FI|ForceInterrupt) <FI>`
     - it must be present for this action to interrupt a request that is under processing.

It is mandatory to provide a request index to interrupt it.



| :ref:`Back to Top <section3.3.7>`
| :ref:`Back to Table of Contents <index>`
