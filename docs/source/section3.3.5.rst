
.. _section3.3.5:

3.3.5 - Clean Request Information
=================================


.. _CR:

Action Option -**CR** (-**CleanRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

cleans requests by deleting all files built under
their request directories and the associated file records. Partitions are
removed if a request is divided into them. The file process count and the
request data size are also reset to 0. Use this action to clean up
requests so they can be rebuilt.

| **dsrqst** -(CR|CleanRequest)
|            :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

A request index is mandatory.



| :ref:`Back to Top <section3.3.5>`
| :ref:`Back to Table of Contents <index>`
