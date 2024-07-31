# deeplabcutUCSF
This is a protocol guide for using deeplabcut on zebrafish data. 

**Using DeepLabCut on HPC Cluster**

First, you need to transfer your local DeepLabCut project folder to the cluster. You can use scp for this purpose.

`scp -r /path/to/your/local/DeepLabCut_project your_username@log1.wynton.ucsf.edu:/path/to/your/destination/folder`

Use SSH to log into the Wynton HPC cluster. 

`ssh your_username@wynton.ucsf.edu`

To use DeepLabCut, you'll need to set up a Conda environment. However, since module loading and conda environment activation are only possible on compute nodes, you should perform these actions within a job script.

`mkdir -p ~/DeepLabCut_jobs`
`cd ~/DeepLabCut_jobs`
`nano setup_env.sh`

Edit the script. 

```
#!/bin/bash
#$ -S /bin/bash
#$ -cwd
#$ -l h_rt=02:00:00  # 2 hours of runtime
#$ -N DLC_Setup

# Load necessary modules
module load python/3.8  # Load Python module
module load cuda/11.3   # Load CUDA if using GPU

# Create and activate the conda environment
conda create -n dlc_env python=3.8 -y
source activate dlc_env

# Install DeepLabCut
pip install deeplabcut
```
