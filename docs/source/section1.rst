
.. _section1:

1 - INTRODUCTION
=================================

**dsrqst** controls and processes special data requests. It supports online
download requests for data subsetting and format conversion services. Queued
requests are managed by the centralized daemon `dscheck <https://gdex-docs-dscheck.readthedocs.io>`_ for processing on
specified machines. Final products are staged on the GDEX Server for online
access or for direct access from NCAR internal computers.

This application:

* Sets request control records for datasets, individual groups, and request types so that users can submit data requests. Hostnames may be specified to control which machines a request runs on. Requests are processed in either fully automated or specialist-controlled mode
* Divides a request into partitions. Partitions are processed concurrently, one per independent process
* Works with web interfaces on the GDEX Server, such as the data subset interfaces provided by DECS specialists. Detailed request information is passed to the web utility program 'dsrqst.php' through HTTP POST entries
* Optionally sends email notices to the specialists who are the primary owners of the datasets for which requests are submitted
* Allows specialists, in specialist-controlled mode, to grant requests by clicking a link in the email notice or by issuing a command on the Unix command line
* Allows the primary owner of a dataset under **dsrqst** control to temporarily transfer responsibility to another specialist (for example, during vacation or any period when they cannot check email to grant requests)
* Builds queued requests, or processes queued request partitions, via the centralized daemon `dscheck <https://gdex-docs-dscheck.readthedocs.io>`_. Final requested data are staged on the GDEX Server for online or background command-line access. Data files requested by multiple users are shared to reduce redundancy
* Purges online requests via the centralized daemon `dscheck <https://gdex-docs-dscheck.readthedocs.io>`_ or manually. Information about purged requests is recorded in GDEXDB and later gathered for data usage metrics by the utility program **viewrqstusage**
* Sends an email notice to the user who requested the data and, optionally, to the specialist who processed the request, after a request is built successfully. A link in the email notice opens the file-list webpage where the data is ready for online download
* Provides an option on the file-list webpage for users to notify **dsrqst** when their downloads are finished, so the request can be purged sooner
* Modifies file information for a specified request by adding or removing file records before the request is granted for processing
* Modifies a request, for example to change its status or its purge date/time
* Deletes a request before it is processed if the request is denied
* Restores a purged request so it can be reprocessed when a user needs the same data re-staged

Minimal steps to set up any type of data request:

* Develop a web interface to accept user requests, and have the interface submit each request to 'dsrqst.php' via HTTP POST entries. The mandatory and optional entry values are described later in this document.
* Add a request control record for a dataset and a specified request type (for example, 'S' for data subset, or 'T' for data subset with format conversion) via action :ref:`-SC <SC>` (-SetControl), executed by the specialist who is the primary owner of the dataset.
* Optionally set partition controls to govern how many data files or how much data are processed in each individual process for a single request.
* A DECS specialist optionally receives an email notice each time a request is submitted. Clicking a link in the email grants the request and places it in the queue under specialist-controlled mode.

To prevent DECS specialists from accidentally processing the wrong request,
only the specialist who owns a request can run **dsrqst** to modify or process
that request or its partitions. Ownership of a request can be transferred to
another specialist by setting a different specialist in the request control
record.

The following sections describe general usage of **dsrqst** first, then provide
detailed descriptions of each option with examples. Other utility programs,
such as 'dsrqst.php', that help submit, change, and check request status
online are described at the end of the document.

All **dsrqst** configuration can be managed through the online interface at
https://gdex.ucar.edu/rda_pg_config under the entry for DSRQST.



| :ref:`Back to Top <section1>`
| :ref:`Back to Table of Contents <index>`
