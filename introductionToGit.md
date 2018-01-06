# First Steps
1. Download Git:
             https://git-scm.com/downloads
2. Open <em>cmd</em>
3. Verify the installation was successful
	    `git --version`

---
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
*  `rm -rt .git`
*  `rd /s /q .git`

---
# Git status
* In the output, notice the file in red under untracked files. 
* Untracked means that Git sees the file but has not started tracking changes yet.

---
# .gitignore
* `echo "a gitignore file">> .gitignore`
* `echo "" > .gitignore`
* `echo null > .gitignore`

---
# Saving changes to the repository
1. Find direcory `cd /path/to/project `
2. Create new file `echo "" >> Example.java`
3. Add file to staging  `git add Example.java` (or git add –all)
4. Check the current state of the repository `git status`
5. check the differences between the working directory and the staging area `git diff`
6. Save changes in repository `git commit -m "added Example.java to the repo"`

---
# git add
* In order for Git to start tracking <em>Example.java</em>, the file needs to be added to the staging area.
* We can add a file to the staging area with: `git add Example.java`

---
# git diff
* Since the file is tracked, we can check the differences between the working directory and the staging area 
<br/>with:`git diff filename`<br/>
* Here, filename is Example.java so `git diff Example.java`

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

---
# git show head
* In Git, the commit you are currently on is known as the HEADcommit.
* To see the HEAD commit, enter: `git show HEAD`
* The output of this command will display everything the git log command displays for the HEAD commit, plus all the file changes that were committed.

---
# git checkout
* What if you decide to change the ghost's line in the working directory, but then decide you wanted to discard that change?
You could rewrite the line how it was originally, but what if you forgot the exact wording? <br/>
* The command `git checkout HEAD filename` will restore the file in your working directory to look exactly as it did when you last made a commit. (το working directory παίρνει τις τιμές του commit)

---
# git reset (1)
* We can unstage that file from the staging area using `git reset HEAD filename`
* This command resets the file in the staging area to be the same as the HEAD commit. It does not discard file changes from the working directory, it just removes them from the staging area.

---
# git reset (2)
* Just like retracing your steps on that hike, Git enables you to rewind to the part before you made the wrong turn. You can do this with:`git reset commit_SHA`
* This command works by using the first 7 characters of the SHA of a previous commit. For example, if the SHA of the previous commit is 5d692065cf51a2f50ea8e7b19b5a7ae512f633ba, use:
`git reset 5d69206`
* HEAD is now set to that previous commit.

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
* Create a new branch:  `git brach mitsos-branch` 
* Be sure to name your branch something that describes the purpose of the branch. 
* Also, branch names can’t contain whitespaces: mitsos-branch and mitsos_branch valid branch names, but mitsos branch is not.

---
# git checkout
* The master and fencing branches are identical: they share the same exact commit history. 
* You can switch to any existing branch with `git checkout branch_name`
* Once you switch branch, be now able to make commits on the branch that have no impact on master.
* You can continue your workflow, while master stays intact

---
# Branching Overview

---
# git merge
* `git merge branch_name`
* Your goal is to update master with changes you made to fencing.
* Fencing is the giver branch, since it provides the changes. 
* Master is the receiver branch, since it accepts those changes.

---
# merge conflict(1)
* What would happen if you made a commit on master before you merged the two branches? 
* Furthermore, what if the commit you made on master altered the same exact text you worked on in fencing? 
* When you switch back to master and ask Git to merge the two branches, Git doesn't know which changes you want to keep.
* This is called a merge conflict.

---
# delete branch
* Branches are usually a means to an end. 
* We create them to work on a new project feature, but the end goal is to merge that feature into the master branch. 
* After the branch has been integrated into master, it has served its purpose and can be deleted.
* The command `git branch -d branch_name` will delete the specified branch from your Git project.

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
# git fetch
* The original Git project may have changed in some way. 
* If so, your clone will no longer be up-to-date.
* An easy way to see if changes have been made to the remote and bring the changes down to your local copy is with: `git fetch`
* This command will not merge changes from the remote into your local repository. It brings those changes onto what's called a remote branch

---
# merge 
* New commits may have been fetched to your local copy of the Git project, those commits are on the origin/masterbranch.
* Your local master branch has not been updated yet, so you can't view or make changes to any of the work added.
* Integrate origin/master into your local master branch `git merge origin/master`

---
# git push
* Share our work with masterbranch
* `git push origin your_branch_name` will push your branch up to the remote, origin
* From there the admin can review your branch and merge your work into the masterbranch, making it part of the definitive project version.
* Git informs us that the branch bio-questions was pushed up to the remote. Sally can now review your new work and can merge it into the remote's master branch.


