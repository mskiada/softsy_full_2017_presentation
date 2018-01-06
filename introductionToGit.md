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
* `echo "a gitignore file">> .gitignore`
* `echo "" > .gitignore`
* `echo null > .gitignore`
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
* In order for Git to start tracking *Example.java*, the file needs to be added to the staging area.
* We can add a file to the staging area with: `git add Example.java`

---
# git diff
Since the file is tracked, we can check the differences between the working directory and the staging area 
<br/>with:`git diff filename`<br>
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

---
# git show head
In Git, the commit you are currently on is known as the HEADcommit. <br/>
To see the HEAD commit, enter: `git show HEAD`<br/>
The output of this command will display everything the git log command displays for the HEAD commit, plus all the file changes that were committed.

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


