---
title: "AmpSeq_FresnedoScripts2019"
author: "SMGP"
date: "4/7/2021"
output:
  html_document: default
  pdf_document: default
---

# Ampsec Scripts from Fresnedo 2019
Info obtained and modified from https://github.com/JFresnedo/AmpSeq/blob/master/Preliminaries.md

# 1. Initial Singularity and AmpSeq image Setup
These steps are for initial Singularity AmpSeq Setup using the HCC clusters at UNL
if you have already done this you skip and go to Step 2.
<First log in to the HCC using the terminal in Rstudio>

Changing from home directory to work directory 
```{bash}
cd $WORK
```

Verify you are in working directory
```{bash include=TRUE}
pwd
```

Creating a working folder  
```{bash include=FALSE}
mkdir AmpSeq
```

Change location to new folder created
```{bash}
cd AmpSeq
```

Cloning repository (containing example and codes)
```{bash}
git clone https://github.com/JFresnedo/AmpSeq.git
```

Singularity won't load in login node so changing to a working node
```{bash}
srun --nodes=1 --ntasks-per-node=2 --mem-per-cpu=32g --time=2:00:00 --pty $SHELL
```

Loading Singularity on the HCC
```{bash}
module load singularity/3.2
```

Pulling the container (info from  github and https://singularity-hub.org/collections/2392) to generate the AmpSeq.sif
```{bash}
singularity pull --name AmpSeq.sif shub://JFresnedo/AmpSeq:ampseq
```

to load the container 
```{bash}
singularity shell AmpSeq.sif
```

To test open 
```{bash}
vcftools or etc
```


## 2. Executing AmpSeq and runing provided example
Use the MD files from the github example

Changing to folder AmpSec/
```{bash}
cd AmpSec/
```

