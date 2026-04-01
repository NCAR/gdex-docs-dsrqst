
.. _section5.1:

5.1 - Single-Value Info Options
=================================

A single-value Info option is used to pass one value into this application.
One value, and one only, must follow a single-value option; otherwise an
error message is displayed if no value or more than one value passed in.


.. _BP:

Info Option -**BP** (-**BatchProcess**) (Aliases: -**d**, -**DelayedMode**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

delayed mode execution. When
it presents, the **dsrqst** command is not executed right way, but the command
information is recorded into RDADB instead and the command is executed later
by the centralized daemon 'dscheck'. One or multiple host names can be specified
after option :ref:`-BP <BP>` to force the **dsrqst** command be executed on or not on the hosts.
For examples, '-d evans' to run on host 'evans'; '-d evans:mirage5' to run on
hosts 'evans' and 'mirage5'; and '-d \!migage1:mirage2' to run on all configured
hosts other than 'mirage1' and 'mirgae2'. Character '!' needs to be escaped for
passing in on command line. A upper limit for number of tries can also be passed
in with this options, 1 to 99, as '-d 2' for example. It default to 1 for cammand
of **dsrqst** if not specified.


.. _DV:

Info Option -**DV** (-**Divider**) (Aliases: -**Delimiter**, -**Separator**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

delimiter for separating
columns of multi-value Info options in input files. It is default to '<:>'.


.. _EL:

Info Option -**EL** (-**EmailLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

defaults to 20. If present with a value larger than 0,
**dsrqst** emails status of requests up to this number.


.. _ES:

Info Option -**ES** (-**EqualSign**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

for an equal sign of assigning one value to either a
single-value option or multi-value option in input files. It is defaulted
to '<=>'.


.. _FN:

Info Option -**FN** (-**FieldNames**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

for a string of single letter field names. Values of
the selected fields are retrieved per actions :ref:`-GC <GC>` (-GetControl), :ref:`-GP <GP>`
(-GetPartition), :ref:`-GR <GR>` (-GetRequest) and :ref:`-GF <GF>` (-GetFile). Values of default fields
are retrieved if this option is not specified. Valid field names are listed
in corresponding action sections.


.. _GU:

Mode Option -**GU** (-**GetUsage**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

gets usage information of given requests and records into
order metrics.


.. _GZ:

Mode Option -**GZ** (-**GMTZone**) (Aliases: -**GMT**, -**GreenwichZone**, -**UTC**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

uses GMT dates/times as
controlling times for processing request actions, instead of mountain time.


.. _LN:

Info Option -**LN** (-**LoginName**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

login name of the current user; it defaults to the current
login DSS specialist who starts execution of **dsrqst**. Set this option if you
try to run this utility for a specialist other than yourself.


.. _OF:

Info Option -**OF** (-**OutputFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

leading an output file name into which the output result
of this application is dumped. Output file format is similar to the format of
the input files. If this option is not given, the result is displayed on
screen.


.. _ON:

Info Option -**ON** (-**OrderNames**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

for a string of single letter field names use to order
the results of GET actions, :ref:`-GC <GC>` (-GetControl), :ref:`-GP <GP>` (-GetPartition), :ref:`-GR <GR>`
(-GetRequest) and :ref:`-GF <GF>` (-GetFile). Upper case is for Ascending order while
lower case is for Descending order. This option also force reordering of
data files displayed on the webpage per :ref:`Action option <section3>` :ref:`-SF <SF>` (-SetFile) when
:ref:`Mode option <section4>` :ref:`-RO <RO>` (-Reorder) is present but Info option :ref:`-WF <WF>` (-WebFile) is
omitted.


.. _PW:

Info Option -**PW** (-**PurgeWait**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

defaults to 7200 Seconds. It works for the Daemon mode
of **dsrqst**. When all due requests are purged already, this option value
tells **dsrqst** to wait this period of time before checking if any more
requests are due to purge again. It can be provided to set a different wait
interval, such as Second, Minute, Hour or Day. For example, ':ref:`-PW <PW>` 4H' is for 4
hours. A digital value only assumes a unit of Second, and ':ref:`-PW <PW>` 3600' means
3600S, for example.


.. _AO:

Info Option -**AO** (-**ActOption**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

for setting :ref:`Action <section3>` and :ref:`Mode options <section4>` in input files. It is
default to '<!>'.


.. _TS:

Info Option -**TS** (-**totalSize**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets default size in GB, the maximum disk space,
for **dsrqst** to stage temporary online data. Requests in queue are put on hold
if the total data online reaches this limit already, until older requests are
purged and data files are removed, so that free disk space is large enough for
next request to be processed.


.. _WH:

Info Option -**WH** (-**WebHomeDir**) (Aliases: -**WebHome**, -**DownloadHome**, -**OnlineHome**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specify a download directory on
RDA Server to stage the temporary data files for the download/archive activity.



| :ref:`Back to Top <section5.1>`
| :ref:`Back to Table of Contents <index>`
