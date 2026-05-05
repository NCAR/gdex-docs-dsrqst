
.. _section3.1.3:

3.1.3 - Delete Request Control Information
=================================


.. _DL:

Action Option -**DL** (-**Delete**) (Aliases: -**RM**, -**Remove**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

deletes one or more request file records from GDEXDB for
the given data file names.

| **dsrqst** :ref:`-(DL|Delete) <DL>` [:ref:`Mode Options <mode3.1.3>`]
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



| :ref:`Back to Top <section3.1.3>`
| :ref:`Back to Table of Contents <index>`
