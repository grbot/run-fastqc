# Nextflow test workflow  

A Nextflow workflow that runs FastQC on Fastq reads and then combines them into a MultiQC report. FastQC and MutliQC are setup on a Docker container. The nextflow script pulls the Docker container and converts it to a Singularity container on the fly. See the `nextflow.log` for settings to run on a Slurm cluster.

## To setup in `.bashrc`

```
# Path exports
export PATH=$PATH:/cbio/soft/jdk-11.0.2/bin:/cbio/soft/nextflow/

# Environmental variable exports
export JAVA_CMD=/cbio/soft/jdk-11.0.2/bin/java
export JAVA_HOME=/cbio/soft/jdk-11.0.2
```

## To run

`nextflow -log nextflow.log run -w /ceph/cbio/users/gerrit/scratch/16s/nextflow-workdir -c nextflow.config main.nf -profile slurm` 

```
$ squeue 
             JOBID PARTITION     NAME     USER ST       TIME  NODES NODELIST(REASON)
              2324      Main tl.rFQC. cbio-ws-  R       0:12      1 cbio-ws-1
              2325      Main tl.rFQC. cbio-ws-  R       0:12      1 cbio-ws-1
              2327      Main tl.rFQC. cbio-ws-  R       0:12      1 cbio-ws-1
              2329      Main tl.rFQC. cbio-ws-  R       0:12      1 cbio-ws-1
              2336      Main tl.rFQC. cbio-ws-  R       0:12      1 cbio-ws-1
```
## Workflow diagram

![workflow](https://raw.githubusercontent.com/grbot/run-fastqc/master/run-fastqc_flowchart.png "Nextflow workflow")
