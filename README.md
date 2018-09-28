# Nextflow test workflow  

A Nextflow workflow that runs FastQC on Fastq reads and then combines them into a MultiQC report. FastQC and MutliQC are setup on a Docker container. The nextflow script pulls the Docker container and converts it to a Singularity container on the fly. See the `nextflow.log` for settings to run on a Slurm cluster.

To be able to mount the `/data` directory on the cluster you need to have the mount defined in your Docker/Singularity container e.g. [see](https://github.com/h3abionet/h3abionet16S/blob/master/dockerfiles/fastqc/Dockerfile)

*To run*: `nextflow -log nextflow.log run -w /data/users/cbio-ws-u24/nextflow-workdir -c nextflow.config main.nf -profile slurm` 

