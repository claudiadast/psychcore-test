.. Psychcore NGS Germline Variant Pipeline documentation master file, created by
   sphinx-quickstart on Thu Mar  8 10:02:37 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to Psychcore NGS Germline Variant Pipeline's documentation!
===================================================================

.. toctree::
   :maxdepth: 2
   :caption: Contents:



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

About
=====

The following NGS pipeline was developed by the UCSF Psychiatry Bioinformatics Core (PsychCore) team. The current build is equipped to automatically call variants on both whole genome and whole exome samples and produce an output VCF, all based on the user's input. Please note that this pipeline is still being developed and will include more features in the future, including: downstream analysis in Hail via Google Cloud's Dataproc, the option to run variant calling on GATK4, and a simple web user-interface to launch it off.

==========================
Setting up Dev Environment
==========================

-----------------------------------------
1. Install Conda, VirtualEnv, or whatever
-----------------------------------------

See: https://conda.io/miniconda.html

* If you have python 2.7 installed currently, pick that installer.
* If you have python 3.6 installed currently, pick that.
* Run the installer. The defaults should be fine.

----------------------------------
2. Create a Python 3.6 environment
----------------------------------

::

   $ conda create -n psy-ngs python=3.6

----------------------------------------------------------------------------------------
3. Activate the newly created environment (you may need to start a new terminal session)
----------------------------------------------------------------------------------------

::

   $ source activate psy-ngs

You can verify that the environment has activated by checking the python version (if it is different than your base)::

   $ python --version

You should also see the environment name prepended to your shell prompt, e.g.::


   (psy-ngs) $ echo "See the environment name?"

----------------------------------------------------------------------------------------------------------
4. After activating the environment for this project, install the python dependencies into the environment
----------------------------------------------------------------------------------------------------------

::

   (psy-ngs) $ cd path/to/this/repo/
   (psy-ngs) $ pip install -r requirements.txt

----------------------
5. Run the application
----------------------

::

   (psy-ngs) $ cd path/to/this/repo/
   (psy-ngs) $ python rkstr8.py proj-mngr

----------------------------------
6. Managing pipelines and projects
----------------------------------

Note to devs:
- Keep an updated requirements.txt (note to developers)
