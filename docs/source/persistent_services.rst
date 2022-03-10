Persistent Services Platforms
=============================

This page documents infrastructure available at each site to support
user-managed applications and services such as data portals, science gateways, workflow managers,
databases, API endpoints, and network services to support scientific projects.
Most sites provide container-based orchestration services to support such workloads.


ALCF
~~~~
ALCF is researching solutions for user service orchestration; this page will be updated as more details become available.


.. _Workflow NERSC:

NERSC
~~~~~
`Spin <https://www.nersc.gov/systems/spin/>`_ is a container-based platform at NERSC designed to support scientific projects.
Services in Spin are built with Docker containers and can easily access NERSC systems and storage.  Services are managed 
via Rancher which provides a easy to use user-interface on top of Kubernetes.  Spin is ideal for running persistent services
that may be required by a workflow or to host data generated on HPC systems.


.. _Workflow OLCF:

OLCF
~~~~

The `Slate <https://docs.olcf.ornl.gov/services_and_applications/slate/overview.html>`_
service at OLCF consists of two user-facing
`OpenShift <https://docs.openshift.com/>`_ clusters in different security
enclaves. Both clusters can access the shared filesystems and the batch queues
of the HPC resources in their respective enclaves:

* Marble is in the Moderate enclave, which gives it access to the Alpine (GPFS)
  filesystem as well as the batch queues for Summit, Andes, and the Data
  Transfer Nodes.
* Onyx is in the Open enclave, which gives it access to the Wolf (GPFS) 
  filesystem as well as the batch queue for Ascent.

.. note::
   Most container images on registries like Docker Hub are built to run as
   root. Due to OLCF's security policies, this means that some images will need 
   to be modified by changing ownership of writable directories in the image.

Resources on Slate are not automatically available to OLCF projects; the
project PI must apply for an allocation on Slate. Part of the reason for this
is because all containers on Slate run as a special project-level automation
user.

