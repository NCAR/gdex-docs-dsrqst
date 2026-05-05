
.. _section3.3.1:

3.3.1 - Build Individual Requests
=================================


.. _BR:

Action Option -**BR** (-**BuildRequest**) (Alias: -**ProcessRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -ProcessRequest) processes one or more
individual requests with the specified request indices.

| **dsrqst** -(BR|BuildRequest) [:ref:`Mode Options <mode3.3.1>`]
|           :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|          [:ref:`-(RN|RequestName) <RN>` RequestNames]
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

A request must be in status 'Q' (Queued) before it can be processed, and
the DECS specialist running the action must own the request.

To process a request owned by another specialist, use :ref:`Info option <section5>` :ref:`-LN <LN>`
(-LoginName) to provide that specialist's login name.

Provide local files via :ref:`Info option <section5>` :ref:`-LF <LF>` (-LocalFile) to build a Type 'C'
(Customized) request.

If a customized request location is provided, the requested data are
staged there and the request is purged immediately.



| :ref:`Back to Top <section3.3.1>`
| :ref:`Back to Table of Contents <index>`
