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
* git init is a one-time command you use during the initial setup of a new repo. 
* Executing this command will create a new .git subdirectory in your current working directory. 
* This will also create a new master branch. 
---

# Remove
* rm -rt .git
* rd /s /q .git
---
# Git status
* In the output, notice the file in red under untracked files. 
* Untracked means that Git sees the file but has not started tracking changes yet.
---
# .gitignore
* echo niaou >> .gitignore
* echo "" > .gitignore
* echo null > .gitignore
---
# Saving changes to the repository
* cd /path/to/project 
* echo "test content for git tutorial" >> CommitTest.txt 
* git add CommitTest.txt (ή git add –all)
* git commit -m "added CommitTest.txt to the repo"





