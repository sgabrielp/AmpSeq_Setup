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
<Code>XXXXXXX <Code>