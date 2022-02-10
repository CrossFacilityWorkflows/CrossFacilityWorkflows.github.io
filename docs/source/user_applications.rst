User Services
===============

This page documents infrastructure available at each site to support
user-managed applications and services such as data portals, science gateways, workflow managers,
databases, API endpoints, and network services to support scientific projects.
Most sites provide container-based orchestration services to support such workloads.


ALCF
~~~~
ALCF is researching solutions for user service orchestration; this page will be updated as more details become available.

NERSC
~~~~~
`Spin <https://www.nersc.gov/systems/spin/>`_ is a container-based platform at NERSC designed to support scientific projects.
Services in Spin are built with Docker containers and can easily access NERSC systems and storage.  Services are managed 
via Rancher which provides a easy to use user-interface on top of Kubernetes.  Spin is ideal for running persistent services
that may be required by a workflow or to host data generated on HPC systems.

OLCF
~~~~
`Slate <https://docs.olcf.ornl.gov/services_and_applications/slate/overview.html>`_
provides a container orchestration service for running user-managed persistent application
services that do not fit into a batch job. It supports all containerized services with OpenShift, 
a Kubernetes-based platform.
