
.. _section3:

3 - ACTION OPTIONS
=================================

Action options specify the task that **dsrqst** executes. No values follow an
Action option. A single **dsrqst** execution can perform multiple tasks
depending on which Action option is chosen: some comprehensive actions
include other simpler actions by default, and others trigger additional
actions when certain :ref:`Mode options <section4>` are present. Providing multiple Action
options simultaneously is not allowed.

Some actions write information to GDEXDB, and others retrieve information
from GDEXDB, for one or more datasets.

Based on the kind of information they manipulate, the actions fall into
three categories:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`Request Control Actions <section3.1>`
     - create, delete, modify, and retrieve request control information in GDEXDB for a given dataset/group and request type
   * - :ref:`Request Actions <section3.2>`
     - create, delete, modify, and retrieve information for individual requests and their requested data files
   * - :ref:`Request Process Actions <section3.3>`
     - build requests by staging data online, and purge requests by cleaning request records and the temporary online data

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
