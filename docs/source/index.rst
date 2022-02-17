.. SIDpy documentation master file, created by
   sphinx-quickstart on Sun Jul 12 16:57:01 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Cross Facility Workflows
========================

**Documentation and best practices on how to run workflows across ASCR facilities**

An number of users and science teams would like to be able to run their workflows at mulitple HPC facilities.  This is particularly true for users analyzing data generated at experimental facilities or observational instruments (such as light sources, genome sequencers, accelerators, telescopes and electron microscopes) which are increasingly requiring High Performance Computing (HPC) scale capabilities for data analysis and workflow processing.  The reasons given for needing cross facility workflows are varied.  Often large data analysis pipelines from experimental facilities require near real-time computing and need to have an alternative analysis site if their primary site is down or undergoing maintenance.  In other instances, teams have acquired allocations at multiple facilities and need to be able to use the allocations efficiently.  

Historically, running workflows across facilities has been challenging.  In this documentation we highlight tools, techniques and best practies for running workflows across facilities.


Jump to our `GitHub project page <https://github.com/CrossFacilityWorkflows/CrossFacilityWorkflows.github.io>`_

.. toctree::
   :glob:
   :maxdepth: 1
   :caption: Technologies

   containers
   workflow_support
   facility_api
   workflows
   identity_management
   data_transfer
   data_management

.. toctree::
   :glob:
   :maxdepth: 1
   :caption: Use cases

   cctbx
