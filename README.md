# AmpSeq_Setup
AmpSeq General Setup

#Cloning repository (containing example and codes)
git clone https://github.com/JFresnedo/AmpSeq.git

#singularity won't load in login node so changing to a working node
srun --nodes=1 --ntasks-per-node=2 --mem-per-cpu=32g --time=2:00:00 --pty $SHELL

#Loading Singularity on the HCC
module load singularity/3.2

#Pulling the container (info from the github and https://singularity-hub.org/collections/2392)
singularity pull --name AmpSeq.sif shub://JFresnedo/AmpSeq:ampseq
# This will generatate the AmpSeq.sif 
to load the container 
singularity shell AmpSeq.sif



#To test open 
vcftools or etc

Log in your HPC service and change directory (cd) to the working directory

Get the information from the AmpSeq GitHub repository by executing:


```{bash}
pwd 
```


```bash
ls -lah
```

```bash
git clone https://github.com/JFresnedo/AmpSeq.git
```
Get the Singularity container with all the software needed
```bash
singularity pull --name AmpSeq.sig shub://JFresnedo/AmpSeq:ampseq
# You will see a warning which you can disregard, actually, a progress bar will show you the download progress of the Singularity container
```
Load Singularity in your HPC service

Test the container works by executing a simple command:
```bash
singularity exec vcftools
```

