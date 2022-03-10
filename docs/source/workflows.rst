Workflows Tools
===============

This page describes approaches available for running workflows within and between computing sites.

ALCF
~~~~

Balsam
------
Balsam has been developed at ALCF since 2013, when it was first conceived to link high energy physics workflows for the LHC with Argonne's Mira supercomputer. The latest version of Balsam consists of a central server, reachable via a REST API, and user-deployable Balsam `Sites` which communicate with the server to obtain jobs and interact with the local scheduler to run jobs, monitor their status, and synchronize progress with the server. While the single server maintains all job state, Sites are deployed by users on computing resources where they have accounts, minimizing the barrier to entry and providing a user a global view of their available computing. Due to its modular design, Balsam can easily adapt to new systems, and currently includes support for multiple systems at ALCF, Summit at OLCF, and Cori and Perlmutter at NERSC. More information about Balsam is available on the `documentation site <https://balsam.readthedocs.io/en/latest/>`_.


NERSC
~~~~~

OLCF
~~~~
Information about workflow tools that are officially supported at OLCF is
available `here <https://docs.olcf.ornl.gov/software/workflows/index.html>`_.
