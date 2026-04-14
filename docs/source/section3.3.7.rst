
.. _section3.3.7:

3.3.7 - Interrupt Requests
=================================


.. _IR:

Action Option -**IR** (-**InterruptRequest**) (Alias: -**InterRupt**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

interrupts requests that are currently queued by
changing their status to 'I' (Interrupted) and recursively killing all child
processes running to build the requests.

| **dsrqst** -(IR|InterruptRequest) [:ref:`Mode Option <mode3.3.7>`]
|            :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode option:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(FI|ForceInterrupt) <FI>`
     - must be present to interrupt a request that is currently under processing.

A request index is mandatory.



| :ref:`Back to Top <section3.3.7>`
| :ref:`Back to Table of Contents <index>`
