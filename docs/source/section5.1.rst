
.. _section5.1:

5.1 - Single-Value Info Options
=================================

A single-value Info option passes one value to **dsrqst**. One value, and one
only, must follow a single-value option; an error message is displayed if no
value or more than one value is passed in.


.. _BP:

Info Option -**BP** (-**BatchProcess**) (Aliases: -**d**, -**DelayedMode**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

delayed mode execution. When
present, the **dsrqst** command is not executed immediately; instead, the command
information is recorded into GDEXDB and executed later by the centralized
daemon `dscheck <https://gdex-docs-dscheck.readthedocs.io>`_. One or multiple host names can be specified after option :ref:`-BP <BP>`
to force the **dsrqst** command to run on or not on those hosts. For example,
'-d evans' to run on host 'evans'; '-d evans:mirage5' to run on hosts 'evans'
and 'mirage5'; and '-d \!mirage1:mirage2' to run on all configured hosts other
than 'mirage1' and 'mirage2'. Character '!' must be escaped on the command
line. An upper limit for number of tries, 1 to 99, can also be passed in with
this option, as '-d 2' for example. It defaults to 1 if not specified.


.. _DV:

Info Option -**DV** (-**Divider**) (Aliases: -**Delimiter**, -**Separator**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

delimiter for separating
columns of multi-value Info options in input files. It defaults to '<:>'.


.. _EL:

Info Option -**EL** (-**EmailLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

defaults to 20. When present with a value larger than 0,
**dsrqst** emails status of up to this many requests.


.. _ES:

Info Option -**ES** (-**EqualSign**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specifies the equal sign used to assign a value to a
single-value or multi-value option in input files. It defaults to '<=>'.


.. _FN:

Info Option -**FN** (-**FieldNames**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a string of single-letter field names. Values of the
selected fields are retrieved by actions :ref:`-GC <GC>` (-GetControl), :ref:`-GP <GP>`
(-GetPartition), :ref:`-GR <GR>` (-GetRequest) and :ref:`-GF <GF>` (-GetFile). Default fields are
retrieved if this option is not specified. Valid field names are listed in the
corresponding action sections.


.. _GU:

Mode Option -**GU** (-**GetUsage**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

gets usage information of given requests and records it in
order metrics.


.. _GZ:

Mode Option -**GZ** (-**GMTZone**) (Aliases: -**GMT**, -**GreenwichZone**, -**UTC**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

uses GMT dates/times as
controlling times for processing request actions, instead of mountain time.


.. _LN:

Info Option -**LN** (-**LoginName**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

login name of the current user; defaults to the current
DECS specialist who starts **dsrqst**. Set this option to run the utility for a
specialist other than yourself.


.. _OF:

Info Option -**OF** (-**OutputFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specifies an output file name for writing the output
result of this application. Output file format matches the format of input
files. If this option is not given, the result is displayed on screen.


.. _ON:

Info Option -**ON** (-**OrderNames**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a string of single-letter field names for ordering results
of GET actions: :ref:`-GC <GC>` (-GetControl), :ref:`-GP <GP>` (-GetPartition), :ref:`-GR <GR>` (-GetRequest) and
:ref:`-GF <GF>` (-GetFile). Upper case is for ascending order; lower case is for descending
order. This option also forces reordering of data files displayed on the
webpage per :ref:`Action option <section3>` :ref:`-SF <SF>` (-SetFile) when :ref:`Mode option <section4>` :ref:`-RO <RO>` (-Reorder) is
present but Info option :ref:`-WF <WF>` (-WebFile) is omitted.


.. _PW:

Info Option -**PW** (-**PurgeWait**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

defaults to 7200 seconds. Works in daemon mode of
**dsrqst**. After all due requests have been purged, **dsrqst** waits this period
before checking again for requests due to be purged. A different wait interval
can be set using seconds, minutes, hours, or days. For example, ':ref:`-PW <PW>` 4H' for
4 hours. A numeric value assumes seconds, so ':ref:`-PW <PW>` 3600' means 3600S.


.. _AO:

Info Option -**AO** (-**ActOption**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

for setting :ref:`Action <section3>` and :ref:`Mode options <section4>` in input files. It
defaults to '<!>'.


.. _TS:

Info Option -**TS** (-**totalSize**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the default size in GB — the maximum disk space —
for **dsrqst** to stage temporary online data. Requests in queue are put on
hold if the total data online reaches this limit, until older requests are
purged and data files are removed, freeing enough disk space for the next
request to be processed.


.. _WH:

Info Option -**WH** (-**WebHomeDir**) (Aliases: -**WebHome**, -**DownloadHome**, -**OnlineHome**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specifies a download
directory on GDEX Server to stage temporary data files for the
download/archive activity.



| :ref:`Back to Top <section5.1>`
| :ref:`Back to Table of Contents <index>`
