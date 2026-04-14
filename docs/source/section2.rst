
.. _section2:

2 - GENERAL DSRQST USAGE
=================================

| **dsrqst** [:ref:`Action Option <section3>`] [:ref:`Mode Options <section4>`] [:ref:`Info Options <section5>`]
|        or
| **dsrqst** [:ref:`-(IF|InputFile) <IF>`] InputFileNames [-b]

Brackets [] indicate optional items. A pipe '|' in parentheses as in format (A|B)
means either A or B can be used. The options applied to **dsrqst** are divided
into three categories: :ref:`Action <section3>`, :ref:`Mode <section4>`, and Information (:ref:`Info <section5>` for short) options.
:ref:`Action options <section3>` specify the task this utility executes; :ref:`Mode options <section4>` modify the
behavior of the actions; and :ref:`Info options <section5>` pass information, one or multiple
values, to run **dsrqst**. Options can be given in short or long name form,
:ref:`-DS <DS>` or -Dataset for example. Some options have alias names for convenience.
Option names are case-insensitive, while the values following :ref:`Info <section5>` options
are case sensitive.

Option :ref:`-DS <DS>` is an :ref:`Info option <section5>` for specifying a dataset number. If a dataset
number is given as the first option following the **dsrqst** command, the option
name :ref:`-DS <DS>` (-Dataset) can be omitted. Some actions can be executed without a
dataset number, which means the actions apply to all available request records
across different datasets. Multiple datasets can be processed for most
actions of **dsrqst**.

Specify one :ref:`Action option <section3>` per **dsrqst** execution. Based on the chosen :ref:`Action <section3>`,
some :ref:`Info options <section5>` are mandatory and others are optional, and certain :ref:`Mode <section4>`
options can be applied to alter the :ref:`Action <section3>`'s behavior. Providing multiple
:ref:`Action options <section3>` simultaneously is not allowed.

All options, except :ref:`Info option <section5>` :ref:`-IF <IF>` (-InputFile), can be given either on the
command line or in input files. Input file names are specified via :ref:`Info <section5>` option
:ref:`-IF <IF>` and can only be provided on the command line. Check the description of :ref:`Info <section5>`
option :ref:`-IF <IF>` (-InputFile) for details on how to present options in input files.
One or multiple input files, combined with options on the command line, can be
used to run **dsrqst**. The option name, :ref:`-IF <IF>` (-InputFile), itself can be omitted if
a single input file is given on the command line and all action and option
information is provided inside the input file.

When retrieving information about request controls, request partitions, request
records, and requested files, :ref:`Info options <section5>` specify conditions for querying
information from GDEXDB. Special characters can further restrict a query:

.. list-table::
   :widths: auto
   :header-rows: 1
 '!', '<', '>' and '<>'. These characters, if provided on the command line, must be quoted or escaped to avoid shell interpretation. The '!', or \!, means exclusion of the following value(s) and must be the first value following an :ref:`Info option <section5>` name. '<' or '>' mean greater or less than the following value, and '<>' means between the following two values. Combine '!' and '<', as "'!' '<' OptionValue", for a condition of 'greater than or equal to OptionValue'.

Display help for a specific option by running:

.. list-table::
   :widths: auto
   :header-rows: 1
 dsrqst [Option] -(h|help) [Option]

The description displays for an option placed either before or after -(h|help).
If no option is specified, or **dsrqst** is issued by itself, this whole document
is displayed via the UNIX utility 'more'. A hard copy of this help document can
be printed from the saved file, dsrqst.usg under python package rda_python_dsrqst/.



| :ref:`Back to Top <section2>`
| :ref:`Back to Table of Contents <index>`
