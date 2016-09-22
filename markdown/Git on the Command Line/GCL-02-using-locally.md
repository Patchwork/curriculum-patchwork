# Using Git Locally

## Cloning a Repository
image: clone-diagram.png

Part of what makes git such a well-loved VCS is that it easily lets everyone on the team have their own local working repository. It's expected that everyone will work on their own computer, and sync changes they've made with each other only when they need to.

But first, we have to make a local copy of your repository. To do this, we have to "clone" the repository that you have hosted on GitHub.

When you clone a GitHub repository you are creating a copy of everything in that repository, including its history. This is one of the benefits of a distributed VCS like git—rather than being required to query a slow centralized server to review the commit history, queries are run locally and are lightning fast.

To make this easier, we've set up a repository for you, which you can find by clicking on the "Repository" link at the upper left hand side of this or any page.

https://youtu.be/PADLsDJK7Jk

* Start a new branch on GitHub to work on.
* Copy the clone URL on GitHub.
* Using the command line, `cd` to the directory that you want to put your local repo in.
* Type `git clone <clone_url>`.
* You might be prompted for your password. You should enter your GitHub password at this point.
* `cd` into the new cloned repo and type `git status`.
* `git branch` will show you the available branches. Only `master` appears.
* `git branch -a` will show all the remote branches.
* `git checkout <branchname>` will create a local branch that matches the remote branch. All edits you make locally will be applied to that branch until you checkout another one.

### Try it out: Cloning a Repository 

Let's go ahead and clone this repository to your local desktop.

* Create a new branch on GitHub. Name the branch `githubID-more-bio`, using your GitHub ID.
* Clone the repository to your desktop using the Command Line.


## Editing Local Files
![edit icon](/images/edit-icon.jpg)

Now that you have cloned the repository and checked out your branch, you are ready to make some changes to the local files. If you are familiar with using the command line to open and edit files, then much of this will be familiar to you. The only difference here is that we will be making our changes on a branch. Let's add more information to the bio we created earlier.

https://youtu.be/QYZnKoJ_Hdg

* `git branch` to make sure you're on the right branch.
* `cd` to the proper directory, then open the file with your text editor.
* Make the changes, then save them.

### Try it out: Editing Local Files

* Open your `bio` file in a text editor. If you don't have a `bio` file, then create it.
* Add some information to your bio.
* Save the file.


## The Two Stage Commit

![commit](/images/two-stage-commit-a.png)

After you have finished making your changes, it is time to commit them. When working from the command line, you will need to be familiar with the idea of the two stage commit.

![two-stage commit](/images/two-stage-commit-b.png)

When you work locally, your files exist in one of four states. They are either untracked, modified, staged, or committed.

An untracked file is one that is not currently part of the version controlled directory—such as any new files or files whose names have been changed.

Modified files are any files that you have edited and saved since the last time you committed.

Untracked and modified files exist in your **working directory**.


![two stage commit](two-stage-commit-c.png)

To add these files to version control, you will create a collection of files that represent a discrete unit of work. This way if you want to revert something in the future, it's easier to find and revert only the mistaken changes. 

We build this unit of work in the **staging area**.

To add files to staging, you use the `git add <filename>` command.

Staging is important because it lets you only stage some of your new or modified files. For instance, if you've added a new variable and fixed a typo, you might want to commit those two changes separately. To do this, you stage and commit each one separately.


![two stage commit](two-stage-commit-d.png)

When we are satisfied with the unit of work we have assembled, we will commit everything in the staging area.

To commit files, use the `git commit` command.

Once changes are committed, the changes are added to the history of that branch, so that you can later see those specific changes, and even undo them if need be.


![two stage commit](two-stage-commit-e.png)

To review:

In order to make a file part of the version controlled directory we will first do a `git add` of only those files we want to commit together, and then we will do a `git commit` to add those changes to the Git version control history. Once the changes are commited, you'll always have a record of them in that state, even after you've changed them again in the working directory.

All of this happens locally, on your computer.

Let's do it now.

https://youtu.be/_gDABUBrmBA

* `git status` lets you see which files have been changed since the last commit.
* `git add <filename>` adds that file to the staging area. 
* `git add .` adds all the changed _and untracked_ files to staging.
* `git commit` will submit all those file changes under one unit of work. 
* This also opens your default text editor (as set earlier in this lesson) for you to add a commit message.
* This commit will happen locally, and only on the checked out branch. If you check out another branch, the changes will no longer show in that file.

### Try it out: Commiting your Changes
Let's use the two-stage commit to stage and commit our changes to the `bio` file from the last section.

* Add your file to staging.
* Commit your changes.

## Syncing Local Changes with GitHub
![push](push.png)

Now that you've committed files locally, it's time to make sure that your remote repository also reflects those changes. So we'll `push` the files and version history up to GitHub.

https://youtu.be/C9mU7Vv0HSM

* Check `git status`: the working directory needs to be clean. If it's not, make sure there isn't anything that you meant to commit!
* Do `git push`: assuming you set the default push behavior to simple, this will push your changes to the same branch on the remote system.
* Back in GitHub, you can easily start a new pull request to merge the changes into `master` using the same process you learned earlier.

###Try it out: Sync Local Changes with GitHub
Let's push the changed `bio` file to the remote GitHub repository and create a pull request.

* Use the command line to push your changes to the remote.
* Go to the GitHub repo and create a new pull request.
