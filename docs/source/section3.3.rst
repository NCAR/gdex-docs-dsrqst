
.. _section3.3:

3.3 - Request Process Actions
=================================

In addition to be started by the centralized daemon 'dscheck', request processes
can be started manually by DSS specialists can process manually, providing
request indices while executing Action :ref:`-BR <BR>` (-BuildRequest) of **dsrqst**.
A request can only be processed manually by a specialist who is listed as
the one who controls the request.

Data files of a processed request are staged on RDA Server temporarily for
online download or access via NCAR internal computers. DSS specialist can also
urge a request manually at due time by providing the request index to run
**dsrqst** with Action :ref:`-PR <PR>` (-PurgeRequest).

Request information can be processed and purged via Actions in this section:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`Build Individual Requests <section3.3.1>`
     - run **dsrqst** to process one or multiple queued requests
   * - Process Partitions
     - run **dsrqst** to process one or multiple queued partitions
   * - :ref:`Purge Individual Requests <section3.3.3>`
     - run **dsrqst** to purge one or multiple due requests
   * - :ref:`Change Purge Time <section3.3.4>`
     - change purge time of online requests for them to be purged later or sooner
   * - :ref:`Clean Request Information <section3.3.5>`
     - clean one or multiple requests by deleting the files built and file records created in RDADB
   * - :ref:`Unlock Request Information <section3.3.6>`
     - unlock one or multiple request records for them to be rebuilt on a different host
   * - :ref:`Interrupt Requests <section3.3.7>`
     - interrupt Queued requests by setting their status to 'I' and killing all the running processes that are building the requests
   * - Unlock Partitions
     - unlock one or multiple partition records for them to be reprocessed on a different host
   * - :ref:`Interrupt Partitions <section3.3.8>`
     - interrupt Queued partitions by setting their status to 'I' and killing all the running partition processes
   * - :ref:`Restore Purged Requests <section3.3.9>`
     - recreate a request that is purged already be restore the request and its file information saved in the purge records

.. toctree::
   :maxdepth: 1
   :caption: Table of Contents

   section3.3.1
   section3.3.2
   section3.3.3
   section3.3.4
   section3.3.5
   section3.3.6
   section3.3.7
   section3.3.8
   section3.3.9



| :ref:`Back to Top <section3.3>`
| :ref:`Back to Table of Contents <index>`
