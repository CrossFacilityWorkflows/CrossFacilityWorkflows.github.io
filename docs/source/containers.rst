.. _Containers:

Containers
==========
This page documents container infrastructure available at each site.

`Containers` are an approach to bundling all of the required files and data for an application as a single file, so the dependencies are fully `contained` and referenced at runtime, removing concerns over changes in underlying system dependencies which can render an application unusable. The resulting container can be moved between systems and still run, since its dependencies are fully satisfied local to the container.

Applications deployed in containers typically run with little to no degradation in performance. This is in line with expectations, and is especially applicable in the context of applications with significant dependence on the filesystem, such as Python applications (which typically load many module files at startup), dynamically linked applications (which need to load shared object files, as opposed to the single-file statically linked applications), and applications with a significant data dependency, where those data dependencies can be included in the container. The reason in all of these cases is that the number of references to files on the remote filesystem is reduced, as they are resolved to the compute node-local container instead.


.. attention::

    Under construction

.. _ALCF Singularity:

ALCF
~~~~

ALCF deploys Singularity for use on the Theta system, including both the Intel KNL and NVIDIA A100 nodes. Singularity images can be derived from pre-existing Docker images, or built directly using Singularity recipes. Containerized applications have run successfully on Theta up to 4096 nodes with Singularity.

Full details about using Singularity at ALCF can be found on the ALCF documentation site, for both `Theta <https://www.alcf.anl.gov/support-center/theta/singularity-theta/>`_ and `ThetaGPU <https://www.alcf.anl.gov/support-center/theta-gpu-nodes/nvidia-containers>`_. Further details about Singularity at ALCF are also available in materials from the ALCF Computational Performance workshop, `here <https://www.alcf.anl.gov/support-center/theta-gpu-nodes/nvidia-containers>`_.


.. _NERSC Shifter:

NERSC
~~~~~

NERSC has been an early adopter and proponent of containers for scientific and HPC workflows.
This led to the development of 
`Shifter <https://www.nersc.gov/research-and-development/user-defined-images/>`_
which is a software package that allows container images created with tools like Docker or Podman to run securely and scalably on large-scale HPC systems.
Using containers with Shifter, users can create an image with there desired operating system and easily 
install software stacks and dependencies. With some care these images can be run across different systems assuming architectual compatibility.
Shifter has several novel features that help with scalable launch and leveraging high-performance interconnect and accelerators.
It is currently the best performing option for python code stacks across multiple nodes. 
For full information on using Shifter at NERSC, please see `this page <https://docs.nersc.gov/development/shifter/how-to-use/>`_.

NERSC is also evaluating `Podman <https://podman.io/>`_ as an eventual replacement for Shifter.  
Podman will allow users to build images directly on the system and integrates more easily with standard container tools.  
NERSC is developing enhancements to Podman to enable the same scalable launch features found in Shifter and other HPC container runtimes.

OLCF 
~~~~
