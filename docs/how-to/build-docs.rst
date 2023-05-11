.. _how_to_build_docs:

Build the documentation
***********************

Follow these steps to build a local copy of the documentation.

Set up a virtual environment
----------------------------

Create a virtual environment and activate it:

.. literalinclude:: code/build-docs/task.yaml
    :language: bash
    :start-after: [docs:create-env]
    :end-before: [docs:create-env-end]
    :dedent: 2

Install the documentation requirements:

.. literalinclude:: code/build-docs/task.yaml
    :language: bash
    :start-after: [docs:install-deps]
    :end-before: [docs:install-deps-end]
    :dedent: 2

Once the requirements are installed, you can deactivate the virtual
environment:

.. literalinclude:: code/build-docs/task.yaml
    :language: bash
    :start-after: [docs:leave-env]
    :end-before: [docs:leave-env-end]
    :dedent: 2

It can be useful to activate and deactivate the virtual environment when you
need to update the modules used to build the documentation.

Build the HTML documentation
----------------------------

You can now use the provided :file:`Makefile` to build the documentation within
the virtual environment:

.. literalinclude:: code/build-docs/task.yaml
    :language: bash
    :start-after: [docs:make-docs]
    :end-before: [docs:make-docs-end]
    :dedent: 2

The home page of the generated documentation can be found in the
:file:`docs/_build/html/index.html` file.

Run a local webserver
---------------------

You can also run a local webserver to serve the documentation locally on port
8080. The documentation will be rebuilt on each file change, and will reload
the browser view automatically:

.. literalinclude:: code/build-docs/task.yaml
    :language: bash
    :start-after: timeout -s SIGINT
    :end-before: [docs:make-rundocs-end]
    :dedent: 2

This also builds the documentation within the virtual environment set up at
the start of this guide.