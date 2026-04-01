
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
|          [:ref:`-(DS|Dataset) <DS>` dsnnn.n]
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

.. _mode3.2.6:

:ref:`Mode options <section4>` that can be specified for getting request Action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(FO|FormatOutput) <FO>`
     - format the column output with a fix width for all values of a given field
   * - :ref:`-(WD|WithDataset) <WD>`
     - show Dataset ID for each request file

Use :ref:`Info option <section5>` :ref:`-FN <FN>` (-FieldNames) to specify what data file fields to be
retrieved. It defaults to 'FRPTYSNMA' if option :ref:`-FN <FN>` is not provided. Data File
information of all available fields is retrieved if :ref:`-FN <FN>` ALL is given.

Valid field names of data files and their corresponding :ref:`Info option <section5>` names:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - R
     - :ref:`-(RI|ReuqstIndex) <RI>`
     - data request index
   * - Q
     - :ref:`-(RN|RequestName) <RN>`
     - request name/ID
   * - P
     - :ref:`-(PI|ParitionIndex) <PI>`
     - request partition index
   * - T
     - :ref:`-(TI|TarfileIndex) <TI>`
     - tarfile index for this small file is tarred
   * - I
     - :ref:`-(GI|GroupIndex) <GI>`
     - group index
   * - B
     - :ref:`-(DS|Dataset) <DS>`
     - dataset name/ID, dsnnn.n
   * - L
     - :ref:`-(SL|SourceLink) <SL>`
     - source file name
   * - Z
     - :ref:`-(OT|SourceType) <OT>`
     - source data type, M - HPSS, W - Web
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
     - command to process this reuqest file
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

Data file information can be retrieved for specified request indices per
option :ref:`-RI <RI>` (-RequestIndex) or partition indices per option :ref:`-PI <PI>` (-PartitionIndex).

Status of a data file record is initially set to 'R' as requested at the time
a request is submitted. It is changed to 'O' as online after the request is
processed and the data file is staged online for download. If a copy of the
same data file is online already for another request, this data file is shared
instead of a new copy is staged.


.. _3.2.6_e7:

**EXAMPLE 7. To get the data file information of partition index 42 for default fields:**

| **dsrqst** :ref:`GF <GF>` :ref:`-PI <PI>` 13

Content of the output:

.. code-block:: none

 WebFile<:>RequestIndex<:>PartitionIndex<:>Size<:>ArchiveFormat<:>DataFormat<:>FileStatus<:>
 godas.P.198306.tar<:>61160<:>13<:>196544000<:>GZ.TAR<:>GRIB1<:>O<:>
 ...



| :ref:`Back to Top <section3.2.6>`
| :ref:`Back to Table of Contents <index>`
