
.. _section3.2.6:

3.2.6 - Get Request File information
=================================


.. _GF:

Action Option -**GF** (-**GetFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves data file information for specified requests or
partitions.

| **dsrqst** -(GF|GetFile) [:ref:`Mode Options <mode3.2.6>`]
|          [:ref:`-(FN|FieldNames) <FN>` FieldNameString]
|          [:ref:`-(RI|RequestIndex) <RI>` RequestIndices]
|          [:ref:`-(RN|RequestName) <RN>` RequestNames]
|          [:ref:`-(PI|PartitionIndex) <PI>` PartitionIndices]
|          [:ref:`-(TI|TarfileIndex) <TI>` TarFileIndices]
|          [:ref:`-(DS|Dataset) <DS>` dNNNNNN]
|          [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|          [:ref:`-(OT|SourceType) <OT>` SourceDataType]
|          [:ref:`-(WF|WebFile) <WF>` DataFileNames]
|          [:ref:`-(WT|WebType) <WT>` DataFileTypes]
|          [:ref:`-(FS|FileStatus) <FS>` DataFileStatus]
|          [:ref:`-(SZ|Size) <SZ>` DataFileSize]
|          [:ref:`-(DF|DataFormat) <DF>` DataFormat]
|          [:ref:`-(AF|ArchiveFormat) <AF>` DataArchiveFormat]
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
     - show Dataset ID for each request file

Use :ref:`Info option <section5>` :ref:`-FN <FN>` (-FieldNames) to choose which data file fields to
retrieve. If :ref:`-FN <FN>` is not provided, it defaults to 'FRPTYSNMA'. Use :ref:`-FN <FN>` ALL
to retrieve every available field.

Valid data file field names and their corresponding :ref:`Info option <section5>` names:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - R
     - :ref:`-(RI|RequestIndex) <RI>`
     - data request index
   * - Q
     - :ref:`-(RN|RequestName) <RN>`
     - request name/ID
   * - P
     - :ref:`-(PI|PartitionIndex) <PI>`
     - request partition index
   * - T
     - :ref:`-(TI|TarfileIndex) <TI>`
     - tarfile index when this small file is tarred
   * - I
     - :ref:`-(GI|GroupIndex) <GI>`
     - group index
   * - B
     - :ref:`-(DS|Dataset) <DS>`
     - dataset name/ID, dNNNNNN
   * - L
     - :ref:`-(SL|SourceLink) <SL>`
     - source file name
   * - Z
     - :ref:`-(OT|SourceType) <OT>`
     - source data type, W - Web
   * - Y
     - :ref:`-(WT|WebFileType) <WT>`
     - file type, Data, dOcument, Software
   * - F
     - :ref:`-(WF|WebFile) <WF>`
     - file name online
   * - A
     - :ref:`-(FS|FileStatus) <FS>`
     - file status, R - requested, O - online
   * - S
     - :ref:`-(SZ|Size) <SZ>`
     - data file size
   * - C
     - :ref:`-(PC|ProcessCommand) <PC>`
     - command to process this request file
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
     - :ref:`-(TR|TimeReady) <TR>`
     - time request processed
   * - K
     - :ref:`-(FD|FileDate) <FD>`
     - date data file ready online
   * - Y
     - :ref:`-(FT|FileTime) <FT>`
     - time data file ready online
   * - D
     - :ref:`-(DE|Description) <DE>`
     - description of this file

Data file information can be retrieved for the request indices given via
option :ref:`-RI <RI>` (-RequestIndex), or the partition indices given via option :ref:`-PI <PI>`
(-PartitionIndex).

A data file record's status is initially 'R' (requested) when a request is
submitted. It changes to 'O' (online) after the request is processed and
the data file has been staged online for download. If a copy of the same
data file is already online for another request, that copy is shared
rather than staging a new one.


.. _3.2.6_e7:

**EXAMPLE 7. To get the default-field data file information for partition index 13:**

| **dsrqst** :ref:`GF <GF>` :ref:`-PI <PI>` 13

Content of the output:

.. code-block:: none

 WebFile<:>RequestIndex<:>PartitionIndex<:>Size<:>ArchiveFormat<:>DataFormat<:>FileStatus<:>
 godas.P.198306.tar<:>61160<:>13<:>196544000<:>GZ.TAR<:>GRIB1<:>O<:>
 ...



| :ref:`Back to Top <section3.2.6>`
| :ref:`Back to Table of Contents <index>`
