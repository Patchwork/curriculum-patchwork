# Setting up Git
In this section you will learn how to configure Git on your local machine for the best experience.

##Using the Command Line

If you've done either of the other two Patchwork courses, then so far all the work we've done has been using GitHub's web interface. However, if you're comfortable on the command line you can easily integrate GitHub into your current workflow.

In this section, we'll teach you how to use Git and GitHub effectively through the command line. We assume a working knowledge of the command line interface, so if you're rusty you might want to brush up on using the CLI before forging ahead.

To get to the command line, you should do the following:

+ **Mac**: Type `command-space` to bring up Spotlight search, then search for `Terminal`.
+ **Linux**: Open up your prefered shell, such as bash or fish.
+ **Windows**: We recommend that you download <a href="https://msysgit.github.io/" target="_blank">Git for Windows from GitHub</a>, as it includes a bash emulator. Without it, the Windows CLI will look a lot different from the Mac / Linux CLI.

If you've never used the command line before, you might want to <a href="http://lifehacker.com/5633909/who-needs-a-mouse-learn-to-use-the-command-line-for-almost-anything" target="_blank">learn more about it here</a>.


## Git vs. GitHub
![Git vs. GitHub](/images/git-v-github.png)

When using the command line, you'll be working with Git. Git is the underlying version control system that GitHub makes use of. Some of the features we've discussed so far, such as pull request and issues, are functionality that GitHub adds. Others, like branching and commits, are Git functionality.

You can think of Git as a version control tool that you can use locally, and GitHub as a remote service that makes using that tool with other people on your team much more functional and seamless.


## Checking Git Version

Git is OS agnostic; the commands are essentially the same whether you are on Mac, Windows or Linux. You can use your favorite application to interact with the command line.

First, let's check the version of Git currently installed on your system by typing `git --version` into the command line. You should have the latest version of Git installed.

Find out what the most recent version of git is at <a href="http://git-scm.com" target="_blank">git-scm.com</a>.

If you don't have the right version, or if you get an error saying Git isn't installed, then you need to install Git. If you're on Linuc or Mac, go to <a href="http://git-scm.com" target="_blank">git-scm.com</a> to download and install the latest version. If you're on Windows, then it's easier if you install the [GitHub Desktop client](https://desktop.github.com/), as it comes with Git and other utilities to make using the command line on Windows easier.

Once you've verified you have the latest version of Git installed, you're ready to move on to getting Git configured correctly.



# Configuring Git

## Git Configuration Levels
![config levels](config-levels.png)

The first thing you should do when you get started using Git is to set your configuration options.

Git allows you to set configuration options at three different levels. The default value for Git config is `--local`.

+ `--system` - These are system-wide configurations. They apply to all users on this computer.
+ `--global` - These are the user level configurations. They only apply to your user account.
+ `--local` - These are the repository level configurations. They only apply to the specific repository where they are set.

## Previewing Configuration Settings
![config list](config-list.jpg)

If you would like to see which config settings have already been added, you can type `git config --list`. This will automatically read from each of the storage containers for config settings and list them.

## Configuring User Name and Email
![config username email](config-username-email.jpg)

Go ahead and follow along as we set up our basic configurations. Git uses the config settings for your user name and email address to generate a unique fingerprint for each of the commits you create, so let's set our user name and email address first.

Type `git config --global user.name "<your_full_name>"` and type `git config --global user.email "<your_email>"`.

Make sure to use the same email address that's associated with your GitHub account.

## Configuring Default Editor
![config editor](config-editor.jpg)

Next, we will add a default text editor. This is the text editor Git will use when you need to edit things like commit messages or handle merge conflicts.

Typing `git config --global core.editor "atom --wait"` will tell Git to use the open source atom text editor.

If you don't have atom and would like to use it, you can find it at <a href="https://atom.io/" target="_blank">atom.io</a>. If you would like to use a different editor you can look for instructions <a href="https://help.github.com/articles/associating-text-editors-with-git/" target="_blank">here</a>.

## Configuring Autocrlf to Handle Whitespace
![config-autocrlf](config-autocrlf.jpg)

Different systems handle line endings and line breaks differently. If you open a file created on another system and do not have `autocrlf` set, Git will think you made changes to the file based on the way your system handles this type of file.

Type `git config --global core.autocrlf`.

* If you are on a **Windows** machine, you will want to set this option to `true`.
* If you are on a **Mac** or **Linux** machine, you will set it to `input`.

And for those wondering, `autocrlf` stands for "auto carriage return line feed".

## Configuring Default Push Behavior
![config-push-default](config-push-default.jpg)

One final configuration option we will want to set is our default value for push.

When you push changes from your local computer to the remote you can choose whether you want Git to automatically push all of the local branches to their matching branches on the remote or whether you only want the currently checked out branch to be pushed.

The config setting we use to set this option is `push.default`. We can set the default to `matching` if we want to push all branches automatically. OR, we can set it to `simple` if we only want to push the branch we are on.

For now, let's use `git config --global push.default simple`. This way you don't make accidental pushes while you're still learning to use Git.

## Viewing Configuration Settings
![config-list](/images/config-list.jpg)

Now that we have made some changes to your configuration options, let's take another look at `git config --list`. You may notice duplicate settings if the same variable is set in multiple levels (such as `--global` and `--local`). The lowest value on the list takes precedence."