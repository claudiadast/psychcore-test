.. _sec-overview:

=================
Pipeline Overview
=================

Genomics Workflow
-----------------
The PsychCore NGS pipeline is a serverless, automated, easy to use genomics 
pipeline for calling variants on large cohorts of human sequencing samples.  
The workflow of the pipeline is as follows:

.. image:: PipelineWorkflow.png

The pipeline takes gzipped paired end sequencing fastq files (R1|R2.fastq.gz) 
for each sample and aligns them to a specified reference build, using BWA MEM.  
Several BAM processing steps (Picard and GATK) follow to produced a final 
processed BAM which is haplotyped using Sentieon's* Haplotyper module.  
These steps are done in parallel for each sample in the cohort.  
After Haplotyper is run, joint genotyping is performed accross the entire 
cohort with Sentieon's Genotyper, producing a VCF which undergoes VQSR (GATK)
which outputs the final VCF.

.. _infrastructure:

Pipeline Infrastructure
-----------------------
Stepfunctions, Batch, Lambda, Docker oh my!


(*) A Note about Sentieon
-------------------------
Sentieon developes and supplies a suite of bioinfromatics analyis tools for 
processing genomics data.  In 2016, Sentieon won the PrecisionFDA Truth_ and 
Consistency_ challenges. Sentieon also won first place in 
`ICGC-TCGA Dream Mutation Calling Challenge`_. 
For more information see Sentieon's homepage here_.

.. _Truth: https://precision.fda.gov/challenges/truth/results
.. _Consistency: https://precision.fda.gov/challenges/consistency/results
.. _ICGC-TCGA Dream Mutation Calling Challenge: https://www.synapse.org/#!Synapse:syn312572/wiki/247695
.. _here: https://www.sentieon.com