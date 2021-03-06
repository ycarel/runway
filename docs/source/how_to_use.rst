How To Use
==========

Getting Started
^^^^^^^^^^^^^^^
- Structure your project repo with environments & modules (see
  :ref:`repo-structure` )
- Execute ``runway init`` to create a ``runway.yml`` file at the root of the
  environment (e.g. at the repo root)
- Define per-environment config options/enablement for each module (see
  :ref:`module-configurations` )

Basic Deployment Commands
^^^^^^^^^^^^^^^^^^^^^^^^^
- ``runway test`` (aka ``runway preflight``) - execute this in your environment to catch errors; if it exits ``0``, you're ready for...
- ``runway plan`` (aka ``runway taxi``) - this optional step will show the diff/plan of what will be changed. With a satisfactory plan you can...
- ``runway deploy`` (aka ``runway takeoff``) - if running interactively, you can choose which deployment to run; otherwise (i.e. on your CI system) each deployment will be run in sequence.

Runway execution without a TTY
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Runway allows you to set an environment variable to allow execution without a TTY or if STDIN is closed. This allows users to execute runway deployments in their CI/CD infrastructure as code deployment systems avoiding the ``EOF when reading a line`` error message. In order to execute runway without a TTY, set the ``CI`` environment variable before your ``runway deploy`` execution. 

.. note:: Executing runway in this way will cause runway to perform updates in your environment without prompt.  Use with caution. 

Removing Deployments
^^^^^^^^^^^^^^^^^^^^
- ``runway destroy`` (aka ``runway dismantle``) - if running interactively, you can choose which deployment to remove; otherwise (i.e. on your CI system) every deployment will be run in reverse sequence (use with caution).
