# First Steps
1. Download Git:
             https://git-scm.com/downloads
2. Open **cmd**
3. Verify the installation was successful
	    ```git --version```
---
# Set config values
#### Configure your Git username and email
* `git config --global user.name "Marianna Skiada"`<br/>
* `git config --global user.email "mskiada@aueb.gr"`<br/>
* `git config --list`
---
# Help
* `git help –config`
---
# Git Workflow
* __A Working Directory:__ where you'll be doing all the work: creating, editing, deleting and organizing files<br/>
* __A Staging Area:__ where you'll list changes you make to the working directory<br/>
* __A Repository:__ where Git permanently stores those changes as different versions of the project<br/><br/>
![](https://github.com/mskiada/softsy_full_2017/blob/master/images/workflow.jpg)
---
# Initializing a new repository
* To create a new repo, use the `git init` command.
* `git init` is a one-time command you use during the initial setup of a new repo. 
* Executing this command will create a new .git subdirectory in your current working directory. 
* This will also create a new master branch. 
---

# Remove Repository
* `rm -rt .git`
* `rd /s /q .git`
---
# Git status
* In the output, notice the file in red under untracked files. 
* Untracked means that Git sees the file but has not started tracking changes yet.
---
# .gitignore
* echo "a gitignore file">> .gitignore
* echo "" > .gitignore
* echo null > .gitignore
---
# Saving changes to the repository
1. Find direcory `cd /path/to/project `
2. Create new file `echo "" >> Example.java`
3. Add file to staging  `git add Example.java` (ή git add –all)
4. Check the current state of the repository `git status`
5. check the differences between the working directory and the staging area `git diff`
6. Save changes in repository `git commit -m "added Example.java to the repo"`
---
# git add
In order for Git to start tracking *Example.java*, the file needs to be added to the staging area.
We can add a file to the staging area with: `git add Example.java`

---
# git diff
Since the file is tracked, we can check the differences between the working directory and the staging area with:
`git diff filename`
Here, filename is Example.java so `git diff Example.java`
---
# git commit
* A commit is the last step in our Git workflow.
* A commit permanently stores changes from the staging area inside the repository.
the option -m followed by a message. Here's an example: git commit -m "Complete first line of dialogue"
Standard Conventions for Commit Messages:
- Must be in quotation marks
- Written in the present tense
- Should be brief (50 characters or less)
---
# git log
Often with Git, you'll need to refer back to an earlier version of a project. Commits are stored chronologically in the repository and can be viewed with `git log`<br/>
In the output, notice:
* A 40-character code, called a SHA, that uniquely identifies the commit. This appears in orange text.
* The commit author (you!)
* The date and time of the commit
* The commit message




