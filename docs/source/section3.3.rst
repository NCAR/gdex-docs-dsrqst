
.. _section3.3:

3.3 - Request Process Actions
=================================

Request processes can be started by the centralized daemon `dscheck <https://gdex-docs-dscheck.readthedocs.io>`_ or
manually by a DECS specialist who supplies request indices when running
Action :ref:`-BR <BR>` (-BuildRequest). A request can only be processed manually by
the specialist who controls it.

Data files for a processed request are staged on the GDEX Server
temporarily for online download or for access from NCAR internal
computers. A DECS specialist can also purge a request manually at its due
time by supplying the request index to **dsrqst** with Action :ref:`-PR <PR>`
(-PurgeRequest).

Requests are processed and purged through the actions in this section:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`Build Individual Requests <section3.3.1>`
     - run **dsrqst** to process one or more queued requests
   * - Process Partitions
     - run **dsrqst** to process one or more queued partitions
   * - :ref:`Purge Individual Requests <section3.3.3>`
     - run **dsrqst** to purge one or more due requests
   * - :ref:`Change Purge Time <section3.3.4>`
     - change the purge time of online requests so they are purged later or sooner
   * - :ref:`Clean Request Information <section3.3.5>`
     - clean one or more requests by deleting the files that have been built and the file records created in GDEXDB
   * - :ref:`Unlock Request Information <section3.3.6>`
     - unlock one or more request records so they can be rebuilt on a different host
   * - :ref:`Interrupt Requests <section3.3.7>`
     - interrupt queued requests by setting their status to 'I' and killing all running processes that are building them
   * - Unlock Partitions
     - unlock one or more partition records so they can be reprocessed on a different host
   * - :ref:`Interrupt Partitions <section3.3.8>`
     - interrupt queued partitions by setting their status to 'I' and killing all running partition processes
   * - :ref:`Restore Purged Requests <section3.3.9>`
     - restore an already-purged request by re-creating the request and its file information from the saved purge records

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
