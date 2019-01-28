.. _s onf:

========================
Configuring the Pipeline
========================

.. _runyaml:

Your Pipeline Ru The pipeline requires some information from the user to run.
In the current build of the pipeline, you, the user, will have to modify the 
``run.yaml`` file located in the root of the project.  It has 24 fields and looks
like the following:

.. co lock:: yaml
 	# Infrastructure configuration
	STACK_NAME : 
	RESOURCE_CFN_TMPL_DEPLOY_BUCKET : 
	GPCE_SSH_KEY_PAIR : 
	START_POINT : 
	QC : 

	# Input/output file locations
	INPUT : 
	OUTPUT : 
	REF_URI : 
	USER_ASSETS_URI : 

	# User assets
	SAMPLE_FILE : 
	TARGET : 
	SENTIEON_PACKAGE_NAME : 
	SENTIEON_LICENSE_NAME : 

	# Cohort information
	NUM_SAMPLES : 
	COHORT_PREFIX : 
	BUILD : 
	OME : 

	# Google Cloud Platform related configuration
	CLOUDSPAN_MODE: 
	GCP_CREDS_FILE : 
	CLOUD_TRANSFER_OUTBUCKET : 
	PROJECT_ID : 
	ZONE : 
	CLOUD_FILE: 

	# Docker
	DOCKER_ACCOUNT: 


Each field must have a value for the pipeline to run.  Listed below are
descriptions for each of the fields.  For more information about the yaml
file format, see the `official yaml website`_.

*Infrastructure configuration*

* .. _STACK_NAME: The name of the Cloudformation (CFN) stack
* .. _RESOURCE_CFN_TMPL_DEPLOY_BUCKET: Bucket name (e.g. pipeli un)
* .. _GPCE_SSH_KEY_PAIR: Accou pecific key pair for using AWS EC2 (e.g. John_Key)
* .. _START_POINT: The format of the input files (fastq|bam|gvcf|vcf)
* .. _QC: List of what QC to run (BAM|VCF)

*Input/output file locations*

* .. _INPUT: S3 location of your fastq files (e.g. s3://pipeli un/fastqs/)
* .. _OUTPUT: S3 location of all resulting files (e.g. s3://pipeli un/results/
* .. _REF_URI: S3 location of reference genome files (e.g. s3://GRCh eferences/)
* .. _USER_ASSETS_URI: S3 location for users' assets upload


*User assets*

* .. _SAMPLE_FILE: Name of the file which has the list of sample names (prefix to .fastq.gz)
* .. _TARGET: Interval BED file if ome is "wes" (e.g. Exo Gv3.bed)
* .. _SENTIEON_PACKAGE_NAME: The Sentieon software file (e.g. sentie enomi 01711.01.tar.gz)
* .. _SENTIEON_LICENSE_NAME: Name of the Sentieon license file (e.g mylicense.lic)

*Cohort information*

* .. _NUM_SAMPLES: Number of samples to run, e.g. the length of SAMPLE_FILE
* .. _COHORT_PREFIX: Prefix for your resulting VCF (e.g. cohort1)
* .. _BUILD: Build of the reference genome (GRCh38 | GRCh37)
* .. _OME: Choice between whole exome or whole genome (wgs | wes)

*Google Cloud Platform related configuration*

* .. _CLOUDSPAN_MODE: Which hail method to run (validation|qc)
* .. _GCP_CREDS_FILE: Absolute path to your Google Cloud service account json (e.g. /Users/Keys/service_creds.json)
* .. _CLOUD_TRANSFER_OUTBUCKET: The Google Cloud bucket to which VCF will be transferred (e.g. gs://pipeli un)
* .. _PROJECT_ID: ID for your Google Cloud Project (e.g. GCP assigns names like "summ at 78325")
* .. _ZONE: The zone in which you want your data to be stored on Google Cloud (e.g.  as )
* .. _CLOUD_FILE: The name of the file in USER_ASSETS which has the g elated template file

*Docker Information*

* .. _DOCKER_ACCOUNT: The name of your docker account (if not using the default: ucsfpsychcore)

Next Step 
Once run.yaml has been properly filled out, the pipeline is ready to be run. Please see :ref:`run` to continue.

.. _official yaml website: http://yaml.org
