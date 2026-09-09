## Reproducing HDS-Practical environment

The purpose of this project is to preserve the Python and R environments used to create toy patient data so that they can be reproduced. **The starting data can be viewed within the `data/` folder.**

## Getting Started

**Downloads**
Start with downloading 5 things:
```
# environmental.yml
# renv.lock files.
# analyze.R (script file)
# analyze.py (script file)
# DockerfileMa
```
**Reproducing the Python Environment**
Open a terminal and set directory to the location of downloaded files
```
# Open conda to run the bellow function to view the toy patient data
conda env create -f environment.yml
conda activate repro-demo
python analyze.py
```
**Reproducing the R Environment**
Open RStudio and set directory to the location of downloaded files
```
# Open RStudio with renv installed with new script to view the toy patient data (saved as df)
renv::restore
renv::status
source(analyze.R)
View(df)
```
**Reproducing the Docker file**
```
# Open a terminal with a working directory containing the dockerfilema file
# Will produce the patient toy data after performing the docker run function
docker build -f DockerfileMa -t dockerfilema .
docker run --rm dockerfilema
```
## Other additions
The `scripts/` folder contain the Python and R scripts used for the project for viewing. The `.gitignore` file is used to prevent any `.csv` data from being tracked by Git within this repository. The `AI_USAGE.md` and `Graduate_Addendum` provides additional context for my personal thoughts in developing the reposetory. 
