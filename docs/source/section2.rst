
.. _section2:

2 - GENERAL DSRQST USAGE
=================================

| **dsrqst** [:ref:`Action Option <section3>`] [:ref:`Mode Options <section4>`] [:ref:`Info Options <section5>`]
|        or
| **dsrqst** [:ref:`-(IF|InputFile) <IF>`] InputFileNames [-b]

Brackets [] indicate optional items. A pipe '|' inside parentheses, as in
(A|B), means either A or B can be used. The options accepted by **dsrqst**
fall into three categories: :ref:`Action <section3>`, :ref:`Mode <section4>`, and Information (:ref:`Info <section5>` for short)
options. :ref:`Action options <section3>` specify the task the utility executes; :ref:`Mode <section4>` options
modify the behavior of an action; and :ref:`Info options <section5>` pass one or more values
to **dsrqst**. Options can be given in short or long form, for example :ref:`-DS <DS>`
or -Dataset. Some options also have alias names for convenience. Option
names are case-insensitive, but the values that follow :ref:`Info options <section5>` are
case-sensitive.

Option :ref:`-DS <DS>` is an :ref:`Info option <section5>` that specifies a dataset number. If a dataset
number is given as the first argument following the **dsrqst** command, the
option name :ref:`-DS <DS>` (-Dataset) can be omitted. Some actions can run without a
dataset number, in which case they apply to all available request records
across datasets. Most **dsrqst** actions can process multiple datasets in a
single execution.

Specify exactly one :ref:`Action option <section3>` per **dsrqst** execution. Depending on the
chosen :ref:`Action <section3>`, certain :ref:`Info options <section5>` are mandatory and others are optional,
and certain :ref:`Mode options <section4>` can be used to alter the action's behavior.
Providing multiple :ref:`Action options <section3>` simultaneously is not allowed.

All options except :ref:`Info option <section5>` :ref:`-IF <IF>` (-InputFile) can be given on the command
line or in input files. Input file names are specified through :ref:`Info <section5>` option
:ref:`-IF <IF>` and can only be provided on the command line. See the description of
:ref:`Info option <section5>` :ref:`-IF <IF>` (-InputFile) for the format of options inside input files.
One or more input files can be combined with command-line options to run
**dsrqst**. The option name :ref:`-IF <IF>` (-InputFile) itself can be omitted when a
single input file is given on the command line and all action and option
information is provided inside that file.

When retrieving information about request controls, request partitions,
request records, or requested files, :ref:`Info options <section5>` specify the conditions
used to query GDEXDB. Special characters can further restrict a query:

.. list-table::
   :widths: auto
   :header-rows: 1
 '!', '<', '>', and '<>'. When provided on the command line, these characters must be quoted or escaped to avoid shell interpretation. The character '!', or \!, means exclusion of the value(s) that follow and must be the first value following an :ref:`Info option <section5>` name. '<' and '>' mean less than or greater than the following value, and '<>' means between the following two values. Combine '!' and '<' as "'!' '<' OptionValue" to express a condition of 'greater than or equal to OptionValue'.

Display help for a specific option by running:

.. list-table::
   :widths: auto
   :header-rows: 1
 dsrqst [Option] -(h|help) [Option]

The description is shown for an option placed either before or after
-(h|help). If no option is specified, or if **dsrqst** is issued by itself,
this entire document is displayed via the UNIX utility 'more'. A hard copy
of this help document can be printed from the saved file dsrqst.usg under
the Python package rda_python_dsrqst/.



| :ref:`Back to Top <section2>`
| :ref:`Back to Table of Contents <index>`
