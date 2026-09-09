# Reproducing HDS-Practical environment

The purpose of this project is to preserve the Python and R environments used to create toy patient data so that they can be reproduced. **The starting data can be viewed within the `data/` folder.**

## To reproduce...
Without digging around too much, simply download the `Environment.yml` and `renv.lock` to reproduce the coding envionrments used to generate the toy patient data. Read bellow if interested in knowing the purpose of the other files

## Python
`Environment.yml` was created through Conda to document the Python environemnt used for the project. 
## RStudio
`renv.lock` was created through R `renv` package in RStudio to document the R envionrment used for the project.
## Docker
`DockerfileMa` was created as a container based on `Environment.yml` environment to run within Python. 

## Other additions
The `scripts/` folder contain the Python and R scripts used for the project for viewing. The `.gitignore` file is used to prevent any `.csv` data from being tracked by Git within this repository. The `AI_USAGE.md` and `Graduate_Addendum` provides additional context for my personal thoughts in developing the reposetory. 
