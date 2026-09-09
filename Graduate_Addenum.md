# Graduate addendum

## Question:
**Set up both a conda/uv (python) and renv (R) environment for the same toy project, and write 3-5 sentence comparing the workflows.**

## Response:
With the conda and uv, I had found that uv more convenient than conda itself. I felt the waiting period I had with mamba/conda was cut short by using `uv.sync` compared to `mamba env create`, which goes for saving/reproducing data from a `uv.lock` as well. Both still achieve similar end goals for the python environment, but the uv was easier to understand and faster.

The workflow is entirely different for the R renv package. Of which I had prefered compared to uv as I had prior exposure to R programming. The basic premise centers on creating a snapshot of packages and code saved within a script using a `renv.lock` file that can be activated through `renv::activate()` to share for reproducibility. It pretty straight forward in sharing this with a person who may be less familiar as there lower demands in setting up and launching a  `renv.lock` file. 

I do not think there is a right or wrong way to do this, but interesting that there are some overlap between the two approaches with shared premis of activate/deactivate, some variation of a locked file, and a way to re-open the shared locked file for other to reproduce that environment. Personally, I would use renv.lock as it what I am familiar with, but with conda or uv, as I found less error had occured when trying to navigate it. 
