
.. _section2:

2 - GENERAL DSRQST USAGE
=================================

| **dsrqst** [:ref:`Action Option <section3>`] [:ref:`Mode Options <section4>`] [:ref:`Info Options <section5>`]
|        or
| **dsrqst** [:ref:`-(IF|InputFile) <IF>`] InputFileNames [-b]

Brackets [] indicate optional items. A pipe '|' in parentheses as in format (A|B)
means either A or B can be used. The options applied to **dsrqst** are divided
into three categories: :ref:`Action <section3>`, :ref:`Mode <section4>`, and Information (:ref:`Info <section5>` for short) options.
:ref:`Action options <section3>` specify what tasks this utility should execute; :ref:`Mode <section4>` options
modify the behaviors of the actions; and :ref:`Info options <section5>` pass information, one or
multiple values, to run **dsrqst**. An option
can be given in form of either short name or long name, :ref:`-DS <DS>` or -Dataset for
example. Some options have alias names for convenience. Option names can be
given in either upper or lower cases, while the values following :ref:`Info <section5>` options
are case sensitive.

Option :ref:`-DS <DS>` is an :ref:`Info option <section5>` used to specify a dataset number. If a dataset
number is given as the first option following the **dsrqst** command, the option
name :ref:`-DS <DS>` (-Dataset) can be omitted. Some actions can be executed without a
dataset number, which means that the actions are applied to all available
request records across different datasets. Multiple datasets can be processed
for most actions of **dsrqst**.

Specify one of the :ref:`Action options <section3>` each time to execute **dsrqst**. Based on what
:ref:`Action <section3>` is chosen, some of the :ref:`Info options <section5>` are mandatory and others are optional,
and certain :ref:`Mode options <section4>` can be applied to alter the behaviors of the Actions.

All options, except :ref:`Info option <section5>` :ref:`-IF <IF>` (-InputFile), can be given either on the
command line or in input files. Input file names are specified via :ref:`Info <section5>` option
:ref:`-IF <IF>` and can only be provided on the command line. Check the description of :ref:`Info <section5>`
option :ref:`-IF <IF>` (-InputFile) for details on how to present options in input files.
One or multiple input files, combined with options on the command line, can be
used to run **dsrqst**. The option name, :ref:`-IF <IF>` (-InputFile), itself can be omitted if
a single input file is given on command line, and action and other option
information are all provided inside the input file.

When information about request controls, request partitions, request records, and
requested files is retrieved, :ref:`Info options <section5>` are used to specify conditions for
querying information from GDEXDB. Some special characters can be used to further
restrict the query with special conditions; they are '!', '<', '>' and '<>'.
These special characters, if provided on the command line, must be quoted or
escaped to avoid being interpreted by the Unix shell.
The '!', or \!, means exclusion to the following value(s) and it must be the
first value following an :ref:`Info option <section5>` name, while '<' or '>' mean greater or
less than the following value and '<>' means between the following two values.
Combine '!' and '<', as syntax "'!' '<' OptionValue", to make a condition of
'greater than or equal to OptionValue'.

Description of an individual option is displayed if **dsrqst** is issued on
command line as

| **dsrqst** [Option] -(h|help) [Option]

A description is displayed for an option given either before or after -(h|help).
If no option is specified or **dsrqst** is issued by itself, this whole document
is displayed per UNIX utility 'more'. A hard copy of this help document can be
printed from the saved file, dsrqst.usg under python package rda_python_dsrqst/.



| :ref:`Back to Top <section2>`
| :ref:`Back to Table of Contents <index>`
