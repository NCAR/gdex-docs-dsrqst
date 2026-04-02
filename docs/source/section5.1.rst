
.. _section5.1:

5.1 - Single-Value Info Options
=================================

A single-value Info option is used to pass one value into this application.
One value, and one only, must follow a single-value option; otherwise an
error message is displayed if no value or more than one value is passed in.


.. _BP:

Info Option -**BP** (-**BatchProcess**) (Aliases: -**d**, -**DelayedMode**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

delayed mode execution. When
present, the **dsrqst** command is not executed right away, but the command
information is recorded into GDEXDB instead and the command is executed later
by the centralized daemon `dscheck <https://gdex-docs-dscheck.readthedocs.io>`_. One or multiple host names can be specified
after option :ref:`-BP <BP>` to force the **dsrqst** command to be executed on or not on the hosts.
For examples, '-d evans' to run on host 'evans'; '-d evans:mirage5' to run on
hosts 'evans' and 'mirage5'; and '-d \!mirage1:mirage2' to run on all configured
hosts other than 'mirage1' and 'mirage2'. Character '!' needs to be escaped for
passing in on command line. An upper limit for number of tries can also be passed
in with this option, 1 to 99, as '-d 2' for example. It defaults to 1 for a command
of **dsrqst** if not specified.


.. _DV:

Info Option -**DV** (-**Divider**) (Aliases: -**Delimiter**, -**Separator**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

delimiter for separating
columns of multi-value Info options in input files. It defaults to '<:>'.


.. _EL:

Info Option -**EL** (-**EmailLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

defaults to 20. If present with a value larger than 0,
**dsrqst** emails status of requests up to this number.


.. _ES:

Info Option -**ES** (-**EqualSign**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specifies the equal sign used to assign a value to either a
single-value option or multi-value option in input files. It defaults to '<=>'.


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

specifies an output file name into which the output result
of this application is written. Output file format is similar to the format of
the input files. If this option is not given, the result is displayed on
screen.


.. _ON:

Info Option -**ON** (-**OrderNames**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a string of single-letter field names used to order
the results of GET actions, :ref:`-GC <GC>` (-GetControl), :ref:`-GP <GP>` (-GetPartition), :ref:`-GR <GR>`
(-GetRequest) and :ref:`-GF <GF>` (-GetFile). Upper case is for ascending order while
lower case is for descending order. This option also forces reordering of
data files displayed on the webpage per :ref:`Action option <section3>` :ref:`-SF <SF>` (-SetFile) when
:ref:`Mode option <section4>` :ref:`-RO <RO>` (-Reorder) is present but Info option :ref:`-WF <WF>` (-WebFile) is
omitted.


.. _PW:

Info Option -**PW** (-**PurgeWait**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

defaults to 7200 seconds. It works for the daemon mode
of **dsrqst**. When all due requests have been purged, this option value tells
**dsrqst** to wait this period of time before checking if any more requests are
due to be purged again. It can be provided to set a different wait interval,
such as seconds, minutes, hours or days. For example, ':ref:`-PW <PW>` 4H' is for 4
hours. A numeric value assumes a unit of seconds, so ':ref:`-PW <PW>` 3600' means 3600S.


.. _AO:

Info Option -**AO** (-**ActOption**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

for setting :ref:`Action <section3>` and :ref:`Mode options <section4>` in input files. It
defaults to '<!>'.


.. _TS:

Info Option -**TS** (-**totalSize**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets default size in GB, the maximum disk space,
for **dsrqst** to stage temporary online data. Requests in queue are put on hold
if the total data online already reaches this limit, until older requests are
purged and data files are removed, so that there is enough free disk space for
the next request to be processed.


.. _WH:

Info Option -**WH** (-**WebHomeDir**) (Aliases: -**WebHome**, -**DownloadHome**, -**OnlineHome**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specify a download directory on
GDEX Server to stage the temporary data files for the download/archive activity.



| :ref:`Back to Top <section5.1>`
| :ref:`Back to Table of Contents <index>`
