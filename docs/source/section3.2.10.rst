
.. _section3.2.10:

3.2.10 - Set Tar File information
=================================


.. _ST:

Action Option -**ST** (-**SetTarfile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

modifies tar file information in GDEXDB for the given
conditions. One or more tar files can be processed per call.

Although a specialist can modify a tar file record, this is rarely needed.
Tar file records are normally generated automatically for a successfully
built request that contains many small data files.

| **dsrqst** -(ST|SetTarfile) [:ref:`Mode Option <mode3.2.10>`]
|          [:ref:`-(RI|RequestIndex) <RI>` RequestIndices]
|          [:ref:`-(PI|PartitionIndex) <PI>` PartitionIndices]
|          [:ref:`-(TI|tarFileIndex) <TI>` TarfileIndices]
|          [:ref:`-(DS|Dataset) <DS>` dNNNNNN]
|          [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|          [:ref:`-(WF|WebFile) <WF>` DataFileNames]
|          [:ref:`-(SZ|Size) <SZ>` DataFileSize]
|          [:ref:`-(DF|DataFormat) <DF>` DataFormat]
|          [:ref:`-(AF|ArchiveFormat) <AF>` DataArchiveFormat]
|          [:ref:`-(FD|FileDate) <FD>` DateReadyOnline]
|          [:ref:`-(FT|FileTime) <FT>` TimeReadyOnline]
|          [:ref:`-(DE|Description) <DE>` FileDescription]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(MD|MyDataset) <MD>`
     - writes information to GDEXDB regardless of whether the specialist running **dsrqst** owns the dataset
   * - :ref:`-(RO|ResetOrder) <RO>`
     - resets the display-order indices of the tar file records to match the order in which they are given via option :ref:`-WF <WF>` (-WebFile)



| :ref:`Back to Top <section3.2.10>`
| :ref:`Back to Table of Contents <index>`
