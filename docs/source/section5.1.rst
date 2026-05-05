
.. _section5.1:

5.1 - Single-Value Info Options
=================================

A single-value Info option passes exactly one value to **dsrqst**. An error
message is displayed if no value or more than one value is given.


.. _BP:

Info Option -**BP** (-**BatchProcess**) (Aliases: -**d**, -**DelayedMode**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

delayed-mode execution.
When present, the **dsrqst** command is not executed immediately; instead,
the command information is recorded in GDEXDB and executed later by the
centralized daemon `dscheck <https://gdex-docs-dscheck.readthedocs.io>`_. One or more host names can follow option :ref:`-BP <BP>`
to force the **dsrqst** command to run on, or to avoid, those hosts. For
example, '-d evans' runs on host 'evans'; '-d evans:mirage5' runs on
hosts 'evans' and 'mirage5'; '-d \!mirage1:mirage2' runs on every
configured host other than 'mirage1' and 'mirage2'. The character '!'
must be escaped on the command line. An upper limit on the number of
tries (1 to 99) can also be supplied via this option, for example '-d 2'.
It defaults to 1 if not specified.


.. _DV:

Info Option -**DV** (-**Divider**) (Aliases: -**Delimiter**, -**Separator**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

delimiter for separating
columns of multi-value Info options inside input files. Defaults to '<:>'.


.. _EL:

Info Option -**EL** (-**EmailLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

defaults to 20. When present with a value greater than
0, **dsrqst** emails the status of up to that many requests.


.. _ES:

Info Option -**ES** (-**EqualSign**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specifies the equal sign used to assign a value to a
single-value or multi-value option in input files. Defaults to '<=>'.


.. _FN:

Info Option -**FN** (-**FieldNames**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

is a string of single-letter field names. The values
of the selected fields are returned by actions :ref:`-GC <GC>` (-GetControl), :ref:`-GP <GP>`
(-GetPartition), :ref:`-GR <GR>` (-GetRequest), and :ref:`-GF <GF>` (-GetFile). If this option is
not specified, the default fields are returned. Valid field names are
listed in the corresponding action sections.


.. _GU:

Mode Option -**GU** (-**GetUsage**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

gets usage information for the given requests and
records it for order metrics.


.. _GZ:

Mode Option -**GZ** (-**GMTZone**) (Aliases: -**GMT**, -**GreenwichZone**, -**UTC**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -GMT|GreenwichZone|UTC) uses GMT dates/times,
rather than mountain time, as the controlling times for processing
request actions.


.. _LN:

Info Option -**LN** (-**LoginName**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

login name of the current user; defaults to the DECS
specialist who is running **dsrqst**. Set this option to run the utility on
behalf of a specialist other than yourself.


.. _OF:

Info Option -**OF** (-**OutputFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specifies the file name for writing the application
output. The output format matches the input file format. If this option
is omitted, results are displayed on screen.


.. _ON:

Info Option -**ON** (-**OrderNames**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

is a string of single-letter field names used to order
the results of GET actions: :ref:`-GC <GC>` (-GetControl), :ref:`-GP <GP>` (-GetPartition), :ref:`-GR <GR>`
(-GetRequest), and :ref:`-GF <GF>` (-GetFile). Uppercase indicates ascending order,
lowercase descending order. This option also forces reordering of the
data files displayed on the webpage for :ref:`Action <section3>` :ref:`-SF <SF>` (-SetFile) when :ref:`Mode <section4>`
option :ref:`-RO <RO>` (-Reorder) is present but Info option :ref:`-WF <WF>` (-WebFile) is
omitted.


.. _PW:

Info Option -**PW** (-**PurgeWait**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

defaults to 7200 seconds. Used in **dsrqst** daemon mode.
After all due requests have been purged, **dsrqst** waits this period
before checking again for requests due to be purged. A different wait
interval can be set in seconds, minutes, hours, or days; for example,
'-PW 4H' for 4 hours. A bare numeric value is interpreted as seconds, so
'-PW 3600' means 3600S.


.. _AO:

Info Option -**AO** (-**ActOption**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

is used for setting :ref:`Action <section3>` and :ref:`Mode options <section4>` inside
input files. Defaults to '<!>'.


.. _TS:

Info Option -**TS** (-**totalSize**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets the default size, in GB, that is the maximum disk
space available for **dsrqst** to stage temporary online data. Queued
requests are held when the total online data reaches this limit, until
older requests are purged and their data files are removed, freeing
enough disk space for the next request to be processed.


.. _WH:

Info Option -**WH** (-**WebHomeDir**) (Aliases: -**WebHome**, -**DownloadHome**, -**OnlineHome**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -WebHome|-DownloadHome|-OnlineHome) specifies
the web home directory where requested data files are temporarily staged.
Defaults to $TRANSFER/dsrqst.



| :ref:`Back to Top <section5.1>`
| :ref:`Back to Table of Contents <index>`
