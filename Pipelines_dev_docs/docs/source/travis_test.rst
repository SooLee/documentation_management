Travis Test
============

We use travis to test that the cwl workflow works properly. In order to run
a travis test, we need a travis.yml file and test files.

The .travis.yml file
---------------------

This travis.yml file tells travis what to do.

Example:

.. image:: images/travis_yml.png

.. note::
            This .travis.yml file is very similar for all the pipelines. You can
            follow the template and modify the docker image name. The version of
            the docker image does not need to be included. The .travis.yml file
            temple can be found `here <https://github.com/4dn-dcic/documentation_management/blob/master/Pipelines_dev_docs/docs/source/files/travis.yml>`_

Tests files
------------

Create a folder called ``tests``. Inside the folder add the following folders and
files:

- a ``test_files`` folder: This is where the input files reside.
- a ``test_input_json`` folder: This should contain a ``input.json`` file specifying the input files
  and parameters for the test.


Example:

.. image:: /images/input_json.png

- a ``json_null_test.py`` file. Just copy this `file <https://github.com/4dn-dcic/documentation_management/blob/master/Pipelines_dev_docs/docs/source/files/json_null_test.py>`_

- a ``test_cwl.sh`` file. Just copy this `file <https://github.com/4dn-dcic/documentation_management/blob/master/Pipelines_dev_docs/docs/source/files/tests_cwl.sh>`_


Configuring Travis in Github
-----------------------------
Go to https://travis-ci.com/ and sign up with Github.

Once you are signed in, go to your repository in https://travis-ci.com/, click in ``more options`` on the
top right, go to ``settings``, go to the section ``Environment Variables`` and add
you DockerHub username and password.

Now you can go back to the main travis CI page and click on ``Restart build``

.. warning:: Make sure the travis test passes before proceeding to the next steps.
