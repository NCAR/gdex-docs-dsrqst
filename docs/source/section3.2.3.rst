
.. _section3.2.3:

3.2.3 - Delete Request Information
=================================


.. _DL:

Action Option -**DL** (-**Delete**) (Aliases: -**RM**, -**Remove**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

deletes one or multiple request file records from GDEXDB for
given data file names.

| **dsrqst** :ref:`-(DL|Delete) <DL>` [:ref:`Mode Options <mode3.2.3>`]
|           :ref:`-(RI|RequestIndex) <RI>` RequestIndices
|           :ref:`-(FN|WebFile) <FN>` RequestFileNames
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode option:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(MD|MyDataset) <MD>`
     - sets information into GDEXDB no matter the specialist who runs **dsrqst** owns the dataset or not

Use this action to delete request files. Request Index must be provided.



| :ref:`Back to Top <section3.2.3>`
| :ref:`Back to Table of Contents <index>`
