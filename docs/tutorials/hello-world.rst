Create a "Hello World" ROCK
***************************

This tutorial will show you how to create, build and run a ROCK, using
a simple example.

You will need to set up your development environment with the
:doc:`prerequisites <common/requirements>` needed for this tutorial before
continuing.

.. include:: common/install-rockcraft.txt

Project Setup
-------------

Create a new directory and write the following into a text editor:

.. literalinclude:: code/hello-world/rockcraft.yaml
    :language: yaml

Save it as :file:`rockcraft.yaml` in the new directory.

Pack the ROCK
-------------

At the command line, enter the directory containing the :file:`rockcraft.yaml`
file and run the :command:`rockcraft` tool to build and pack the ROCK:

.. literalinclude:: code/hello-world/task.yaml
    :language: bash
    :start-after: [docs:build-rock]
    :end-before: [docs:build-rock-end]
    :dedent: 2

The output should look similar to this:

..  code-block:: text
    :emphasize-lines: 13
    :class: foo

    Launching instance...
    Retrieved base ubuntu:20.04
    Extracted ubuntu:20.04
    Executed: pull hello
    Executed: overlay hello
    Executed: build hello
    Executed: stage hello
    Executed: prime hello
    Executed parts lifecycle
    Created new layer
    Cmd set to ['/usr/bin/hello', '-t']
    Labels and annotations set to ['org.opencontainers.image.version=1.0', 'org.opencontainers.image.title=hello', 'org.opencontainers.image.ref.name=hello', 'org.opencontainers.image.licenses=Apache-2.0', 'org.opencontainers.image.created=2022-06-30T09:07:38.124741+00:00']
    Exported to OCI archive 'hello_1.0_amd64.rock'

At the end of the process, a file named :file:`hello_1.0_amd64.rock` should be
present in the current directory. This is the ROCK that Rockcraft has created
for us in `OCI archive format`_, which is simply a :command:`tar` archive.

Run the ROCK in Docker
----------------------

First, use the version of :command:`skopeo` supplied with Rockcraft to publish
the recently created ROCK to Docker's registry:

.. literalinclude:: code/hello-world/task.yaml
    :language: bash
    :start-after: [docs:skopeo-copy]
    :end-before: [docs:skopeo-copy-end]
    :dedent: 2

Now run the ``hello`` command from the ROCK:

.. literalinclude:: code/hello-world/task.yaml
    :language: bash
    :start-after: [docs:docker-run]
    :end-before: [docs:docker-run-end]
    :dedent: 2

Which should print:

..  code-block:: text
    :class: foo

    hello, world

.. include:: /links.txt