# First Steps
1. Download Git:
             https://git-scm.com/downloads
2. Open <em>cmd</em>
3. Verify the installation was successful
	    `git --version`

# Set config values
#### Configure your Git username and email
*  `git config  --global user.name "Marianna Skiada" `
*  `git config  --global user.email "mskiada@aueb.gr" `
*  `git config  --list`

---
# Help
* `git help –config`

---
# Git Workflow
* <em>A Working Directory:</em> where you'll be doing all the work: creating, editing, deleting and organizing files<br/>
* <em>A Staging Area:</em> where you'll list changes you make to the working directory<br/>
* <em>A Repository:</em> where Git permanently stores those changes as different versions of the project<br/><br/><br/>
 ![](images/workflow.jpg)

---
# Initializing a new repository
* To create a new repo, use the `git init` command.
* `git init` is a one-time command you use during the initial setup of a new repo. 
* Executing this command will create a new .git subdirectory in your current working directory. 
* This will also create a new master branch. 

---
# Remove Repository
*  `rm -rf .git`
*  `rd /s /q .git`

---
# Git status
* In the output, notice the file in red under untracked files. 
* Untracked means that Git sees the file but has not started tracking changes yet.

---
# Saving changes to the repository
1. Find direcory `cd /path/to/project `
2. Create new file `Example.java`
3. Add file to staging  `git add Example.java` (or git add –all)
4. Check the current state of the repository `git status`
5. Save changes in repository `git commit -m "added Example.java to the repo"`

---
# git add
* In order for Git to start tracking <em>Example.java</em>, the file needs to be added to the staging area.
* We can add a file to the staging area with: `git add Example.java`

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
* Often with Git, you'll need to refer back to an earlier version of a project. Commits are stored chronologically in the repository and can be viewed with `git log`<br/>
In the output, notice:
* A 40-character code, called a SHA, that uniquely identifies the commit. This appears in orange text.
* The commit author (you!)
* The date and time of the commit
* The commit message

----
# Branching
* Up to this point, you've worked in a single Git branch called master.
* Git allows us to create branches to experiment with versions of a project. 
* It will have no effect on the master branch until you're ready to merge the happy ending to the master branch.

---
# git branch (1)
* Check what branch you are currently on `git branch`
* In the output, the `*` (asterisk) is showing you what branch you’re on.

----
# git branch (2)
* Create a new branch:  `git branch mitsos-branch` 
* Be sure to name your branch something that describes the purpose of the branch. 
* Also, branch names can’t contain whitespaces: mitsos-branch and mitsos_branch valid branch names, but mitsos branch is not.

---
# git checkout
* The master and fencing branches are identical: they share the same exact commit history. 
* You can switch to any existing branch with `git checkout branch_name`
* Once you switch branch, be now able to make commits on the branch that have no impact on master.
* You can continue your workflow, while master stays intact

---

#GIT TEAMWORK

---
# Cloning an existing repository
* `git clone remote_location clone_name`
* e.g. `git clone https://github.com/mariannitapaes/mariannitapaes.github.io.git .`
* Like `git init`, cloning is generally a one-time operation 
* Once a developer has obtained a working copy, all version control operations are managed through their local repository
* **remote_location** tells Git where to go to find the remote. This could be a web address, or a filepath, such as:
<em>https://github.com/mariannitapaes/mariannitapaes.github.io.git</em>
* **clone_name** is the name you give to the directory in which Git will clone the repository, `.` means at the current folder

---
# Configuration & set up
* `git push -u <remote_name> <local_branch_name>`
* This command will map remote repository at <remote_repo_url> to a ref in your local repo under <remote_name>. 
* Once you have mapped the remote repo you can push local branches to it.

---
# git push
* Share our work with masterbranch
* `git push origin your_branch_name` will push your branch up to the remote, origin
* From there the admin can review your branch and merge your work into the masterbranch, making it part of the definitive project version.
* Git informs us that the branch bio-questions was pushed up to the remote. Sally can now review your new work and can merge it into the remote's master branch.


