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


================================
Setting up the Pipeline Platform
================================

------------------------
1. Create an AWS Account
------------------------

If you do not have one already, please create an Amazon Web Services (AWS) account, as this will be the platform upon which the pipeline is executed. 

-----------------------------
2. Submit AWS Limit Increases
-----------------------------

Depending on the current status of your AWS account and the number of samples on which you plan to call variants, you may need to increase the number of instance types to support the respective sample scale. 

To check the current status of your AWS limits, go to the EC2 dashboard in the AWS console, followed by the "Limits" tab on the left panel. If you need more instances of a certain type, find that instance type and click on "Request limit increase". Please note that this may take some time to process, so it should be done early.

---------------------------------
3. Obtain a Sentieon License File
---------------------------------

Because the current build only supports Sentieon for the variant calling steps, you will need to obtain a Sentieon license:

* A Free Trial is offered here: https://www.sentieon.com/home/free-trial/. 
* Once you obtain the license file, please upload it to S3.

==========================
Setting up Dev Environment
==========================

-----------------------------------------
4. Install Conda, VirtualEnv, or whatever
-----------------------------------------

See: https://conda.io/miniconda.html

* If you have python 2.7 installed currently, pick that installer.
* If you have python 3.6 installed currently, pick that.
* Run the installer. The defaults should be fine.

----------------------------------
5. Create a Python 3.6 environment
----------------------------------

::

   $ conda create -n psy-ngs python=3.6

----------------------------------------------------------------------------------------
6. Activate the newly created environment (you may need to start a new terminal session)
----------------------------------------------------------------------------------------

::

   $ source activate psy-ngs

You can verify that the environment has activated by checking the python version (if it is different than your base)::

   $ python --version

You should also see the environment name prepended to your shell prompt, e.g.::


   (psy-ngs) $ echo "See the environment name?"

----------------------------------------------------------------------------------------------------------
7. After activating the environment for this project, install the python dependencies into the environment
----------------------------------------------------------------------------------------------------------

::

   (psy-ngs) $ cd path/to/this/repo/
   (psy-ngs) $ pip install -r requirements.txt

----------------------
8. Run the application
----------------------

::

   (psy-ngs) $ cd path/to/this/repo/
   (psy-ngs) $ python rkstr8.py proj-mngr

----------------------------------
9. Managing pipelines and projects
----------------------------------

Note to devs:
- Keep an updated requirements.txt (note to developers)

