Rockcraft commands
==================

The :command:`rockcraft` tool is run from the command line and has the
following syntax:

.. code:: text

   rockcraft [help] <command>

The commands that Rockcraft understands are defined :ref:`in the section below
<reference_commands>`. Additionally, :command:`rockcraft` can be run without a
command -- in this case, the ``pack`` command will be used.

Rockcraft requires a :file:`rockcraft.yaml` file for most commands.
The `init`_ command can be used to create a new :file:`rockcraft.yaml` project
file.

Getting help
------------

To get a brief description of a command, include ``help`` before the name of
the command when running :command:`rockcraft`. For example, running Rockcraft
in the following way will show the help text for the ``init`` command:

.. code:: bash

   rockcraft help init

Running :command:`rockcraft` with only ``help`` or ``-h`` will provide general
help for the tool.

.. _reference_commands:

Commands
--------

Commands can take an optional parameter, ``<part-name>``. When a part name is
provided, the command applies to that specific part. When no part name is
provided, the command applies to all parts, and they are all implicitly
specified.

build
~~~~~
Builds artifacts defined for each part.

clean
~~~~~
Removes the assets for the specified parts. When no part is specified, the
entire build environment (e.g. the LXD instance) is removed.

init
~~~~
Initializes a rockcraft project with a boilerplate :file:`rockcraft.yaml`
project file.
This command does not accept a part name because no parts are defined until a
project file is created.

See :ref:`rockcraft_format` for information about the contents of
:file:`rockcraft.yaml` files.

overlay
~~~~~~~
Runs operations defined for the specified parts on a layer over the base
filesystem, potentially modifying its contents.

pack
~~~~
*This is the default lifecycle command for Rockcraft.*

Process parts and create the ROCK as an OCI archive file containing the project
payload with the provided metadata.

prime
~~~~~
Prepare, for each specified part, the final payload to be packed as a ROCK,
performing additional processing and adding metadata files.

pull
~~~~
Downloads or retrieves artifacts defined for the specified parts.

stage
~~~~~
Stages built artifacts into a common staging area, for each specified part.
