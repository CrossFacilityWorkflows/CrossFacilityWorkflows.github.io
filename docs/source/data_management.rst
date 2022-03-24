.. _Data Management:

Data Management
===============

This section describes tools that assist in managing data across facilities.

.. note::
   Does data management include Globus? I think (might be wrong) that DataFed is like Globus with a metadata layer, so they are similar. 
   DataFed and ADIOS strike me as very different things, DataFed being Globus-like, and ADIOS for data management within an application.

.. _DataFed:

DataFed
-------

.. image:: ./assets/Cross_Facility_Federation_of_Repositories.png

`DataFed <https://ornl.github.io/DataFed/>`_ is scientific data management and collaboration system that dramatically
simplifies tasks such as organizing, searching for, sharing, discovering, and reusing data
, especially across facilities and organizations.
This is made possible because DataFed "federates" repositories of data into a single, cohesive, and uniform platform.
DataFed was designed to enhance  productivity and reproducibility in scientific research,
keeping the increasingly global and multidisciplinary nature of research involving "big data" in mind.
DataFed supports the early lifecycle stages of “working” scientific data and serves as a tool to ease the burden associated with capturing,
organizing, and sharing potentially large volumes of heterogeneous scientific data.
DataFed provides a FAIR-principled environment in which scientific data can be precisely controlled and refined in preparation for eventual data publishing.
DataFed can be accessed via a `web portal <https://datafed.ornl.gov>`_ or via
`command-line <https://ornl.github.io/DataFed/user/cli/guide.html>`_ and `python application programming interfaces <https://ornl.github.io/DataFed/user/python/high_level_guide.html>`_.

The `documentation website <https://ornl.github.io/DataFed/>`_ provides information on
`preparing prerequisites <https://ornl.github.io/DataFed/system/getting_started.html>`_,
`installing and configuring <https://ornl.github.io/DataFed/user/client/install.html>`_  DataFed,
user guides for the `command-line <https://ornl.github.io/DataFed/user/cli/guide.html>`_ and
`python <https://ornl.github.io/DataFed/user/python/high_level_guide.html>`_ application programming interfaces,
`Jupyter notebooks and corresponding YouTube videos <https://ornl.github.io/DataFed/user/python/notebooks.html>`_ that were part of hands-on tutorials.

