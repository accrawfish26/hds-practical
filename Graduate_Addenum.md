# Graduate addendum

## Question:
**Set up both a conda/uv (python) and renv (R) environment for the same toy project, and write 3-5 sentence comparing the workflows.**

## Response:
With the conda and uv, I had found that uv more convenient than conda itself. I felt the waiting period was cut short by using `uv.sync` compared to `mamba env create` and saving and reproducing data from a `uv.lock`. But both regardless achieve similar end goals for the python environment.

The workflow is different for R programming with renv. I am biased towards this as I had more familiarity, which may had influenced the fact it was easier to pick up the concepts of renv than conda. the basic premise centers on creating a snapshot of packages and code saved within a script using a `renv.lock` file that can be activated through `renv::activate()` to share for reproducibility. 

I can see there no right or wrong, but interesting that there are some overlap with the activate/deactivate commands, both having a locked file that requires packages uploaded into, and have respective command required to make that locked file. 
