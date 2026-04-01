
.. _section4:

4 - MODE OPTIONS
=================================

Use proper Mode options to modify behaviors of :ref:`Action options <section3>`. Mode options
are all optional. No value is allowed to be passed in following any Mode option.


.. _AW:

Mode Option -**AW** (-**AnyWhere**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

works with :ref:`Info option <section5>` :ref:`-BP <BP>` (-BatchProcess) to use empty
work directory so that the recorded "dsrqst' command can be started processing
anywhere other than the directory where the command was recorded initially.


.. _BG:

Mode Option -**BG** (-**BackGround**) (Alias: -**b**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

background process. When it presents
screen display is turned off for both standard outputs and errors.


.. _CS:

Mode Option -**CS** (-**CheckStatus**) (Aliases: -**CheckReqeustStatus**, -**CheckParitionStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

if present, checks and displays more detailed status
information of each request. To show process progress in percentage, fields
dsrqst.fcount or dsrqst.size_request must not be empty, and wfrqst.status must
be set to 'O' for echo finished data file record.


.. _FI:

Mode Option -**FI** (-**ForceInterrrupt**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

if present, force interrupts a request that is still
under building; otherwise a warning message will display.


.. _FO:

Mode Option -**FO** (-**FormatOutput**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

if present, formats column output results for get
actions. A same width, evaluated dynamically, is applied for all values of a
given field.


.. _FP:

Mode Option -**FP** (-**ForcePurge**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

if present, purges a request that is not due yet. This
Mode option is also used for :ref:`Action <section3>` :ref:`-DL <DL>` with either Mode options :ref:`-UD <UD>` (-UnusedData)
or :ref:`-UR <UR>` (-UnusedRequest) to clean the unused data files or request directories.


.. _MD:

Mode Option -**MD** (-**PgDataset**) :
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

does not publish filelist after update and set the request
status to N. No normal email is send either since the data are not ready online,
but error message, if any, is still sent to specialist. Add Mode option :ref:`-NE <NE>`
too if no email is wanted fo any situation.


.. _4_e8:

**EXAMPLE 8. Rebuild request 27208 that is not in status Q and no email needs to be sent and no filelist needs to be published:**

| **dsrqst** :ref:`BR <BR>` :ref:`-RI <RI>` 27208 :ref:`-RS <RS>` Q :ref:`-NE <NE>` :ref:`-NO <NO>`


.. _NP:

Mode Option -**NP** (-**NewPartition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

new partitions can only be added for a given request
index when this Mode option is present when :ref:`Action <section3>` :ref:`-SP <SP>` (-SetPartition) of
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
of the data file lists of a request as the order data file records are given
for actions :ref:`-SF <SF>` (-SetFile). Another way of reordering the data files is to
provide explicitly display order index values per :ref:`Info option <section5>` :ref:`-DO <DO>`
(-DisplayOrder).


.. _UD:

Mode Option -**UD** (-**UnusedData**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

checks and removes unused data under data/dsnnn.n with
action :ref:`-DL <DL>` (-Delete). Only physically removing if Mode option :ref:`-FP <FP>` is present.


.. _UF:

Mode Option -**UF** (-**UnstagedFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

checks and reset request file status for files are not
on disk with action :ref:`-DL <DL>` (-Delete).


.. _UR:

Mode Option -**UR** (-**UnusedRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

with action :ref:`-DL <DL>` (-Delete), checks and removes request
directory that still on disk but not in RDADB any more. Only physically removing
if Mode option :ref:`-FP <FP>` is present.


.. _WD:

Mode Option -**WD** (-**WithDataset**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

get the dataset ID for Actions :ref:`-GF <GF>` (-GetFile) and :ref:`-GT <GT>` (-GetTarFile).


.. _WE:

Mode Option -**WE** (-**WithEmail**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

forces to send email to requester after the a filelist being
republished successfully for a request. It works with :ref:`Action <section3>` :ref:`-RP <RP>` (-ResetPurge|RePublish).



| :ref:`Back to Top <section4>`
| :ref:`Back to Table of Contents <index>`
