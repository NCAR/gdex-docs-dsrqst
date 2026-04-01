
.. _section3:

3 - ACTION OPTIONS
=================================

Action options are used to specify what tasks **dsrqst** executes. No values
are allowed to follow Action options. Multiple tasks may be processed with a
single execution of **dsrqst** depending on what Action option is chosen. Some of
the comprehensive actions include automatically other simpler actions as
default; and others include additional actions when certain :ref:`Mode options <section4>` are
present. Multiple Action options provided simultaneously are blocked.

Some actions are setting information into and some getting information from
RDADB for one or multiple datasets.

Based on the information being manipulated, the actions are divided into four
categories:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`Request Control Actions <section3.1>`
     - create, delete, modify and retrieve request control information in RDADB, of a given dataset/group and a request type,
   * - :ref:`Request Actions <section3.2>`
     - create, delete, modify and retrieve request information of individual requests and the requested data files
   * - :ref:`Request Process Actions <section3.3>`
     - build requests by staging HPSS data online and purge requests by clean request records and temporary online data

.. toctree::
   :maxdepth: 2
   :caption: Table of Contents

   section3.1
   section3.2
   section3.3

**Appendix A: List of Examples**

- :ref:`A.1. Action Option -SC (-SetControl) <3.1.1_e1>`
- :ref:`A.2. Action Option -GC (-GetControl) <3.1.2_e2>`
- :ref:`A.3. Action Option -GR (-GetRequest) <3.2.1_e3>`
- :ref:`A.4. Action Option -SR (-SetRequest) <3.2.2_e4>`
- :ref:`A.5. Action Option -SR (-SetRequest) <3.2.2_e5>`
- :ref:`A.6. Action Option -GP (-GetPartition) <3.2.4_e6>`
- :ref:`A.7. Action Option -GF (-GetFile) <3.2.6_e7>`



| :ref:`Back to Top <section3>`
| :ref:`Back to Table of Contents <index>`
