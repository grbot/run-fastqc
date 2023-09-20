# Nextflow test workflow  

A Nextflow workflow that runs FastQC on Fastq reads and then combines them into a MultiQC report. FastQC and MutliQC are setup on a Docker container. See the `nextflow.log` for run settings.

## To run

 `NXF_VER=21.10.6 nextflow run main.nf -c nextflow.config -w /home/test01/nextflow-work -profile standard -with-trace -with-report -with-timeline` 

## Workflow diagram

![workflow](https://raw.githubusercontent.com/grbot/run-fastqc/master/run-fastqc_flowchart.png "Nextflow workflow")
