Build a ROCK with Rockcraft's GitHub Action
*******************************************

Within your GitHub repository, make sure you have
`GitHub Actions`_ enabled.

Navigate to ``.github/workflows``, open the YAML file where you want the ROCK
build to take place, and add the following steps:

.. literalinclude:: code/rockcraft-pack-action/rockcraft-pack.yaml
    :language: yaml

Commit and push the changes. This will trigger a new workflow run using
Rockcraft to pack your ROCK based on the :file:`rockcraft.yaml` file at your
project's root.

To learn how to publish this ROCK outside the GitHub build environment and how
to pass additional input parameters to this action, please refer to the
`action's documentation <Rockcraft GitHub pack action_>`_.

.. _`GitHub Actions`: https://docs.github.com/en/actions/quickstart

.. include:: /links.txt