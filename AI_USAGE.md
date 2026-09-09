## AI Usage transparency

### Prompt 1

**Uploaded the full error from the follow-along about error that Mamba cannot create an envionrment because `environment.yml` due to the packages within it.**

**Chat GPT initial response**: "This means Mamba cannot create the environment because your `envionrment.yml` is asking for two package version that cannot coexist"

**Chat GPT recommendation**: "The fix is to remove the `numphy=1.19` requirement from `environment.yml`. That version is too old for panda 2.2.

**My edits**: I had followed the recommendation by removing `numphy=1.19` and had successfully resolved the error and was able to use `environment.yml`


=========================
### Prompt 2

**Uploaded the full error when attempting to push my `renv.lock` through `git push` and was returned that there is nothing to update.**

**Chat GPT initial response**: "The key issue is: `renv.lock` is not showing under `git status` as untracked because it is already tracked by Git (or otherwise already knwon to Git), but your other files are untracked... Notice renv.lock is NOT in that list."

"One other important thing, your promt says: /c/users/crawf/desktop/app_comp_hds/app-comp-hds-r (master) and your `git pull` says: ... * branch master -> FETCH_HEAD. So you're working on the master branch, not main."

**Chat GPT recommendation**: "Since you're currently on `master`, rename the local branch to `main` with `git branch -m master main`. Then push `main` to GitHub and set it as the upstream: `git push -u origin main`"

**My edits**: I had followed the recommendation and learned about the importance of paying attention to branches and how to switch between them. I swapped back to main and was able to push renv.lock into the GitHub. 

=========================
### Prompt 3

**A silly mistake in hinsight, but was trying to push the scripts/ folder but was not working. I had asked and shared full error that was simalar to number 2   where it said there is nothing to commit after I performed `git add`.**

**Chat GPT initial response**: "Yes - and this output tells us something useful. You ran: `git add scripts` but `git status` doesn't show scripts/ as untracked, because Git is apparently already tracking the files inside scripts." 

"Ah - that's the whole reason. If `ls scripts` shows nothing, then scripts/ is an empty folder. Git does not track empty folders. Git only tracks files."

**Chat GPT recommendation**: "If you put a file inside it, then `git add scripts/` `git commit -m "Add scripts"` `git push` will put the folder in GitHub."

**My edits**: I recall from class and from the above about empty folders cannot be added to Git. I had went ahead and used the `mv` to move the `.R` and `.py` scripts into the folder and ran the git commands again to upload successfully. 

========================
### Prompt 4

** Tried to perform docker for both R and Python environment and had to learn that I cannot merge 2 two seperate sources into one place. I end up using what was shared through class follow along to help build an understanding of docker##

**Chat GPT initaial response**: "Yes. Since you've developed the R/renv and Mamba Dockerfiles separately, the next step is to combine them into one Dockerfile. But there's one important issue first: you can't combine two `from` lines into one Dockerfile. You need to choose one base image and install the other environmet into it.

**Chat GPT recommendation**: I'd recommend using the Miniforge/Mamba image as the base, then install R and `renv` into that same container.

**My edits**: I decided against that reccomendation and create two different container for each respective program for Mamba - envionrment.yml and R - renv.lock. I then did the `docker build -f DockerfileMa` and `docker run --rm hds-practical-lab1` to get the reproducible output. This was then added to github.

### 4.5
**Tried to perform `docker run --rm hds-practical-lab1` and had learned about understanding what commands are file names that I need to be clear/consistant with.

**Chat GPT initial response**: "The error means you haven't built an image named `hds-practical-lab1` yet. 

**Chat GPT recommendation**: "If your dockerfile is named `dockerfilema` then `docker build -f DockerfileMa -t hds-practical-lab1 .

**My edits**: I realised that hds-practical-lab1 was related to an old testing when playing with the docker commands that I had kept when trying to run. From GPT recommendation, I replaced the `hds-practical-lab1` with `dockerfilema` and that had worked.


