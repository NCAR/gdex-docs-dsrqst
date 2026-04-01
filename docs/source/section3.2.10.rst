
.. _section3.2.10:

3.2.10 - Set Tar File information
=================================


.. _ST:

Action Option -**ST** (-**SetTarfile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

modifies tar file information into RDADB for given
condition. One or multiple tar files can be processed each time.

Although a tar file record can be modified by a specialist, it is raely
needed. Tar file records are normally generated for a successfully-built
request with many small data files.

| **dsrqst** -(ST|SetTarfile) [:ref:`Mode Option <mode3.2.10>`]
|          [:ref:`-(RI|RequestIndex) <RI>` RequestIndices]
|          [:ref:`-(PI|PartitionIndex) <PI>` PartitionIndices]
|          [:ref:`-(TI|tarFileIndex) <TI>` TarfileIndices]
|          [:ref:`-(DS|Dataset) <DS>` dsnnn.n]
|          [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|          [:ref:`-(WF|WebFile) <WF>` DataFileNames]
|          [:ref:`-(SZ|Size) <SZ>` DataFileSize]
|          [:ref:`-(DF|DataFormat) <DF>` DataFormat]
|          [:ref:`-(AF|ArchiveFormat) <AF>` DataArchiveFormat]
|          [:ref:`-(FD|FileDate) <FD>` DateReadyOnline]
|          [:ref:`-(FT|FileTime) <FT>` TimeReadyOnline]
|          [:ref:`-(DE|Description) <DE>` FileDescription]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.2.10:

:ref:`Mode option <section4>` that can be specified for setting tar file Action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(MD|MyDataset) <MD>`
     - sets information into RDADB no matter the specialist who runs **dsrqst** owns the dataset or not
   * - :ref:`-(RO|ResetOrder) <RO>`
     - resets the display order indices of the tar file records according to the order as they are given per option :ref:`-WF <WF>` (-WebFile)



| :ref:`Back to Top <section3.2.10>`
| :ref:`Back to Table of Contents <index>`
