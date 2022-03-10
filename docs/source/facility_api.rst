APIs for Facilities
===================

Engineering workflow pipelines to handle data collection and analysis at large scale 
across a distributed architecture --- spanning separate instrument and supercomputing 
facilities, management structures, authentication and authorizations systems, 
and other technical and organizational disparities --- requires reliable, easily 
programmable interfaces (APIs) to HPC resources that are based on common, 
industry-standard tools and reusable by multiple science communities. 
Thus, HPC APIs are a key enabling technology for projects that use modern instrument facilities, 
allowing them to continue their natural upward scaling by leveraging off-site supercomputing 
resources as easily as they have leveraged on-site HPC clusters in the past. 

This page documents programmatic interfaces to HPC resources to enable a new
paradigm of scientific endeavors, especially those that are automated or span
multiple facilities.

.. attention::

    Under construction

ALCF
~~~~
ALCF has traditionally developed the Cobalt scheduler for its systems, opening the opportunity to also expose aspects of the scheduler via a programmable API. This work is underway as part of scheduler development in preparation for the Aurora system.

NERSC
~~~~~
NERSC is developing the `SuperFacility API <https://docs.nersc.gov/services/sfapi/>`_
that can be used to script jobs or workflows running against NERSC systems.
The ultimate goal is the totally automated use of NERSC, integrating everything from compute to storage.

Currently, the API is hosted at https://api.nersc.gov/api/v1.2/ and it covers the 
following functional categories

.. list-table:: SF API endpoints
   :widths: 25 50
   :header-rows: 1

   * - Endpoint
     - Usage
   * - ``/account``
     - Get accounting data about the user’s projects, roles, groups and compute and storage allocations
   * - ``/compute``
     - Run batch jobs and query job and queue statuses on compute resources
   * - ``/status``
     - Query the status of system components
   * - ``/storage``
     - Transfer files between storage tiers and external facilities (uses Globus)
   * - ``/utilities``
     - Traverse the file system, upload and download small files, and execute commands
   * - ``/tasks``
     - Query the status and results of asynchronous operations
     
The inclusion of some of these endpoints in the API are rather straightforward. 
For example, it is essential for HPC workflows to submit jobs and query their status 
(``/compute``) and be able to move data efficiently within the HPC center and to the outside world (``/storage``). 
The inclusion of other endpoints follows very specific motivations.

Experiments often require HPC-scale computing at short notice because detector output, 
the driver of compute demand, often varies cyclically. 
Some experiments may even arrange for multiple compute sites to be available to handle workloads on demand. 
To build a truly automated and resilient workflow, the scientist (or workflow orchestration service) 
needs to be able to query the health and status of a facility and make real-time decisions 
based on the response; for example, if a filesystem is unavailable, the workflow pipeline must 
not send data to it. This key requirement is fulfilled with a ``/status`` endpoint.

Science teams often comprise tens or hundreds of members at different organizations worldwide, 
with differing needs for data access. These collaborations need a way for PIs to automate the 
management of their team members’ accounts at the HPC facility --- for example, to set 
access permissions. They also need to manage petabyte-scale data sets across multiple 
file systems, and move data into and out of the HPC facility as needed. Including these
functions through an ``/account`` endpoint allows automation of these tasks.

Information on how to sign up for API and find example for its use can be found on NERSC's documentation pages:
https://docs.nersc.gov/services/sfapi/


Other
~~~~~
ETH's CSCS is developing `FirecREST <https://github.com/eth-cscs/firecrest>`_,
a RESTful Services Gateway to High-Performance Computing (HPC) resources, is a
high-performance and reusable framework that integrates with existing HPC
infrastructure, thus enabling the access to HPC resources to web-enabled
services.
