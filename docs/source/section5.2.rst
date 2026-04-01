
.. _section5.2:

5.2 - Multi-Value Info Options
=================================

A multi-value Info option is used to pass multiple values for one Info option
into **dsrqst**. At lease one value must follow each multi-value option.


.. _AF:

Info Option -**AF** (-**ArchiveFormat**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

for file
archiving formats of data files being staged onto RDA Server for download.
The file archive format indicates post process of a data file. COS blocking
on the original data files, for option values, 'BI' - binary blocked, 'C1' or
'CH' - ASCII/character blocked, are automatically unblocked for the data files
and the the COS block options are stripped from archive format values. Option
value 'TAR' means a tarred file, 'Z' means a compressed file, 'GZ' means a
gzipped file, and 'BZ2' means a file is compressed via bzip2. 'TAR.GZ', for
example, means a file is tarred and then gzipped; the order is important. The
maximum length of format string is 10. Additional characters are truncated
for length longer than 10.


.. _CC:

Info Option -**CC** (-**CarbonCopy**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

provides additional one or multiple email addresses on
command line to receive Cc'd email notification of the request processing
results. The carbon copy emails can be set into Request Control record via
action :ref:`-SC <SC>` (-SetControl) to control who will be Cc'ed for an email notice
after a request is successfully built. It is defaulted to 'S' for the
associated specialist only. Multiple emails can be specified in a single
space-delimited string up to 255 characters. Set it to empty to stop carbon
copy email.

For DSS specialists, login user names themselves are acceptable instead of
full email address; otherwise full email addresses are required for emails
with domains other than 'ucar.edu'.


.. _5.2_e9:

**EXAMPLE 9. To make a carbon copy email to 'schuster@ucar.edu' for processing results of request index 42, provide Info option -CC with login user name 'schuster':**

| **dsrqst** :ref:`BR <BR>` :ref:`-RI <RI>` 42 :ref:`-CC <CC>` schuster


.. _CI:

Info Option -**CI** (-**ControlIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

automatically generated control index for a request
control record when it is first added for a given dataset and/ or group index.


.. _CM:

Info Option -**CM** (-**ControlMode**) (Alias: -**ControlMethod**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets request control :ref:`Mode <section4>` for a
request control record. 'S' for specialist-control mode and 'A' for automated
request mode.


.. _DB:

Info Option -**DB** (-**Debug**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

to turn on debug mode with specified information. This option
provides up to 3 values, they are Debug Level, debug log file path and debug
log file name. The debug level is mandatory for this option. It can be a
single integer value, for example, 1000 means to log debug messages for debug
levels 1 to 1000; or a range of values, for example, 200-1000 means to log
debug messages from debug levels 200 to 1000. The default debug file path is
'$DSSHOME}/dssdb/log' and the default debug file name is 'mydss.dbg'. Provides
the second and third values for this option to override the default ones
respectively.


.. _DE:

Info Option -**DE** (-**Description**) (Aliases: -**Desc**, -**Note**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets readable descriptions for a request
control, request partition, request record or a data file. Multiple lines are
allowed for a description if it is passed in from an input file specified by
Info option :ref:`-IF <IF>` (-InputFile).

Description for a request record is normally filled by passing 'rnote' to online
utility program 'dsrqst.php'. Use html tags <p> and </p> to start and end the
description for html text; without the leading <p>, html tags <pre> and </pre>
are added to preserve the original text display format when it is displayed on
final request data output web page.


.. _DF:

Info Option -**DF** (-**DataFormat**) (Aliases: -**ContentFormat**, -**InternalFormat**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

data content
format of files being staged on RDA Server for download. This is content
format of data files. For examples, NetCDF, IMMA and etc.


.. _DO:

Info Option -**DO** (-**DisplayOrder**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

for display order indices of data files of a given
request. This Info option is ignored if :ref:`Mode option <section4>` :ref:`-RO <RO>` (-Reorder) is present.


.. _DP:

Info Option -**DP** (-**DatePurge**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets a date for a request to be due for purging. A purge
date is automatically set for a request when it is processed. Use this option
to change it.


.. _DQ:

Info Option -**DQ** (-**DateRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets a date for a request when it is submitted. A request
date is automatically set for a request when it is submitted. Use this option
only if it needs to be changed.


.. _DR:

Info Option -**DR** (-**DateReady**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets a date for a request when its data files are ready
online for download. A ready  date is automatically set for a request when it
is processed. Use this option only if it needs to be changed.


.. _DS:

Info Option -**DS** (-**Dataset**) (Aliases: -**Dsid**, -**DatasetID**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

provides one or multiple IDs for some actions.


.. _EM:

Info Option -**EM** (-**Email**) (Aliases: -**RequestEmail**, -**RequestUserEmail**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets user email addresses in request records to for users
who submit the requests.


.. _EN:

Info Option -**EN** (-**EmailNotice**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

set a file name for s specified email notice in a
request control record or an individual request record, instead of
the default template of email notice. If a specified email template file is
set for a request control record, all data requests under the control record
will share the same email template file.

The default email notice template file is $WebDownloadHome/notices/email_notice.
Get a copy and edit it to have your own customized email file. Absolute path must
be added to the file name if your template file is not in the standard directory
$WebDownloadHome/notices/.


.. _EO:

Info Option -**EO** (-**EmptyOutput**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets a empty output flag to control if an email notice is sent
to public user who requested data but no data generated for output. Valid values
are: 'Y' allows sending email to user for empty output, and 'N' tells dsrqst
to send email notice to specialist only for empty output. The default value is 'N'.
A 'Y' can be set into request control record via :ref:`Action <section3>` :ref:`-SC <SC>` (-SetControl).


.. _EV:

Info Option -**EV** (-**Environments**) (Alias: -**Envs**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -Envs), specifies environment variables, in form of
VarName=VarValue and separated by ',', needed to be set to run **dsrqst** as a batch
job. The environment varaibles will be set in the batch starting script.

For environment variables with a leading '!' it is treated as an executable
command and its returned string is used as a dynamically created variable string


.. _FC:

Info Option -**FC** (-**FileCount**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

count of data files requested in a single request.


.. _FD:

Info Option -**FD** (-**FileDate**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

date of a data file staged online.


.. _FS:

Info Option -**FS** (-**FileStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

file status in a individual data file record. Valid
status, 'R'equested, 'O'nline and 'E'rror.


.. _FT:

Info Option -**FT** (-**FileTime**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

time of a data file staged online.


.. _GI:

Info Option -**GI** (-**GroupIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

for group indices. This is considered only if a dataset
is divided further into groups. Valid group index values are 1, 2, 3, ....,
while 0 means actions for the whole dataset which is the default index value
if it is not provide explicitly.


.. _HN:

Info Option -**HN** (-**HostName**) (Alias: -**HostMachine**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

host machine names to set into request control records or
individual request records. One or multiple host names can be set into a
request control record. The hostname information in request control records
limits the associated requests can, or cannot, be processed on the specified
machines. An individual request can only be built on a specified machine if
its host name field is set.


.. _5.2_e10:

**EXAMPLE 10. Set request control record of Control Index 67 of d540000 to control its associated requests to be processed on bross and evans only:**

| **dsrqst** :ref:`SC <SC>` :ref:`-CI <CI>` 67 :ref:`-HN <HN>` bross:evans

Add '!' in front of the host names, as :ref:`-HN <HN>` \!bross:evans, to control the
associated requests to be built on all available machines other than bross
and evans. Character '!' needs to be escaped for passing in on command line.


.. _IF:

Info Option -**IF** (-**InputFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

for input file names; one or multiple file names may be
given on command line. Input files are used to hold all valid options and the
associated values of Info options that need to be passed in for execution of
**dsrqst**.

In a input file, lines start with sign '#' are considered as comments;
Option Names can be given either short, long or alias names. :ref:`Action <section3>` and :ref:`Mode <section4>`
options are given in format of OptionName<!>. Single value Assignment is
given in format of OptionName<=>OptionValue. One option is given on each line.
Different setting sign of :ref:`Action <section3>` and :ref:`Mode options <section4>` can be provided by Info
option -AO (-ActOption, default to <!>); and different equal sign of single
value assignment can be provided by Info option :ref:`-ES <ES>`, (-EqualSign, default to
'<=>'). Multi-value assignments can be given in columns delimited with
separator specified per option -SP (-Separator, default to '<:>'). It starts
with a column title line for multi-value option names and the rest holds
values corresponding to each column titles. The value information stops at
the end of the file or when a new column name line or another single value
assignment appears. If the last column is a multi-line value field, an
additional separator must be appended for each line, including the column
title line to end lines properly.


.. _LF:

Info Option -**LF** (-**LocalFile**) (Alias: -**LocFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

local file names that are pre-processed
files for customized data.


.. _LM:

Info Option -**LM** (-**RequestLimit**) (Alias: -**UpLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

0 means to use system default 40 GB limit. It sets
the number of GB for up limit of data that can berequested each time. This
limit should be checked and and validated before a request is submitted.


.. _MO:

Info Option -**MO** (-**Modules**) (Alias: -**Mods**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -Mods), specifies module names, separated by ',',
needed to be loaded to run **dsrqst** as a batch job. The modules will be set
in the batch starting script.

For module names with a leading '!' it is treated as an executable command
and its returned string is used as a dynamically created module name string.


.. _MP:

Info Option -**MP** (-**MaxPeriod**) (Alias: -**MaxrequestPeriod**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

it sets the maximum default request period on request
interface to avoid of a default large request job. Valid example values
are 5Y or 10M for periods of 5 Years or 10 Months, respectively.


.. _MR:

Info Option -**MR** (-**MaxRequest**) (Alias: -**MaximumRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

max number of outstanding requests
allowed for a single dsrqst control record from an individual user. It defaults
to 20. A positive value, such as 10, can be set via :ref:`Action <section3>` :ref:`-SC <SC>` (-SetControl)
into request control record. If the max number is reached, additional requests
are denied until any of the outstanding requests are purged or deleted.


.. _OB:

Info Option -**OB** (-**OrderBy**) (Alias: -**OrderByPattern**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

temporal patterns used to order
filelist according to the string values of field names specified per
option :ref:`-ON <ON>` (-OrderNames). 'YYYYmon', for example, means the order should
be based on on 4 digit year and three letter lower case month names as 'jan',
'feb', and etc. Check option :ref:`-ON <ON>` (-OrderNames) for example of ordering
files by temporal patterns.


.. _OR:

Info Option -**OR** (-**ORiginFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

original file name with path se in source file record. This
value is used if the source link is empty.


.. _OT:

Info Option -**OT** (-**SourceType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

original data type, 'M' for data on HPSS.


.. _PC:

Info Option -**PC** (-**ProcessCommand**) (Aliases: -**Command**, -**SpecialCommand**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets customized command to
build requests, process partitions or process individual files.


.. _PF:

Info Option -**PF** (-**PartitionFlag**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets partition command call flag for subsetting request,
N - call customized command, in form of 'CustomizedCommand RequestIndex',
to initialize filelist only, no need further cammand calls during partion
process or final request build; P - call customized command, in form of
'CustomizedCommand RequestIndex WorkPath PartionIndex', too to process
partition data; F - call customized command , in form of
'CustomizedCommand RequestIndex WorkPath', to built request data finally;
B - for both P and F.


.. _PI:

Info Option -**PI** (-**PartitionIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

automatically generated partition index for a request
partition record when it is first added.


.. _PL:

Info Option -**PL** (-**PartitionLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets number of files for each partition in reuqest
control configuration via action :ref:`-SC <SC>` (-SetControl).


.. _PZ:

Info Option -**PZ** (-**PartitionsiZe**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets data size for each partition in reuqest
control configuration via action :ref:`-SC <SC>` (-SetControl).


.. _PO:

Info Option -**PO** (-**Priority**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

process priorities of the queued requests. Default value
is 10. The highest value is 1.


.. _PS:

Info Option -**PS** (-**PartitionStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

partition status for request partition record. 'I' for
an inclusive condition and 'E' for an exclusive condition.


.. _QS:

Info Option -**QS** (-**QSubOptions**) (Alias: -**PBSOptions**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -PBSOptions), specifies options to run **dsrqst** as
a batch job via qsub on PBS nodes. The qsub options must be quoted when presented
on the command line, such as, :ref:`-QS <QS>` '-l walltime=12:00:00'.

For qsub options with a leading '!' it is treated as an executable command
and its returned string is used as a dynamically created qsub option string.


.. _RF:

Info Option -**RF** (-**RequestInfo**) (Alias: -**RequestInformation**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets additional request
information for a request record, such as detailed subsetting information.
The request information is normally filled by passing 'rinfo' to online
utility program 'dsrqst.php'.


.. _RI:

Info Option -**RI** (-**RequestIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

automatically generated request index for a request
record when it is first added when a request is submitted by a user per
web interface of data request.


.. _RL:

Info Option -**RL** (-**RequestLocation**) (Aliases: -**RequestHome**, -**RequestPath**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specifies a
customized location to stage the request result.


.. _RN:

Info Option -**RN** (-**RequestName**) (Alias: -**RequestID**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

request name or ID, it is automatically set as combination
of upper case string of user last name and the request index.


.. _RO:

Mode Option -**RO** (-**ResetOrder**) (Alias: -**Reorder**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

when present, resets the display orders
of the data file lists of a request as the order data file records are given
for actions :ref:`-SF <SF>` (-SetFile). Another way of reordering the data files is to
provide explicitly display order index values per Info option :ref:`-DO <DO>`
(-DisplayOrder).


.. _RS:

Info Option -**RS** (-**RequestStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

request status for an individual request record. Valid
status, 'W'ait, 'Q'ueue, 'O'nline, 'I'nterrupted, 'H'old, 'P'urge and 'E'rror.


.. _RT:

Info Option -**RT** (-**RequestType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

type of request. Valid types, M - HPSS data, S - Subset data,
T - Subset/Format Conversion, F - Format Conversion (Web), H - Format Conversion
(HPSS), P - Data Plotting, C - Customized Data, D - CDP link, N - NCARDAP
(THREDDS) Data Server, Q - Database Query, and R - Realtime Data Download.


.. _SI:

Info Option -**SI** (-**SizeInput**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

size of original data required for a request.


.. _SL:

Info Option -**SL** (-**SourceLink**) (Alias: -**SourceID**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a file name of original data. For type 'M' request,
this is a HPSS file name; for type 'W', it is a web file.


.. _SN:

Info Option -**SN** (-**Specialist**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

set login name of a specialist into RDADB for request
control records and request records. When the requests are handled, the system
login name is validated against the one saved one in RDADB; the request
handling processes, both building and purging requests, are blocked if them
are not match.


.. _SQ:

Info Option -**SQ** (-**SizeRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

size of data of all files requested for an individual
request.


.. _SZ:

Info Option -**SZ** (-**Size**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

file size each data file online.


.. _TA:

Info Option -**TA** (-**TarFlag**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a field in request control and reuqest record, 'Y' to tar small
request files, or 'N' for not.


.. _TF:

Info Option -**TF** (-**ToFormat**) (Aliases: -**OutputFormat**, -**ProductFormat**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

string of ':' delimited
data format(s) of output files being staged on RDA Server for download after
conversion of data files or subsetting results. These are content formats of
output data files. For examples, NETCDF:GRIB, and etc.

NOTE: the output format(s) set via this option must be supported by
the underline format conversion commands for full data files or subsetting
outputs.


.. _TI:

Info Option -**TI** (-**TarfileIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

automatically generated tar file index for a tar file
record when small request files are tarred.


.. _TP:

Info Option -**TP** (-**TimePurge**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets a time for a request to be due for purging. A purge
time is automatically set for a request when it is processed. Use this option
to change it.


.. _TQ:

Info Option -**TQ** (-**TimeRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets a time for a request when it is submitted. A request
time is automatically set for a request when it is submitted. Use this option
only if it needs to be changed.


.. _TR:

Info Option -**TR** (-**TimeReady**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets a time for a request when its data files are ready
online for download. A ready  time is automatically set for a request when it
is processed. Use this option only if it needs to be changed.


.. _UA:

Info Option -**UA** (-**URL**) (Aliases: -**URLAddress**, -**URLLink**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

provide a URL link as an initial
webpage for this specified request.


.. _VP:

Info Option -**VP** (-**ValidPeriod**) (Alias: -**DataValidPeriod**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

defaults to 5 days. It sets the number of days the data
files are staged online. After this period, requests are due to be purged.


.. _WF:

Info Option -**WF** (-**WebFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

data file name staged online.


.. _WH:

Info Option -**WH** (-**WebHomeDir**) (Aliases: -**WebHome**, -**DownloadHome**, -**OnlineHome**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specify a download directory on
RDA Server to stage the temporary data files for the download/archive activity.


.. _WT:

Info Option -**WT** (-**WebFileType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

file types for the requested data; D-Data, O-dOcument
and S-Software.



| :ref:`Back to Top <section5.2>`
| :ref:`Back to Table of Contents <index>`
