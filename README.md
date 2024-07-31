# deeplabcutUCSF
This is a protocol guide for using deeplabcut on zebrafish data. 

**Using DeepLabCut on HPC Cluster**

First, you need to transfer your local DeepLabCut project folder to the cluster. You can use scp for this purpose.
`scp -r /path/to/your/local/DeepLabCut_project your_username@log1.wynton.ucsf.edu:/path/to/your/destination/folder`

Use SSH to log into the Wynton HPC cluster. 
`ssh your_username@wynton.ucsf.edu`
