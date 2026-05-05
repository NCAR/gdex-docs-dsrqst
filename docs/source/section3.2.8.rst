
.. _section3.2.8:

3.2.8 - Delete Request File Information
=================================


.. _DL:

Action Option -**DL** (-**Delete**) (Aliases: -**RM**, -**Remove**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

deletes one or more request file records from GDEXDB for
the given data file names.

| **dsrqst** -(DL|Delete) [:ref:`Mode Options <mode3.2.8>`]
|           :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|           :ref:`-(FN|WebFile) <FN>` RequestFileNames
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode option:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(MD|MyDataset) <MD>`
     - writes information to GDEXDB regardless of whether the specialist running **dsrqst** owns the dataset

Use this action to delete request files. The request index is mandatory.



| :ref:`Back to Top <section3.2.8>`
| :ref:`Back to Table of Contents <index>`
