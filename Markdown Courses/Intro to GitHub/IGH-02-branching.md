# Doing Work on GitHub

## Branches

In GitHub, a branch is a working copy of your project. Everything in your project lives on a branch.

By convention, the default branch is a repository is called `master`. Master is typically the deployed, production copy of your code. When you are ready to make changes or add a new feature to your project, you will create a new branch to avoid introducing bugs in your production code. At the end of the GitHub workflow, this branch will be merged back into `master`.

When you create a branch, you are creating a full copy of the parent branch and giving it a new, unique name. From that point on edits made to one branch _will not_ show up on the parent until you merge the branches back together.

### Using Branches Effectively

It is common to have a bunch of different features or ideas in progress at any given time—some of which are ready to go, and others which are not. Branching exists to help you manage this workflow.

![Branches](https://raw.githubusercontent.com/1point618/curriculum-github/master/images/github-branches.png)

Any time you want to start a new chunk of work, you should create a new branch for that work. 

Each branch you create should exist to introduce a single feature or fix a single bug. You want to create short-lived, single-purpose branches that can easily be merged (or reverted) later.

Here is a video walk-through of how to create a branch on GitHub:

<iframe width="560" height="315" src="https://www.youtube.com/embed/xgQmu81G1yY" frameborder="0" allowfullscreen></iframe>


##Commiting

Committing is how you take a snapshot of your project at a specific point in time. Commits are added to the current branch and can include changes to one or more files.

Commits always have a brief message associated with them. The commit message is a description of the changes introduced in this snapshot. Think of it as the story of your project, 50 characters at a time. 

Here's a short video on creating, editing, and commiting files on GitHub:

<iframe width="560" height="315" src="https://www.youtube.com/embed/47M6Is7pIB8" frameborder="0" allowfullscreen></iframe>



## Try it Out

Now it is your turn to walk through the GitHub Workflow. Start by creating a branch and adding a new file to your repository.

We have set up <a href='https://github.com/wheelhouseio/workflow-project' target='_blank'>a project</a> that you can fork and use for the steps below. 

* Navigate to <a href="https://github.com/wheelhouseio/workflow-project" target="_blank">the project</a>.
* Fork the project by clicking on the `Fork` button in the upper-right hand corner.
* Once it's finished, look around. This is the Code Veiw, where all your code in the repo is stored.
* In the upper left, click on the drop down next to `Branch: master`. This is where you can create new branches, or switch to another branch.
* Create a branch called `create-bio`.
* On the `create-bio` branch, create a file called `new-file.md`. Include the following text:
  ```
  This is a new file.
  * It is formatted using markdown.
  * That's why it has the `.md` file extension.
  ```
* Add a commit message and commit the file directly to your branch.