
.. _section1:

1 - INTRODUCTION
=================================

Program **dsrqst** is a utility for controlling and processing special data requests.
The current implementation supports online download requests of the HPSS data for
users who want to access the data via RDA Web Server, and services of data subsets
and data format conversions. The queued requests are normally controlled by
centralized daemon 'dscheck' to be processed on specified machines. The end
products are staged on RDA server for users to access online or via NCAR internal
computers directly.

This application is implemented to:

* Set request control records for datasets and/or individual groups, and request types to allow users to submit data requests. A number of hostnames can be specified to control on, or not on, what machines the data requests are processed. The requests are processed in Modes of either fully automated or specialist controlled. If a dataset or a group that has a request control record set in RDADB via **dsrqst** for type 'M', the users, who have permission to view the HPSS data lists of the dataset or group, are able to submit online data download requests
* Divide A request further into partitions. The partitions are processed concurrently, one in each independent process.
* Provide web interfaces on RDA Server to allow users with permission to select the HPSS data files for online download requests. Web interfaces for other request types, i.e. data subsets, are provided by DSS specialists. Detail request information is passed to web utility program 'dsrqst.php' with specified HTTP POST entries
* Send email notices optionally to specialists who are the primary owners of the datasets that requests are submitted
* Allow specialists to grant the requests, under the specialist controlled mode, by clicking links in the email notices or issue commands at the Unix commandline
* Allow primary owners of the datasets under **dsrqst** control to temporarily transfer responsibility to other specialists, in case on vacation or other reasons that they can not check email to grant requests for a period of time
* Build queued requests, or process queued request partitions, via a centralized daemon 'dscheck'. The final requested data are staged on RDA Server for online or background commandline accesses. Same data files that are requested by multiple users are shared to reduce redundancy.
* Purge online requests via a centralized daemon 'dscheck' or manually. Information of purged requests are recorded in RDADB and, later, are gathered for data usage metrics via viewing utility program 'viewrqstusage'.
* Send an email notice to both the user who requested data and, optionally, to the specialist who processes the request, after a request is built successfully. A link in the email notice leads to the webpage of the file list ready for online download
* Add option on the online file list webpage to allow users to inform **dsrqst** for finishing data downloads so that their requests can be purged sooner
* Modify file information for a specified request by adding or removing file records before the request is granted for processing
* Modify request, such as changing request status, and purge date/time
* Delete a request before it is processed in case the request is denied
* restore purged request to reprocess it based on user's demand for re-staging the same data

Minimal steps to setup any types of data requests:

* Develop a web interface to accept user requests and the interface program submit a request to 'dsrqst.php' with HTTP POST entries. The mandatory and optional entry values are describe later in this document. For online download requests of HPSS data the web interface is automatically created via utility program **publish_filelist**.
* Add a request control record for a dataset for a specified request type, for examples, "M" for HPSS data, 'S' for data subset, and 'T' for data subset with format conversion, via action :ref:`-SC <SC>` (-SetControl) by a specialist who is the primary owner of the dataset.
* Optionally, partition controls can be set to further control how many data files or how much data size to be processed in an individual process for one data request.
* DSS specialist, optionally, receives an email notice each time a request is submitted. Click a link in the email to grant the request by putting it in the Queue for the specialist-controlled :ref:`Mode <section4>`.

To prevent DSS specialists from executing **dsrqst** accidentally for processing a
wrong request, only the specialist who owns the request can execute **dsrqst** to
modify and process the request or its partitions. Ownership of requests can be
transfered to other specialists by setting a different specialist in the request
control record.

In the following sections, general usage of **dsrqst** is described first; and
detail descriptions of different options are given next; and examples are
interspersed through out the document. Other utility programs, such as 'dsrqst.php',
that help to submit, change request status, and check request status online are
described at the end of the document.

All **dsrqst** configuration can be managed via online interface,
https://gdex.ucar.edu/rda_pg_config
under the entry of DSRQST.



| :ref:`Back to Top <section1>`
| :ref:`Back to Table of Contents <index>`
