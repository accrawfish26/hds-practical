## Reproducing HDS-Practical environment

The purpose of this project is to preserve the Python and R environments used to create toy patient data so that they can be reproduced. **The starting data can be viewed within the `data/` folder.**

## To reproduce...
Without digging around too much, simply download the `Environment.yml` and `renv.lock` to reproduce the coding envionrments used to generate the toy patient data. Read bellow if interested in knowing the purpose of the other files

## Python
`Environment.yml` was created through Conda to document the Python environemnt used for the project. 

**To reproduce, I would reccoemnd using these codes then run the script:**

Set working directory as the location of downloaded `environment.yml`    

Call to open the file through conda:  
`conda env create -f environment.yml`  

Activate the environment:  
`conda activate repro-demo`    

## RStudio
`renv.lock` was created through R `renv` package in RStudio to document the R envionrment used for the project.  

**To reproduce, I would reccomend use these codes then run the script:**  

  Open the renv enviornemnt:  
  `renv::restore()`  
 
  Open and run the R. script found in `scripts/` file
  
## Docker
`DockerfileMa` was created as a container based on `Environment.yml` environment to run within Python. 

**To reproduce, I would reccomemend start with these codes, then run the script:** 

  Build Docker image (or package):   
    `docker build -f DockerfileMa -t hds-practical-lab1`  
  
  Then run the container (contains all the set packages):  
    `docker run --rm hds-practical-lab1`  
## Other additions
The `scripts/` folder contain the Python and R scripts used for the project for viewing. The `.gitignore` file is used to prevent any `.csv` data from being tracked by Git within this repository. The `AI_USAGE.md` and `Graduate_Addendum` provides additional context for my personal thoughts in developing the reposetory. 
