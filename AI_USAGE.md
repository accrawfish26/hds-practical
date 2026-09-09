## AI Usage transparency

### Prompt 1
**Model:** ChatGPT  
**Error:** 
```
error libmamba Could not solve for environment specs The following packages are incompatible ├─ numpy =1.19 * is requested and can be installed; └─ pandas =2.2 * is not installable because there are no viable options ├─ pandas [2.2.0|2.2.1|2.2.2] would require │ └─ numpy >=1.22.4,<2.0a0 *, which conflicts with any installable ver; ├─ pandas [2.2.0|2.2.1|2.2.2] would require │ └─ numpy >=1.23.5,<2.0a0 *, which conflicts with any installable ver; ├─ pandas 2.2.0 would require │ └─ numpy >=1.26.3,<2.0a0 *, which conflicts with any installable ver; ├─ pandas [2.2.1|2.2.2] would require │ └─ numpy >=1.26.4,<2.0a0 *, which conflicts with any installable ver; ├─ pandas [2.2.2|2.2.3] would require │ └─ numpy [>=1.22.4 *|>=1.22.4,<3 *] but there are no viable options │ ├─ numpy [1.23.5|1.24.0|...|1.26.2] conflicts with any installabl; │ ├─ numpy 1.26.3 conflicts with any installable versions previousl; │ ├─ numpy 1.26.4 conflicts with any installable versions previousl; │ ├─ numpy [1.22.4|1.23.0|...|1.23.4] conflicts with any installabl; │ ├─ numpy [2.0.0|2.0.1|...|2.5.2] conflicts with any installable v; │ └─ numpy 2.5.0rc1 would require │ └─ _numpy_rc =* *, which does not exist (perhaps a missing cha; └─ pandas 2.2.3 would require └─ numpy >=1.21,<3 * but there are no viable options ├─ numpy [1.23.5|1.24.0|...|1.26.2] conflicts with any installabl; ├─ numpy 1.26.3 conflicts with any installable versions previousl; ├─ numpy 1.26.4 conflicts with any installable versions previousl; ├─ numpy [1.22.4|1.23.0|...|1.23.4] conflicts with any installabl; ├─ numpy [2.0.0|2.0.1|...|2.5.2] conflicts with any installable v; ├─ numpy 2.5.0rc1, which cannot be installed (as previously expla; └─ numpy [1.21.0|1.21.1|...|1.22.3] conflicts with any installabl. critical libmamba Could not solve for environment specs
```
I first asked ChatGPT what this error meant, then asked how to fix it.

**ChatGPT response:** This means Mamba cannot create the environment because your `envionrment.yml` is asking for two package version that cannot coexist.

**ChatGPT suggested fix:** The fix is to remove the `numphy=1.19` requirement from `environment.yml`. That version is too old for panda 2.2.  

**My edit:** I had followed the recommendation by editing my code to remove `numphy=1.19`. By removing the package, I was able to verify the error was resolved that prevented `environment.yml` file to run.
   
=========================
### Prompt 2
**Model:** ChatGPT  
**Error:**
```
error: failed to push some refs to 'https://github.com/accrawfish26/hds-practical'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
(base)
crawf@ACcrawfish MINGW64 /c/users/crawf/desktop/app_comp_hds/app-comp-hds-r (main)
$ git push https://github.com/accrawfish26/hds-practical
fatal: The upstream branch of your current branch does not match
the name of your current branch.  To push to the upstream branch
on the remote, use

git push https://github.com/accrawfish26/hds-practical HEAD:master

To push to the branch of the same name on the remote, use

git push https://github.com/accrawfish26/hds-practical HEAD

To choose either option permanently, see push.default in 'git help config'.

To avoid automatically configuring an upstream branch when its name
won't match the local branch, see option 'simple' of branch.autoSetupMerge
in 'git help config'.
```
I first asked ChatGPT what this error meant, then asked how to fix it.

**Chat GPT inital response:** The key issue is: `renv.lock` is not showing under `git status` as untracked because it is already tracked by Git (or otherwise already knwon to Git), but your other files are untracked. /c/users/crawf/desktop/app_comp_hds/app-comp-hds-r (master) and your `git pull` says: ... * branch master -> FETCH_HEAD. So you're working on the master branch, not main.

