Identity Management
===================

Identity management across facilities remains a challenge.
There are currently no multi-site solutions in place for
creating and managing identities across the DOE sites.  However, there
are various efforts underway that should address these challenges
in the future.  Currently, users will need to request allocations
and accounts at each site.  Below are pointers for each site describing
how to get allocations and establish access.

ALCF
~~~~

The process for obtaining an account at ALCF begins with an allocation request. Users new to ALCF systems will often request a `discretionary allocation <https://www.alcf.anl.gov/science/directors-discretionary-allocation-program>`_, which grants a user account and a small number of compute hours with which to compile code, make initial runs, and collect performance data with the goal of applying for a larger allocation. User accounts can be managed through the `user accounts site <https://accounts.alcf.anl.gov/>`_.

Larger allocations are awarded through competitive application processes, including `INCITE <http://www.doeleadershipcomputing.org/>`_ and `ALCC <https://science.osti.gov/ascr/Facilities/Accessing-ASCR-Facilities/ALCC>`_.

NERSC
~~~~~
In order to get an account at NERSC, you will need an allocation
to associate with your account.  If you are part of an existing project,
you can specify that project when you request your account.  Otherwise,
you will need to request an allocation via ERCAP.  Accounts and allocations
are managed via IRIS (https://iris.nersc.gov).

* Requesting a new account: https://docs.nersc.gov/accounts/
* Requesting a new allocation: https://www.nersc.gov/users/accounts/allocations/first-allocation/

NERSC is in the process of adding support for Federated Identity management.  This is described
in detail here.

https://docs.nersc.gov/connect/federatedid/

OLCF
~~~~

At OLCF, user accounts must be attached to active projects, and the resources
that users can access depend on the security enclave that their projects were
assigned at creation. There are two security enclaves at OLCF, and thus there
are two kinds of accounts: OLCF Moderate and OLCF Open.

Most of the resources that OLCF is famous for, like Summit and the upcoming
`Frontier <https://www.olcf.ornl.gov/frontier/>`_, are part of the Moderate
enclave. Most users will have an OLCF Moderate account. This enclave uses
two-factor authentication by means of an RSA SecurID token or a mobile phone
app.

The Open enclave at OLCF has similar but smaller-scale resources than the
Moderate enclave. For example,
`Ascent <https://docs.olcf.ornl.gov/systems/ascent_user_guide.html>`_ has the
same architecture and design as Summit, but it has only 18 nodes, whereas
Summit has approximately 4,600. The Open enclave is most often used for
training purposes or when the reduced security constraints are both compatible
and necessary for a project to perform its scientific mission. This enclave
uses the `XCAMS system <https://web.ornl.gov/xcams/xcamsfaq.htm>`_ for
authentication.

More information about the different account types, as well as information for
how to apply for allocation, is available
`here <https://docs.olcf.ornl.gov/accounts/index.html>`_.

