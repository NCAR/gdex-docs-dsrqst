
.. _section5.2:

5.2 - Multi-Value Info Options
=================================

A multi-value Info option passes multiple values for one Info option to
**dsrqst**. At least one value must follow each multi-value option.


.. _AF:

Info Option -**AF** (-**ArchiveFormat**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

file archiving
formats of data files being staged onto GDEX Server for download. The file
archive format indicates post-processing of a data file. COS blocking on the
original data files — option values 'BI' (binary blocked), 'C1' or 'CH'
(ASCII/character blocked) — is automatically unblocked and the COS block
options are stripped from archive format values. Option value 'TAR' means a
tarred file, 'Z' a compressed file, 'GZ' a gzipped file, and 'BZ2' a file
compressed via bzip2. 'TAR.GZ', for example, means a file is tarred then
gzipped; order is important. The maximum format string length is 10;
additional characters are truncated.


.. _CC:

Info Option -**CC** (-**CarbonCopy**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

provides one or more additional email addresses to receive
Cc'd notification of request processing results. Carbon copy emails can be set
in a request control record via :ref:`Action <section3>` :ref:`-SC <SC>` (-SetControl) to control who is
Cc'd for an email notice after a request is successfully built. It defaults to
'S' for the associated specialist only. Multiple emails can be specified in a
single space delimited string up to 255 characters. Set it to empty to stop
carbon copy email.

For DECS specialists, login usernames are acceptable instead of full email
addresses; otherwise full email addresses are required for emails with domains
other than 'ucar.edu'.


.. _5.2_e9:

**EXAMPLE 9. To carbon copy 'schuster@ucar.edu' for processing results of request index 42, provide Info option -CC with login user name 'schuster':**

| **dsrqst** :ref:`BR <BR>` :ref:`-RI <RI>` 42 :ref:`-CC <CC>` schuster


.. _CI:

Info Option -**CI** (-**ControlIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

automatically generated control index for a request
control record when it is first added for a given dataset and/or group index.


.. _CM:

Info Option -**CM** (-**ControlMode**) (Alias: -**ControlMethod**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets request control mode for a
request control record. 'S' for specialist-controlled mode and 'A' for
automated request mode.


.. _DB:

Info Option -**DB** (-**Debug**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

turns on debug mode with specified information. This option
accepts up to 3 values: debug level, debug log file path, and debug log file
name. The debug level is mandatory. It can be a single integer value — for
example, 1000 logs debug messages for levels 1 to 1000 — or a range such as
200-1000, which logs messages from levels 200 to 1000. The default debug file
path is '${DSSHOME}/dssdb/log' and the default debug file name is 'pgdss.dbg'.
Provide the second and third values to override these defaults.


.. _DE:

Info Option -**DE** (-**Description**) (Aliases: -**Desc**, -**Note**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets readable descriptions for a
request control, request partition, request record, or data file. Multiple
lines are allowed for a description passed in from an input file specified by
Info option :ref:`-IF <IF>` (-InputFile).

Description for a request record is normally filled by passing 'rnote' to
online utility program 'dsrqst.php'. Use html tags <p> and </p> to start and
end the description for html text; without the leading <p>, html tags <pre>
and </pre> are added to preserve the original text display format on the
final request data output web page.


.. _DF:

Info Option -**DF** (-**DataFormat**) (Aliases: -**ContentFormat**, -**InternalFormat**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

data content
format of files being staged on GDEX Server for download. This is the content
format of data files. For example, NetCDF, IMMA, etc.


.. _DO:

Info Option -**DO** (-**DisplayOrder**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

display order indices of data files for a given request.
Ignored if :ref:`Mode option <section4>` :ref:`-RO <RO>` (-Reorder) is present.


.. _DP:

Info Option -**DP** (-**DatePurge**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets a date when a request is due for purging. A purge
date is automatically set when a request is processed. Use this option to
change it.


.. _DQ:

Info Option -**DQ** (-**DateRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the date a request was submitted. A request date is
automatically set when a request is submitted. Use this option only if it
needs to be changed.


.. _DR:

Info Option -**DR** (-**DateReady**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the date when a request's data files are ready online
for download. A ready date is automatically set when a request is processed.
Use this option only if it needs to be changed.


.. _DS:

Info Option -**DS** (-**Dataset**) (Aliases: -**Dsid**, -**DatasetID**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

provides one or multiple dataset IDs for some actions.


.. _EM:

Info Option -**EM** (-**Email**) (Aliases: -**RequestEmail**, -**RequestUserEmail**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets user email addresses in request records for users who
submit the requests.


.. _EN:

Info Option -**EN** (-**EmailNotice**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets a file name for a specified email notice in a
request control record or an individual request record, overriding the default
email notice template. If an email template file is set for a request control
record, all data requests under that control record share the same template.

The default email notice template file is $WebDownloadHome/notices/email_notice.
Get a copy and edit it to create your own customized email file. An absolute
path must be added to the file name if your template file is not in the
standard directory $WebDownloadHome/notices/.


.. _EO:

Info Option -**EO** (-**EmptyOutput**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets an empty output flag controlling whether an email
notice is sent to a public user whose request generated no output data. Valid
values: 'Y' sends email to the user for empty output; 'N' sends the email
notice to the specialist only. The default value is 'N'. A 'Y' can be set
in a request control record via :ref:`Action <section3>` :ref:`-SC <SC>` (-SetControl).


.. _EV:

Info Option -**EV** (-**Environments**) (Alias: -**Envs**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -Envs), specifies environment variables, in the
form VarName=VarValue separated by ',', to set when running **dsrqst** as a
batch job. The environment variables are set in the batch starting script.

An environment variable with a leading '!' is treated as an executable command
and its returned string is used as a dynamically created variable string.


.. _FC:

Info Option -**FC** (-**FileCount**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

count of data files requested in a single request.


.. _FD:

Info Option -**FD** (-**FileDate**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

date a data file was staged online.


.. _FS:

Info Option -**FS** (-**FileStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

file status in an individual data file record. Valid
statuses: 'R'equested, 'O'nline and 'E'rror.


.. _FT:

Info Option -**FT** (-**FileTime**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

time a data file was staged online.


.. _GI:

Info Option -**GI** (-**GroupIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

group indices. Relevant only if a dataset is divided into
groups. Valid group index values are 1, 2, 3, ...; 0 means actions for the
whole dataset and is the default if not provided explicitly.


.. _HN:

Info Option -**HN** (-**HostName**) (Alias: -**HostMachine**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

host machine names to set in request control records or
individual request records. One or multiple host names can be set in a
request control record. The hostname information in request control records
controls on which machines the associated requests can or cannot be processed.
An individual request can only be built on a specified machine if its host
name field is set.


.. _5.2_e10:

**EXAMPLE 10. Set request control record of Control Index 67 of d540000 to restrict its associated requests to be processed on bross and evans only:**

| **dsrqst** :ref:`SC <SC>` :ref:`-CI <CI>` 67 :ref:`-HN <HN>` bross:evans

Add '!' in front of the host names, as :ref:`-HN <HN>` \!bross:evans, to restrict
the associated requests to all available machines other than bross and
evans. Character '!' must be escaped on the command line.


.. _IF:

Info Option -**IF** (-**InputFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

input file names; one or multiple file names may be given
on the command line. Input files hold all valid options and associated values
for Info options to pass to **dsrqst** for execution.

In an input file, lines starting with '#' are treated as comments.
Option names can be given in short, long, or alias form. :ref:`Action <section3>` and :ref:`Mode <section4>`
options are given in the format OptionName<!>. Single-value assignments use
the format OptionName<=>OptionValue. One option is given per line.
A different setting sign for :ref:`Action <section3>` and :ref:`Mode options <section4>` can be provided via Info
option -AO (-ActOption, default '<!>'); a different equal sign for
single-value assignments can be provided via Info option :ref:`-ES <ES>` (-EqualSign,
default '<=>').  Multi-value assignments use columns delimited by the
separator specified per option -SP (-Separator, default '<:>'). The first
line is the column title line of multi-value option names; the rest holds
values corresponding to each column title. Value information continues to the
end of the file or stops when a new column name line or another single-value
assignment appears. If the last column is a multi-line value field, an
additional separator must be appended to each line, including the column
title line, to terminate lines properly.


.. _LF:

Info Option -**LF** (-**LocalFile**) (Alias: -**LocFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

local file names that are pre-processed
files for customized data.


.. _LM:

Info Option -**LM** (-**RequestLimit**) (Alias: -**UpLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

0 means to use the system default 40 GB limit. Sets the
upper limit in GB of data that can be requested at one time. This limit should
be checked and validated before a request is submitted.


.. _MO:

Info Option -**MO** (-**Modules**) (Alias: -**Mods**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -Mods), specifies module names, separated by ',',
to load when running **dsrqst** as a batch job. The modules are set in the
batch starting script.

A module name with a leading '!' is treated as an executable command and its
returned string is used as a dynamically created module name string.


.. _MP:

Info Option -**MP** (-**MaxPeriod**) (Alias: -**MaxrequestPeriod**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the maximum default request period on the request
interface to prevent a default large request job. Valid example values are
5Y or 10M for periods of 5 Years or 10 Months, respectively.


.. _MR:

Info Option -**MR** (-**MaxRequest**) (Alias: -**MaximumRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

max number of outstanding
requests allowed for a single dsrqst control record from an individual user.
Defaults to 20. A positive value, such as 10, can be set via :ref:`Action <section3>` :ref:`-SC <SC>`
(-SetControl) in the request control record. If the max number is reached,
additional requests are denied until outstanding requests are purged or deleted.


.. _OB:

Info Option -**OB** (-**OrderBy**) (Alias: -**OrderByPattern**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

temporal patterns for ordering a
filelist according to the string values of field names specified per option
:ref:`-ON <ON>` (-OrderNames). 'YYYYmon', for example, means ordering based on a 4-digit
year and three-letter lowercase month names such as 'jan', 'feb', etc. Check
option :ref:`-ON <ON>` (-OrderNames) for examples of ordering files by temporal patterns.


.. _OR:

Info Option -**OR** (-**ORiginFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

original file name with path set in source file record.
This value is used if the source link is empty.


.. _OT:

Info Option -**OT** (-**SourceType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

original data type; 'W' for data on Web Server.


.. _PC:

Info Option -**PC** (-**ProcessCommand**) (Aliases: -**Command**, -**SpecialCommand**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets customized command to build
requests, process partitions, or process individual files.


.. _PF:

Info Option -**PF** (-**PartitionFlag**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets partition command call flag for subset request.
N - call customized command in the form 'CustomizedCommand RequestIndex' to
initialize the filelist only, with no further command calls during partition
process or final request build; P - call customized command in the form
'CustomizedCommand RequestIndex WorkPath PartitionIndex' to also process
partition data; F - call customized command in the form
'CustomizedCommand RequestIndex WorkPath' to build request data finally;
B - for both P and F.


.. _PI:

Info Option -**PI** (-**PartitionIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

automatically generated partition index for a request
partition record when it is first added.


.. _PL:

Info Option -**PL** (-**PartitionLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the number of files per partition in request
control configuration via action :ref:`-SC <SC>` (-SetControl).


.. _PZ:

Info Option -**PZ** (-**PartitionsiZe**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the data size per partition in request control
configuration via action :ref:`-SC <SC>` (-SetControl).


.. _PO:

Info Option -**PO** (-**Priority**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

process priority of queued requests. Default value is 10;
1 is the highest priority.


.. _PS:

Info Option -**PS** (-**PartitionStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

partition status for request partition record. 'I'
for an inclusive condition and 'E' for an exclusive condition.


.. _QS:

Info Option -**QS** (-**QSubOptions**) (Alias: -**PBSOptions**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -PBSOptions), specifies options for running
**dsrqst** as a batch job via qsub on PBS nodes. The qsub options must be
quoted on the command line, such as :ref:`-QS <QS>` '-l walltime=12:00:00'.

A qsub option string with a leading '!' is treated as an executable command
and its returned string is used as a dynamically created qsub option string.


.. _RF:

Info Option -**RF** (-**RequestInfo**) (Alias: -**RequestInformation**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets additional request
information for a request record, such as detailed subsetting information.
Request information is normally filled by passing 'rinfo' to online utility
program 'dsrqst.php'.


.. _RI:

Info Option -**RI** (-**RequestIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

automatically generated request index for a request
record when it is first created upon user submission via the web interface.


.. _RL:

Info Option -**RL** (-**RequestLocation**) (Aliases: -**RequestHome**, -**RequestPath**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specifies a
customized location to stage the request result.


.. _RN:

Info Option -**RN** (-**RequestName**) (Alias: -**RequestID**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

request name or ID, automatically set as a combination
of the user's uppercased last name and the request index.


.. _RO:

Mode Option -**RO** (-**ResetOrder**) (Alias: -**Reorder**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

resets the display orders of the data
files in a request to match the order in which data file records are given
for :ref:`Action <section3>` :ref:`-SF <SF>` (-SetFile). Another way of reordering the data files is to
explicitly provide display order index values per Info option :ref:`-DO <DO>`
(-DisplayOrder).


.. _RS:

Info Option -**RS** (-**RequestStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

request status for an individual request record. Valid
statuses: 'W'ait, 'Q'ueue, 'O'nline, 'I'nterrupted, 'H'old, 'P'urge and 'E'rror.


.. _RT:

Info Option -**RT** (-**RequestType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

type of request. Valid types: S - Subset data,
T - Subset/Format Conversion, F - Format Conversion (Web), P - Data Plotting,
C - Customized Data, D - CDP link, N - NCARDAP (THREDDS) Data Server,
Q - Database Query, and R - Realtime DataDownload.


.. _SI:

Info Option -**SI** (-**SizeInput**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

size of original data required for a request.


.. _SL:

Info Option -**SL** (-**SourceLink**) (Alias: -**SourceID**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

file name of original data. For type 'W', it is a web file.


.. _SN:

Info Option -**SN** (-**Specialist**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the login name of a specialist in GDEXDB for request
control records and request records. When the requests are handled, the system
login name is validated against the one saved in GDEXDB; request handling
processes — both building and purging — are blocked if they do not match.


.. _SQ:

Info Option -**SQ** (-**SizeRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

size of data of all files requested for an individual
request.


.. _SZ:

Info Option -**SZ** (-**Size**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

file size of each data file online.


.. _TA:

Info Option -**TA** (-**TarFlag**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a field in request control and request records. 'Y' to tar
small request files, or 'N' for no.


.. _TF:

Info Option -**TF** (-**ToFormat**) (Aliases: -**OutputFormat**, -**ProductFormat**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

':' delimited string
of data format(s) for output files staged on GDEX Server for download after
format conversion or subsetting. These are content formats of output data
files. For example, NETCDF:GRIB.

NOTE: the output format(s) set via this option must be supported by the
underlying format conversion commands for full data files or subsetting
outputs.


.. _TI:

Info Option -**TI** (-**TarfileIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

automatically generated tar file index for a tar file
record when small request files are tarred.


.. _TP:

Info Option -**TP** (-**TimePurge**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets a time when a request is due for purging. A purge
time is automatically set when a request is processed. Use this option to
change it.


.. _TQ:

Info Option -**TQ** (-**TimeRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the time a request was submitted. A request time is
automatically set when a request is submitted. Use this option only if it
needs to be changed.


.. _TR:

Info Option -**TR** (-**TimeReady**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the time when a request's data files are ready online
for download. A ready time is automatically set when a request is processed.
Use this option only if it needs to be changed.


.. _UA:

Info Option -**UA** (-**URL**) (Aliases: -**URLAddress**, -**URLLink**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

provides a URL link as an initial
webpage for the specified request.


.. _VP:

Info Option -**VP** (-**ValidPeriod**) (Alias: -**DataValidPeriod**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

defaults to 5 days. Sets the number of days the data
files are staged online. After this period, requests are due to be purged.


.. _WF:

Info Option -**WF** (-**WebFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

data file name staged online.


.. _WH:

Info Option -**WH** (-**WebHomeDir**) (Aliases: -**WebHome**, -**DownloadHome**, -**OnlineHome**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specifies a download
directory on GDEX Server to stage temporary data files for the
download/archive activity.


.. _WT:

Info Option -**WT** (-**WebFileType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

file types for the requested data; D-Data, O-dOcument
and S-Software.



| :ref:`Back to Top <section5.2>`
| :ref:`Back to Table of Contents <index>`
