
.. _section5.2:

5.2 - Multi-Value Info Options
=================================

A multi-value Info option passes one or more values for a single Info
option to **dsrqst**. At least one value must follow each multi-value
option.


.. _AF:

Info Option -**AF** (-**ArchiveFormat**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the file
archive format for files staged on the GDEX Server for download. The
archive format indicates post-processing applied to a data file. COS
blocking on the original data files — option values 'BI' (binary blocked),
'C1' or 'CH' (ASCII/character blocked) — is automatically removed, and
the COS block options are stripped from the archive format value. Option
value 'TAR' means a tarred file, 'Z' a compressed file, 'GZ' a gzipped
file, and 'BZ2' a file compressed with bzip2. 'TAR.GZ', for example,
means a file is tarred and then gzipped; the order is significant. The
archive format string is at most 10 characters; additional characters are
truncated.


.. _CC:

Info Option -**CC** (-**CarbonCopy**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

provides one or more additional email addresses to
receive a Cc'd notification of request processing results. Carbon copy
emails can be set in a request control record via :ref:`Action <section3>` :ref:`-SC <SC>`
(-SetControl) to control who is Cc'd on the notice after a request is
successfully built. Defaults to 'S', meaning the associated specialist
only. Multiple emails can be supplied as a single space-delimited string
of up to 255 characters. Set it to empty to stop carbon-copy email.

For DECS specialists, login user names are accepted in place of full
email addresses; otherwise, full email addresses are required for any
domain other than 'ucar.edu'.


.. _5.2_e9:

**EXAMPLE 9. To Cc 'schuster@ucar.edu' on the processing results for request index 42, supply Info option -CC with the login user name 'schuster':**

| **dsrqst** :ref:`BR <BR>` :ref:`-RI <RI>` 42 :ref:`-CC <CC>` schuster


.. _CI:

Info Option -**CI** (-**ControlIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the automatically generated control index for a
request control record when it is first added for a given dataset and/or
group index.


.. _CM:

Info Option -**CM** (-**ControlMode**) (Alias: -**ControlMethod**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -ControlMethod) sets the request control mode
for a request control record. 'S' for specialist-controlled mode and 'A'
for automated request mode.


.. _DB:

Info Option -**DB** (-**Debug**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

turns on debug mode with the specified information. This
option accepts up to 3 values: debug level, debug log file path, and
debug log file name. The debug level is mandatory. It can be a single
integer value — for example, 1000 logs debug messages for levels 1
through 1000 — or a range such as 200-1000, which logs messages from
level 200 through 1000. The default debug file path is
'${DSSHOME}/dssdb/log' and the default debug file name is 'pgdss.dbg'.
Provide the second and third values to override these defaults.


.. _DE:

Info Option -**DE** (-**Description**) (Aliases: -**Desc**, -**Note**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -Desc|-Note) sets a readable description for
a request control, request partition, request record, or data file.
Multiple lines are allowed when the description is supplied through an
input file specified via Info option :ref:`-IF <IF>` (-InputFile).

The description for a request record is normally filled by passing
'rnote' to the online utility program 'dsrqst.php'. Use the html tags
<p> and </p> to begin and end the description for html text; without a
leading <p>, the html tags <pre> and </pre> are added automatically to
preserve the original text formatting on the final request data output
webpage.


.. _DF:

Info Option -**DF** (-**DataFormat**) (Aliases: -**ContentFormat**, -**InternalFormat**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the content
format of the files staged on the GDEX Server for download. For example,
NetCDF, IMMA, etc.


.. _DO:

Info Option -**DO** (-**DisplayOrder**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

display-order indices for data files of a given
request. Ignored when :ref:`Mode option <section4>` :ref:`-RO <RO>` (-Reorder) is present.


.. _DP:

Info Option -**DP** (-**DatePurge**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the date when a request is due to be purged. A
purge date is set automatically when a request is processed. Use this
option to change it.


.. _DQ:

Info Option -**DQ** (-**DateRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the date a request was submitted. The request
date is set automatically when a request is submitted. Use this option
only if the date needs to be changed.


.. _DR:

Info Option -**DR** (-**DateReady**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the date when a request's data files are ready
online for download. The ready date is set automatically when a request
is processed. Use this option only if it needs to be changed.


.. _DS:

Info Option -**DS** (-**Dataset**) (Aliases: -**Dsid**, -**DatasetID**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

provides one or more dataset IDs for the actions that
accept them.


.. _EM:

Info Option -**EM** (-**Email**) (Aliases: -**RequestEmail**, -**RequestUserEmail**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the user email addresses in request records for the
users who submitted them.


.. _EN:

Info Option -**EN** (-**EmailNotice**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets a file name for a specified email notice in a
request control record or an individual request record, overriding the
default email notice template. If an email template file is set on a
request control record, every data request under that control record
shares the same template.

The default email notice template is $WebDownloadHome/notices/email_notice.
Copy and edit it to create your own customized email file. Provide an
absolute path with the file name if your template is not in the standard
directory $WebDownloadHome/notices/.


.. _EO:

Info Option -**EO** (-**EmptyOutput**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the empty-output flag, which controls whether an
email notice is sent to a public user when their request produced no
output data. Valid values: 'Y' sends email to the user for empty output;
'N' sends the notice to the specialist only. The default is 'N'. A 'Y'
can be set on a request control record via :ref:`Action <section3>` :ref:`-SC <SC>` (-SetControl).


.. _EV:

Info Option -**EV** (-**Environments**) (Alias: -**Envs**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -Envs) specifies environment variables, in
the form VarName=VarValue separated by ',', to set when running **dsrqst**
as a batch job. The variables are set in the batch starting script.

An environment variable with a leading '!' is treated as an executable
command, and its returned string is used as a dynamically generated
variable string.


.. _FC:

Info Option -**FC** (-**FileCount**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the number of data files requested in a single
request.


.. _FD:

Info Option -**FD** (-**FileDate**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the date a data file was staged online.


.. _FS:

Info Option -**FS** (-**FileStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the file status in an individual data file record.
Valid statuses: 'R'equested, 'O'nline, and 'E'rror.


.. _FT:

Info Option -**FT** (-**FileTime**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the time a data file was staged online.


.. _GI:

Info Option -**GI** (-**GroupIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

group indices. Relevant only when a dataset is
divided into groups. Valid group indices are 1, 2, 3, ...; 0 means the
action applies to the whole dataset, and is the default if not provided
explicitly.


.. _HN:

Info Option -**HN** (-**HostName**) (Alias: -**HostMachine**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

host machine names to set in request control records or
individual request records. One or more host names can be set on a
request control record. The host name information on a request control
record controls which machines its associated requests can or cannot run
on. An individual request can only be built on a specified machine when
its host name field is set.


.. _5.2_e10:

**EXAMPLE 10. Set the request control record with control index 67 of d540000 to restrict its associated requests to bross and evans only:**

| **dsrqst** :ref:`SC <SC>` :ref:`-CI <CI>` 67 :ref:`-HN <HN>` bross:evans

Add '!' before the host names, as in :ref:`-HN <HN>` \!bross:evans, to restrict the
associated requests to every available machine other than bross and
evans. The character '!' must be escaped on the command line.


.. _IF:

Info Option -**IF** (-**InputFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

input file names; one or more can be given on the
command line. Input files hold all valid options and the values for the
Info options that are passed to **dsrqst** for execution.

Inside an input file, lines beginning with '#' are treated as comments.
Option names can be given in short, long, or alias form. :ref:`Action <section3>` and :ref:`Mode <section4>`
options use the format OptionName<!>. Single-value assignments use the
format OptionName<=>OptionValue, with one option per line. A different
setting sign for :ref:`Action <section3>` and :ref:`Mode options <section4>` can be configured via Info
option -AO (-ActOption, default '<!>'); a different equal sign for
single-value assignments can be configured via Info option :ref:`-ES <ES>`
(-EqualSign, default '<=>'). Multi-value assignments use columns
delimited by the separator configured via option :ref:`-SP <SP>` (-Separator,
default '<:>'). The first line is the column-title line listing the
multi-value option names; the remaining lines hold the values
corresponding to each column title. Value rows continue until the end of
the file, or until a new column-name line or another single-value
assignment appears. If the last column is a multi-line value field, an
additional separator must be appended to each line, including the
column-title line, to terminate lines properly.


.. _LF:

Info Option -**LF** (-**LocalFile**) (Alias: -**LocFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

local file names for pre-processed
customized data.


.. _LM:

Info Option -**LM** (-**RequestLimit**) (Alias: -**UpLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

; 0 means use the system default of a 40 GB limit.
Sets the upper limit, in GB, of data that can be requested at one time.
This limit should be checked and validated before a request is submitted.


.. _MO:

Info Option -**MO** (-**Modules**) (Alias: -**Mods**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -Mods) specifies module names, separated by ',',
to load when running **dsrqst** as a batch job. The modules are set in the
batch starting script.

A module name with a leading '!' is treated as an executable command, and
its returned string is used as a dynamically generated module name string.


.. _MP:

Info Option -**MP** (-**MaxPeriod**) (Alias: -**MaxrequestPeriod**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the maximum default request period on the request
interface, to prevent an oversized default request job. Valid example
values are 5Y or 10M, for periods of 5 years or 10 months respectively.


.. _MR:

Info Option -**MR** (-**MaxRequest**) (Alias: -**MaximumRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the maximum number of
outstanding requests allowed for a single dsrqst control record from one
user. Defaults to 20. A positive value, such as 10, can be set via
:ref:`Action <section3>` :ref:`-SC <SC>` (-SetControl) on the request control record. When the maximum
is reached, additional requests are denied until outstanding requests
are purged or deleted.


.. _OB:

Info Option -**OB** (-**OrderBy**) (Alias: -**OrderByPattern**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

temporal patterns for ordering
a file list according to the string values of the field names specified
via option :ref:`-ON <ON>` (-OrderNames). 'YYYYmon', for example, orders by a 4-digit
year followed by a three-letter lowercase month name such as 'jan',
'feb', etc. See option :ref:`-ON <ON>` (-OrderNames) for examples of ordering files
by temporal patterns.


.. _OR:

Info Option -**OR** (-**ORiginFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the original file name with path set in a source
file record. This value is used when the source link is empty.


.. _OT:

Info Option -**OT** (-**SourceType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

original data type; 'W' for data on a Web Server.


.. _PC:

Info Option -**PC** (-**ProcessCommand**) (Aliases: -**Command**, -**SpecialCommand**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -Command) sets the customized command
used to build requests, process partitions, or process individual files.


.. _PF:

Info Option -**PF** (-**PartitionFlag**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the partition command call flag for a subset
request.
N - call the customized command in the form
'CustomizedCommand RequestIndex' to initialize the file list only,
with no further command calls during the partition process or the
final request build;
P - call the customized command in the form
'CustomizedCommand RequestIndex WorkPath PartitionIndex' to also
process partition data;
F - call the customized command in the form
'CustomizedCommand RequestIndex WorkPath' to build the request data
finally;
B - both P and F.


.. _PI:

Info Option -**PI** (-**PartitionIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the automatically generated partition index for a
request partition record when it is first added.


.. _PL:

Info Option -**PL** (-**PartitionLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the maximum number of files per partition in
a request control configuration via action :ref:`-SC <SC>` (-SetControl).


.. _PZ:

Info Option -**PZ** (-**PartitionsiZe**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the maximum data size per partition in a
request control configuration via action :ref:`-SC <SC>` (-SetControl).


.. _PO:

Info Option -**PO** (-**Priority**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the process priority of queued requests. The default
is 10; 1 is the highest priority.


.. _PS:

Info Option -**PS** (-**PartitionStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

partition status for a request partition record.
'I' for an inclusive condition, 'E' for an exclusive condition.


.. _QS:

Info Option -**QS** (-**QSubOptions**) (Alias: -**PBSOptions**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -PBSOptions) specifies options for running
**dsrqst** as a batch job via qsub on PBS nodes. The qsub options must be
quoted on the command line, for example :ref:`-QS <QS>` '-l walltime=12:00:00'.

A qsub option string with a leading '!' is treated as an executable
command, and its returned string is used as a dynamically generated
qsub option string.


.. _RF:

Info Option -**RF** (-**RequestInfo**) (Alias: -**RequestInformation**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -RequestInformation) sets additional request
information for a request record, such as detailed subsetting
information. Request information is normally filled by passing 'rinfo' to
the online utility program 'dsrqst.php'.


.. _RI:

Info Option -**RI** (-**RequestIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the automatically generated request index for a
request record when it is first created upon user submission via the web
interface.


.. _RL:

Info Option -**RL** (-**RequestLocation**) (Aliases: -**RequestHome**, -**RequestPath**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -RequestHome|RequestPath) specifies a
customized location at which to stage the request result.


.. _RN:

Info Option -**RN** (-**RequestName**) (Alias: -**RequestID**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the request name or ID, set automatically as the
user's uppercased last name combined with the request index.


.. _RO:

Mode Option -**RO** (-**ResetOrder**) (Alias: -**Reorder**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -Reorder) resets the display order of the
data files in a request to match the order in which the data file
records are given for :ref:`Action <section3>` :ref:`-SF <SF>` (-SetFile). The display order can also
be set explicitly by providing display-order index values via Info
option :ref:`-DO <DO>` (-DisplayOrder).


.. _RS:

Info Option -**RS** (-**RequestStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

request status for an individual request record.
Valid statuses: 'W'ait, 'Q'ueue, 'O'nline, 'I'nterrupted, 'H'old,
'P'urge, and 'E'rror.


.. _RT:

Info Option -**RT** (-**RequestType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the request type. Valid types: S - Subset data,
T - Subset/Format Conversion, F - Format Conversion (Web), P - Data
Plotting, C - Customized Data, D - CDP link, N - NCARDAP (THREDDS) Data
Server, Q - Database Query, and R - Realtime DataDownload.


.. _SI:

Info Option -**SI** (-**SizeInput**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the size of the original data required for a request.


.. _SL:

Info Option -**SL** (-**SourceLink**) (Alias: -**SourceID**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the file name of the original data. For type 'W',
this is a web file.


.. _SN:

Info Option -**SN** (-**Specialist**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the login name of a specialist in GDEXDB for
request control records and request records. When the requests are
handled, the system login name is validated against the one stored in
GDEXDB; both the build and the purge processes are blocked if they do
not match.


.. _SQ:

Info Option -**SQ** (-**SizeRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the total data size of all files requested in a
single request.


.. _SZ:

Info Option -**SZ** (-**Size**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the file size of each data file online.


.. _TA:

Info Option -**TA** (-**TarFlag**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a field on request control and request records. 'Y' to
tar small request files, 'N' otherwise.


.. _TF:

Info Option -**TF** (-**ToFormat**) (Aliases: -**OutputFormat**, -**ProductFormat**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a ':'-delimited
string of the data formats for the output files staged on the GDEX
Server for download after format conversion or subsetting. These are
content formats of the output data files. For example, NETCDF:GRIB.

NOTE: the output format(s) set via this option must be supported by the
underlying format conversion commands for full data files or subsetting
outputs.


.. _TI:

Info Option -**TI** (-**TarfileIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the automatically generated tar file index for a
tar file record when small request files are tarred.


.. _TP:

Info Option -**TP** (-**TimePurge**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the time a request is due to be purged. A purge
time is set automatically when a request is processed. Use this option
to change it.


.. _TQ:

Info Option -**TQ** (-**TimeRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the time a request was submitted. The request
time is set automatically when a request is submitted. Use this option
only if it needs to be changed.


.. _TR:

Info Option -**TR** (-**TimeReady**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the time when a request's data files are ready
online for download. The ready time is set automatically when a request
is processed. Use this option only if it needs to be changed.


.. _UA:

Info Option -**UA** (-**URL**) (Aliases: -**URLAddress**, -**URLLink**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -URLAddress|-URLLink) provides a URL link to use as
the initial webpage for the specified request.


.. _VP:

Info Option -**VP** (-**ValidPeriod**) (Alias: -**DataValidPeriod**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

defaults to 5 days. Sets the number of days the data
files remain staged online. After this period, requests are due to be
purged.


.. _WF:

Info Option -**WF** (-**WebFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the data file name staged online.


.. _WT:

Info Option -**WT** (-**WebFileType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the file type for the requested data; D-Data,
O-dOcument, and S-Software.



| :ref:`Back to Top <section5.2>`
| :ref:`Back to Table of Contents <index>`