**Chat GPT suggested fix:** Since you're currently on `master`, rename the local branch to `main` with `git branch -m master main`. Then push `main` to GitHub and set it as the upstream: `git push -u origin main`

**My edit:** I follow the recommendation by redirecting branch with `git push -u origin main` with the directory /c/users/crawf/desktop/accrawfish26/hs-practical.git (main). I verrified it by seeing the change of master to main within the terminal and where that the data was now stored in the main branch within my repository. 

**Model:** ChatGPT  
**Error:**
```
$ git fetch origin remote: Repository not found. fatal: repository '
accrawfish26/hs-practical.git' not found
```
I first asked ChatGPT what this error meant, then asked how to fix it.

**Chat GPT inital response:** Ah — I see the issue. The remote URL is misspelled.

**Chat GPT suggested fix:** fix hs-practical.git to hds-practical.git to directory

**My edit:** I fixed the spelling error and had sucessfully pushed branch to switch from `master` to `main` that allowed for sucessful `git push` with `renv.lock` file to the git repository. I was able to verify as the change in spelling removed the error.

=========================
### Prompt 3
**Model:** ChatGPT  
**Error:** 
```
docker build -t dockerfilema . [+] Building 0.1s (1/1) FINISHED docker:desktop-linux => [internal] load build definition from Dockerfile 0.0s => => transferring dockerfile: 2B 0.0s ERROR: failed to build: failed to solve: failed to read dockerfile: open Dockerfile: no such file or directory What's next: Debug this build failure with Gordon → docker ai "help me fix this build failure"
```
I first asked ChatGPT what this error meant, then asked how to fix it.

**ChatGPT initial response:** You found the problem. Docker is looking for a file literally named Dockerfile, but you don't have one. The attempted function `docker build -t dockerfilema .` serach for a dockerfile, but no assigned folder have that name.

**ChatGPT suggested fix:** Use `docker build -f DockerfileMamba -t dockerfilema .` to specifiy the name of file with `-f` that will allow for docker to run expected output with `docker run --rm dockerfilema`.

**My edits:** I had realised that I had changed the file name and had added the `-f` function. I edit the suggestion to specificy for `Dockerfilema` file that I wanted to be used for the Docker container. I was able to verify the error was gone because the function now had produced the desired container that can be found in the git repository.

========================
### Prompt 4

**Model:** ChatGPT  
**Error** 
```
cat > DockerfileLab1 << 'ENDLab1' > FROM condaforge/miniforge3:latest > FROM rocker/r-ver:4.5.1 > WORKDIR /hds-practical-lab1 > COPY environment.yml . > RUN mamba env create -f environment.yml && mamba clean -afy > COPY renv.lock . > RUN R -e "enstall.packages('renv', version = '1.1.5')" > RUN R -e "renv::restore()" > COPY . . > ENDLab1
```
I first asked ChatGPT what this error meant, then asked how to fix it.

**ChatGPT inital Response:** You're getting closer, but this Dockerfile will not work yet. There are three things to fix. 1. You have two FROM lines. 2. Typo: `enstall.packages.` 3. We need R + Mamba in the same base. So don't change your existing renv.lock or environment.yml. The next problem to solve is finding/using a base image that provides both R and Conda/Mamba, or installing one into the other.

**ChatGPT suggested fix:** The second FROM replaces the first stage. It does not combine them. So your container would be based on `FROM rocker/r-ver:4.5.1` only. Should be `install.packages` not `install packages.` I recommend starting with the R image and installing Mamba into it, rather than trying to combine two FROM statements.

**My edits:** For the first sugestion, I kept closer to the class practical, so I emmited the R FROM to keep only `FROM condaforge/miniforge3:latest`. I had fixed the spelling mistake. For the third, I had edited this by realising I can have two seperate container for each programming envionrment that would prevent the suggestion of downloading Mamba into R. It would be simpler to separate. This led to the `docker run --rm hds-practical-lab1` to get the reproducible output into github. I was able to verify all the above by deciding and acheiving python container for Docker. 

