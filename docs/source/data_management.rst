Data Management
===============

DataFed
---------

.. image:: ./assets/Cross_Facility_Federation_of_Repositories.png

DataFed is scientific data management and collaboration system that dramatically
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


See `this page <https://ornl.github.io/DataFed/>`_ for more detailed documentation, YouTube videos, Jupyter notebooks, user guides, API reference etc.

Upon completing the necessary steps to `prepare <https://ornl.github.io/DataFed/system/getting_started.html>`_,
`install and configure <https://ornl.github.io/DataFed/user/client/install.html>`_ DataFed, users can start using DataFed to manage their data:

Command Line Interface
~~~~~~~~~~~~~~~~~~~~~~
Accessing the the CLI in interactive mode:

.. code:: bash

    $ datafed
    Welcome to DataFed CLI, version 1.1.0:0
    Authenticated as u/user123
    Use 'exit' command or Ctrl-C to exit shell.

Creating a Data Record that will contain rich scientific metadata, provenance information, etc.:

.. code:: bash

    root> data create \
    --alias "record_from_nersc" \ # Optional argument
    --description "Data and metadata created at NERSC" \ # Optional argument
    --metadata-file ./nersc_md.json \ # Optional argument
    "First record created at NERSC using DataFed CLI" # Title is required though

    ID:            d/31030353
    Alias:         record_from_nersc
    Title:         First record created at NERSC using DataFed CLI
    Data Size:     0
    Data Repo ID:  repo/cades-cnms
    Source:        (none)
    Owner:         somnaths
    Creator:       somnaths
    Created:       11/25/2020,08:04
    Updated:       11/25/2020,08:04
    Description:   Data and metadata created at NERSC

Uploading data in the local file system to remote DataFed data repository:

.. code:: bash

    root> data put \
    --wait \ # optional - wait until Globus transfer completes
    "record_from_nersc" \ # optional - (unique) alias of record
    ./nersc_data.txt # path to data

    Task ID:             task/31030394
    Type:                Data Put
    Status:              Succeeded
    Started:             11/25/2020,08:05
    Updated:             11/25/2020,08:05

For more examples, please see the `user guide for the DataFed CLI <https://ornl.github.io/DataFed/user/cli/guide.html>`_.

Python API
~~~~~~~~~~

Import the package and instantiate the messaging client to communicate with the DataFed
server:

.. code:: python

    from datafed.CommandLib import API
    df_api = API()

Prepare (fake) scientific metadata that would go into a Data Record:

.. code:: python

    parameters = {
                  'a': 4,
                  'b': [1, 2, -4, 7.123],
                  'c': 'Something important',
                  'd': {'x': 14, 'y': -19} # Can use nested dictionaries
                  }

Create the Data Record:

.. code:: python

    dc_resp = df_api.dataCreate('my important data',
                                metadata=json.dumps(parameters),
                                parent_id=dest_collection, # parent collection
                                )

    print(dc_resp)

.. code-block:: none

    (data {
      id: "d/34682319"
      title: "Some new title for the data"
      alias: "my_first_dataset"
      repo_id: "repo/cades-cnms"
      size: 0.0
      ext_auto: true
      ct: 1611077217
      ut: 1611077220
      owner: "p/trn001"
      creator: "u/somnaths"
      notes: 0
    }
    update {
      id: "d/34682319"
      title: "Some new title for the data"
      alias: "my_first_dataset"
      owner: "p/trn001"
      creator: "u/somnaths"
      size: 0.0
      notes: 0
      deps_avail: true
    }
    , 'RecordDataReply')

Upload raw data that will be associated with this Data Record:

.. code-block:: python

    put_resp = df_api.dataPut(record_id,
                              './parameters.json',
                              wait=True, # Waits until transfer completes.
                              )
    print(put_resp)

.. code-block:: none

    (item {
       id: "d/34682319"
       title: "Some new title for the data"
       size: 0.0
       owner: "p/trn001"
     }
    task {
       id: "task/34702491"
       type: TT_DATA_PUT
       status: TS_SUCCEEDED
       client: "u/somnaths"
       step: 3
       steps: 4
       msg: "Finished"
       ct: 1611102437
       ut: 1611102444
       source: "olcf#dtn/gpfs/alpine/stf011/scratch/somnaths/DataFed_Tutorial/raw_data.dat"
       dest: "d/34682319"
     }, 'DataPutReply')

More examples are available in the
`user guide <https://ornl.github.io/DataFed/user/python/high_level_guide.html#getting-started>`_ and in `Jupyter notebooks <https://ornl.github.io/DataFed/user/python/notebooks.html>`_.
