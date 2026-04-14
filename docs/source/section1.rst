
.. _section1:

1 - INTRODUCTION
=================================

**dsrqst** controls and processes special data requests. It supports online
download requests of data subset and format conversion services. Queued
requests are controlled by the centralized daemon `dscheck <https://gdex-docs-dscheck.readthedocs.io>`_ for processing
on specified machines. End products are staged on GDEX Server for online
access or direct access via NCAR internal computers.

This application:

* Sets request control records for datasets and/or individual groups and request types to allow users to submit data requests. Hostnames can be specified to control on which machines the data requests are processed. Requests are processed in either fully automated or specialist-controlled mode
* Divides a request further into partitions. Partitions are processed concurrently, one per independent process
* Provides web interfaces on GDEX Server for users, such as data subsets, are provided by DECS specialists. Detailed request information is passed to web utility program 'dsrqst.php' with specified HTTP POST entries
* Optionally sends email notices to specialists who are the primary owners of the datasets for which requests are submitted
* Allows specialists to grant requests, under the specialist-controlled mode, by clicking links in the email notices or by issuing commands at the Unix command line
* Allows primary owners of datasets under **dsrqst** control to temporarily transfer responsibility to other specialists, for example during vacation or when they cannot check email to grant requests for a period of time
* Builds queued requests, or processes queued request partitions, via the centralized daemon `dscheck <https://gdex-docs-dscheck.readthedocs.io>`_. Final requested data are staged on GDEX Server for online or background command-line access. Data files requested by multiple users are shared to reduce redundancy
* Purges online requests via the centralized daemon `dscheck <https://gdex-docs-dscheck.readthedocs.io>`_ or manually. Information about purged requests is recorded in GDEXDB and later gathered for data usage metrics via utility program **viewrqstusage**
* Sends an email notice to both the user who requested data and, optionally, the specialist who processes the request, after a request is built successfully. A link in the email notice leads to the webpage of the file list ready for online download
* Adds an option on the online file list webpage for users to notify **dsrqst** when downloads are finished so their requests can be purged sooner
* Modifies file information for a specified request by adding or removing file records before the request is granted for processing
* Modifies a request, such as changing request status and purge date/time
* Deletes a request before it is processed if the request is denied
* Restores a purged request to reprocess it based on user demand for re-staging the same data

Minimal steps to set up any type of data request:

* Develop a web interface to accept user requests and have the interface program submit a request to 'dsrqst.php' with HTTP POST entries. The mandatory and optional entry values are described later in this document.
* Add a request control record for a dataset for a specified request type, for example, 'S' for data subset, and 'T' for data subset with format conversion, via action :ref:`-SC <SC>` (-SetControl) by the specialist who is the primary owner of the dataset.
* Optionally set partition controls to further control how many data files or how much data to process in an individual process for one data request.
* A DECS specialist optionally receives an email notice each time a request is submitted. Clicking a link in the email grants the request by putting it in the queue for the specialist-controlled mode.

To prevent DECS specialists from accidentally processing the wrong request,
only the specialist who owns the request can execute **dsrqst** to modify and
process the request or its partitions. Ownership of requests can be
transferred to other specialists by setting a different specialist in the
request control record.

The following sections describe general usage of **dsrqst** first, then
provide detailed descriptions of each option with examples throughout. Other
utility programs, such as 'dsrqst.php', that help submit, change, and check
request status online are described at the end of the document.

All **dsrqst** configuration can be managed via online interface,
https://gdex.ucar.edu/rda_pg_config under the entry of DSRQST.



| :ref:`Back to Top <section1>`
| :ref:`Back to Table of Contents <index>`
