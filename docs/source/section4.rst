
.. _section4:

4 - MODE OPTIONS
=================================

Use proper Mode options to modify the behavior of :ref:`Action options <section3>`. Mode options
are all optional. No values should follow any Mode option.


.. _AW:

Mode Option -**AW** (-**AnyWhere**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

works with :ref:`Info option <section5>` :ref:`-BP <BP>` (-BatchProcess) to use empty
work directory so that the recorded **dsrqst** command can be started processing
anywhere other than the directory where the command was recorded initially.


.. _BG:

Mode Option -**BG** (-**BackGround**) (Alias: -**b**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

background process. When present,
screen display is turned off for both standard output and errors.


.. _CS:

Mode Option -**CS** (-**CheckStatus**) (Aliases: -**CheckReqeustStatus**, -**CheckParitionStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

if present, checks and displays more detailed status
information of each request. To show process progress in percentage, fields
dsrqst.fcount or dsrqst.size_request must not be empty, and wfrqst.status must
be set to 'O' for each finished data file record.


.. _FI:

Mode Option -**FI** (-**ForceInterrrupt**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

if present, forcibly interrupts a request that is
still being built; otherwise a warning message is displayed.


.. _FO:

Mode Option -**FO** (-**FormatOutput**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

if present, formats column output results for get
actions. The same width, evaluated dynamically, is applied to all values of a
given field.


.. _FP:

Mode Option -**FP** (-**ForcePurge**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

if present, purges a request that is not due yet. This
Mode option is also used for :ref:`Action <section3>` :ref:`-DL <DL>` with either Mode options :ref:`-UD <UD>` (-UnusedData)
or :ref:`-UR <UR>` (-UnusedRequest) to clean the unused data files or request directories.


.. _MD:

Mode Option -**MD** (-**MyDataset**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

allows a specialist to add, modify or delete request
control records, request partition records, request records and data file records
for a dataset owned by another specialist.


.. _NC:

Mode Option -**NC** (-**NewControl**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a new request control can only be added when this Mode option is
present and request control index is given as 0 when :ref:`Action <section3>` :ref:`-SC <SC>` (-SetControl) of
**dsrqst** is executed. This Mode option blocks mistakes of adding request control
records unintentionally.


.. _NE:

Mode Option -**NE** (-**NoEmail**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

does not send email notice to the specialist after update


.. _NO:

Mode Option -**NO** (-**NotOnline**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

does not publish filelist after update and sets the request
status to N. No normal email is sent either since the data are not ready online,
but error message, if any, is still sent to specialist. Add Mode option :ref:`-NE <NE>`
too if no email is wanted for any situation.


.. _4_e8:

**EXAMPLE 8. Rebuild request 27208 that is not in status Q and no email needs to be sent and no filelist needs to be published:**

| **dsrqst** :ref:`BR <BR>` :ref:`-RI <RI>` 27208 :ref:`-RS <RS>` Q :ref:`-NE <NE>` :ref:`-NO <NO>`


.. _NP:

Mode Option -**NP** (-**NewPartition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

new partitions can only be added for a given request
index when this Mode option is present and :ref:`Action <section3>` :ref:`-SP <SP>` (-SetPartition) of
**dsrqst** is executed.


.. _NR:

Mode Option -**NR** (-**NewRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a new request can only be added when this Mode option is
present and request index is given as 0 when :ref:`Action <section3>` :ref:`-SR <SR>` (-SetRequest) of
**dsrqst** is executed. This Mode option blocks mistakes of adding request
records unintentionally.


.. _RO:

Mode Option -**RO** (-**ResetOrder**) (Alias: -**Reorder**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

when present, resets the display orders
of the data files in a request to match the order in which data file records
are given for :ref:`Action <section3>` :ref:`-SF <SF>` (-SetFile). Another way of reordering the data files
is to explicitly provide display order index values per :ref:`Info option <section5>` :ref:`-DO <DO>`
(-DisplayOrder).


.. _UD:

Mode Option -**UD** (-**UnusedData**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

checks and removes unused data under data/dNNNNNN with
:ref:`Action <section3>` :ref:`-DL <DL>` (-Delete). Files are only physically removed if Mode option :ref:`-FP <FP>`
is present.


.. _UF:

Mode Option -**UF** (-**UnstagedFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

checks and resets request file status for files that are
not on disk with :ref:`Action <section3>` :ref:`-DL <DL>` (-Delete).


.. _UR:

Mode Option -**UR** (-**UnusedRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

with :ref:`Action <section3>` :ref:`-DL <DL>` (-Delete), checks and removes request
directories that are still on disk but no longer in GDEXDB. Directories are only
physically removed if Mode option :ref:`-FP <FP>` is present.


.. _WD:

Mode Option -**WD** (-**WithDataset**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

gets the dataset ID for Actions :ref:`-GF <GF>` (-GetFile) and :ref:`-GT <GT>` (-GetTarFile).


.. _WE:

Mode Option -**WE** (-**WithEmail**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

forces sending email to the requester after a filelist is
republished successfully for a request. Works with :ref:`Action <section3>` :ref:`-RP <RP>` (-ResetPurge|RePublish).



| :ref:`Back to Top <section4>`
| :ref:`Back to Table of Contents <index>`
