
.. _section3.2.9:

3.2.9 - Get Tar File information
=================================


.. _GT:

Action Option -**GT** (-**GetTarfile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves tar file information for specified requests or
partitions.

| **dsrqst** -(GT|GetTarfile) [:ref:`Mode Options <mode3.2.9>`]
|          [:ref:`-(FN|FieldNames) <FN>` FieldNameString]
|          [:ref:`-(RI|RequestIndex) <RI>` RequestIndices]
|          [:ref:`-(RN|RequestName) <RN>` RequestNames]
|          [:ref:`-(PI|PartitionIndex) <PI>` PartitionIndices]
|          [:ref:`-(TI|TarfileIndex) <TI>` TarFileIndices]
|          [:ref:`-(WF|WebFile) <WF>` TarFileNames]
|          [:ref:`-(DS|Dataset) <DS>` dNNNNNN]
|          [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|          [:ref:`-(SZ|Size) <SZ>` TarFileSize]
|          [:ref:`-(DF|DataFormat) <DF>` DataFormat]
|          [:ref:`-(AF|ArchiveFormat) <AF>` ArchiveFormat]
|          [:ref:`-(FD|FileDate) <FD>` DateReadyOnline]
|          [:ref:`-(FT|FileTime) <FT>` TimeReadyOnline]
|          [:ref:`-(OF|OutputFile) <OF>` OutputFileName]
|          [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(FO|FormatOutput) <FO>`
     - format the column output with a fixed width for all values of a given field
   * - :ref:`-(WD|WithDataset) <WD>`
     - show Dataset ID for each request tar file

Use :ref:`Info option <section5>` :ref:`-FN <FN>` (-FieldNames) to specify which tar file fields to
retrieve. It defaults to 'TFRPSMN' if :ref:`-FN <FN>` is not provided. Tar file
information of all available fields is retrieved if :ref:`-FN <FN>` ALL is given.

Valid field names of tar files and their corresponding :ref:`Info option <section5>` names:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - T
     - :ref:`-(TI|TarfileIndex) <TI>`
     - tarfile index when this small file is tarred
   * - R
     - :ref:`-(RI|RequestIndex) <RI>`
     - data request index
   * - Q
     - :ref:`-(RN|RequestName) <RN>`
     - request name/ID
   * - P
     - :ref:`-(PI|PartitionIndex) <PI>`
     - request partition index
   * - I
     - :ref:`-(GI|GroupIndex) <GI>`
     - group index
   * - B
     - :ref:`-(DS|Dataset) <DS>`
     - dataset name/ID, dNNNNNN
   * - F
     - :ref:`-(WF|WebFile) <WF>`
     - tar file name
   * - S
     - :ref:`-(SZ|Size) <SZ>`
     - data file size
   * - M
     - :ref:`-(DF|DataFormat) <DF>`
     - data format, i.e. GRIB, NetCDF
   * - N
     - :ref:`-(AF|ArchiveFormat) <AF>`
     - archive format, i.e. TAR, GZ
   * - O
     - :ref:`-(DO|DisplayOrder) <DO>`
     - order the file shown on webpage
   * - J
     - :ref:`-(FD|FileDate) <FD>`
     - date data file ready online
   * - K
     - :ref:`-(FT|FileTime) <FT>`
     - time data file ready online
   * - D
     - :ref:`-(DE|Description) <DE>`
     - description of this file

Tar file information can be retrieved for specified request indices per
option :ref:`-RI <RI>` (-RequestIndex) or partition indices per option :ref:`-PI <PI>` (-PartitionIndex).



| :ref:`Back to Top <section3.2.9>`
| :ref:`Back to Table of Contents <index>`
