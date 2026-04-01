
.. _section3.2.7:

3.2.7 - Set Request File information
=================================


.. _SF:

Action Option -**SF** (-**SetFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

creates and modifies data file information into RDADB for
given dataset/group(s)/file(s) of a specified request index. One or multiple
remote files can be processed each time.

Although a data file record can be modified by a specialist, it is raely
needed. A data file record is normally either generated per Web interfaces
that accept submission of data requests or built per subsetting programs.

| **dsrqst** -(SF|SetFile) [:ref:`Mode Option <mode3.2.7>`]
|          [:ref:`-(RI|RequestIndex) <RI>` RequestIndices]
|          [:ref:`-(PI|PartitionIndex) <PI>` PartitionIndices]
|          [:ref:`-(TI|tarFileIndex) <TI>` TarfileIndices]
|          [:ref:`-(DS|Dataset) <DS>` dsnnn.n]
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

.. _mode3.2.7:

:ref:`Mode option <section4>` that can be specified for setting data file Action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(MD|MyDataset) <MD>`
     - sets information into RDADB no matter the specialist who runs **dsrqst** owns the dataset or not
   * - :ref:`-(RO|ResetOrder) <RO>`
     - resets the display order indices of the data file records according to the order as they are given per option :ref:`-WF <WF>` (-WebFile)



| :ref:`Back to Top <section3.2.7>`
| :ref:`Back to Table of Contents <index>`
