
.. _section3.3.2:

3.3.2 - Process Individual Partitions
=================================


.. _PP:

Action Option -**PP** (-**ProcessPartition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

processes one or more individual partitions with
the specified partition indices.

| **dsrqst** -(PP|ProcessPartition) [:ref:`Mode Options <mode3.3.2>`]
|           :ref:`-(PI|PartitionIndex) <PI>` PartitionIndices
|          [:ref:`-(LF|LocalFile) <LF>` LocalFileNames]
|          [:ref:`-(MO|Modules) <MO>`  ModuleList]
|          [:ref:`-(EV|Environments) <EV>`  EnvironmentPairList]
|          [:ref:`-(QS|QsubOptions) <QS>`  PBSBatchOptions]
|          [:ref:`-(BP|BatchProcess) <BP>` [BatchProcessHosts]]
|          [:ref:`-(LN|LoginName) <LN>` SpecialistLoginName]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(AW|AnyWhere) <AW>`
     - works with :ref:`Info option <section5>` :ref:`-BP <BP>` (-BatchProcess) to allow the recorded **dsrqst** command to be started anywhere
   * - :ref:`-(BG|BackGround) <BG>`
     - background process; turns off screen display for both standard output and standard error
   * - :ref:`-(GZ|GMTZone) <GZ>`
     - uses GMT dates/times as controlling times
   * - :ref:`-(NE|NoEmail) <NE>`
     - does not send email to the specialist after update
   * - :ref:`-(NO|NotOnline) <NO>`
     - does not publish the file list after update and sets the request status to N

A partition must be in status 'Q' (Queued) before it can be processed, and
the DECS specialist running the action must own the partition.



| :ref:`Back to Top <section3.3.2>`
| :ref:`Back to Table of Contents <index>`
