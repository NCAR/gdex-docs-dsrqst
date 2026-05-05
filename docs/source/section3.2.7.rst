
.. _section3.2.7:

3.2.7 - Set Request File information
=================================


.. _SF:

Action Option -**SF** (-**SetFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

creates or modifies data file information in GDEXDB for
given dataset/group(s)/file(s) of a specified request index. One or more
remote files can be processed per call.

Although a specialist can modify a data file record, this is rarely
needed. Data file records are normally generated either by the web
interface that accepts data request submissions or by the subsetting
programs.

| **dsrqst** -(SF|SetFile) [:ref:`Mode Option <mode3.2.7>`]
|          [:ref:`-(RI|RequestIndex) <RI>` RequestIndices]
|          [:ref:`-(PI|PartitionIndex) <PI>` PartitionIndices]
|          [:ref:`-(TI|tarFileIndex) <TI>` TarfileIndices]
|          [:ref:`-(DS|Dataset) <DS>` dNNNNNN]
|          [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|          [:ref:`-(SL|SourceLink) <SL>` SourceDataID]
|          [:ref:`-(OT|SourceType) <OT>` SourceDataType]
|          [:ref:`-(WF|WebFile) <WF>` DataFileNames]
|          [:ref:`-(WT|WebFileType) <WT>` DataFileTypes]
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
     - resets the display-order indices of the data file records to match the order in which they are given via option :ref:`-WF <WF>` (-WebFile)



| :ref:`Back to Top <section3.2.7>`
| :ref:`Back to Table of Contents <index>`
