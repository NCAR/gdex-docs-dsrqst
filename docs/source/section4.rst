
.. _section4:

4 - MODE OPTIONS
=================================

Use Mode options to modify the behavior of :ref:`Action options <section3>`. Mode options are all
optional. No values should follow any Mode option.


.. _AW:

Mode Option -**AW** (-**AnyWhere**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

works with :ref:`Info option <section5>` :ref:`-BP <BP>` (-BatchProcess) to use an empty
work directory so that the recorded **dsrqst** command can be started anywhere
other than the directory where the command was originally recorded.


.. _BG:

Mode Option -**BG** (-**BackGround**) (Alias: -**b**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

background process. When present, screen
display is turned off for both standard output and errors.


.. _CS:

Mode Option -**CS** (-**CheckStatus**) (Aliases: -**CheckReqeustStatus**, -**CheckParitionStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

checks and displays more detailed status information for
each request. To show process progress as a percentage, fields dsrqst.fcount
or dsrqst.size_request must not be empty, and wfrqst.status must be set to
'O' for each finished data file record.


.. _FI:

Mode Option -**FI** (-**ForceInterrrupt**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

forcibly interrupts a request that is still being
built; otherwise a warning message is displayed.


.. _FO:

Mode Option -**FO** (-**FormatOutput**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

formats column output results for get actions. The same
width, evaluated dynamically, is applied to all values of a given field.


.. _FP:

Mode Option -**FP** (-**ForcePurge**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

purges a request that is not yet due. This Mode option is
also used for :ref:`Action <section3>` :ref:`-DL <DL>` with either Mode options :ref:`-UD <UD>` (-UnusedData) or :ref:`-UR <UR>`
(-UnusedRequest) to physically remove unused data files or request directories.


.. _MD:

Mode Option -**MD** (-**MyDataset**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

allows a specialist to add, modify or delete request
control records, request partition records, request records and data file
records for a dataset owned by another specialist.


.. _NC:

Mode Option -**NC** (-**NewControl**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a new request control can only be added when this Mode
option is present and request control index is given as 0 when :ref:`Action <section3>` :ref:`-SC <SC>`
(-SetControl) is executed. This Mode option prevents accidentally adding
request control records.


.. _NE:

Mode Option -**NE** (-**NoEmail**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

does not send email notice to the specialist after update.


.. _NO:

Mode Option -**NO** (-**NotOnline**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

does not publish filelist after update and sets the request
status to N. No normal email is sent since the data are not ready online, but
error messages, if any, are still sent to the specialist. Add Mode option :ref:`-NE <NE>`
too if no email is wanted in any situation.


.. _4_e8:

**EXAMPLE 8. Rebuild request 27208 that is not in status Q, without sending email or publishing a filelist:**

| **dsrqst** :ref:`BR <BR>` :ref:`-RI <RI>` 27208 :ref:`-RS <RS>` Q :ref:`-NE <NE>` :ref:`-NO <NO>`


.. _NP:

Mode Option -**NP** (-**NewPartition**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

new partitions can only be added for a given request
index when this Mode option is present and :ref:`Action <section3>` :ref:`-SP <SP>` (-SetPartition) is
executed.


.. _NR:

Mode Option -**NR** (-**NewRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a new request can only be added when this Mode option is
present and request index is given as 0 when :ref:`Action <section3>` :ref:`-SR <SR>` (-SetRequest) is
executed. This Mode option prevents accidentally adding request records.


.. _RO:

Mode Option -**RO** (-**ResetOrder**) (Alias: -**Reorder**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

resets the display orders of the data
files in a request to match the order in which data file records are given
for :ref:`Action <section3>` :ref:`-SF <SF>` (-SetFile). Another way of reordering the data files is to
explicitly provide display order index values per :ref:`Info option <section5>` :ref:`-DO <DO>`
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

checks and resets request file status for files that
are not on disk with :ref:`Action <section3>` :ref:`-DL <DL>` (-Delete).


.. _UR:

Mode Option -**UR** (-**UnusedRequest**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

with :ref:`Action <section3>` :ref:`-DL <DL>` (-Delete), checks and removes request
directories that are still on disk but no longer in GDEXDB. Directories are
only physically removed if Mode option :ref:`-FP <FP>` is present.


.. _WD:

Mode Option -**WD** (-**WithDataset**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

gets the dataset ID for Actions :ref:`-GF <GF>` (-GetFile) and
:ref:`-GT <GT>` (-GetTarFile).


.. _WE:

Mode Option -**WE** (-**WithEmail**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

forces sending email to the requester after a filelist is
republished successfully for a request. Works with :ref:`Action <section3>` :ref:`-RP <RP>` (-ResetPurge|RePublish).



| :ref:`Back to Top <section4>`
| :ref:`Back to Table of Contents <index>`
