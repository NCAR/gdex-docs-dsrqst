
.. _section3.3.5:

3.3.5 - Clean Request Information
=================================


.. _CR:

Action Option -**CR** (-**CleanRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

cleans requests by deleting all the files built under
the request directories and the associated file records. Partitions are
removed if a request is divided into partitions. File process count
and request data size are also initialized to 0. Use this action to clean up
the requests to allow them to be rebuilt.

| **dsrqst** -(CR|CleanRequest)
|            :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

It is mandatory to provide a request index to clean it.



| :ref:`Back to Top <section3.3.5>`
| :ref:`Back to Table of Contents <index>`
