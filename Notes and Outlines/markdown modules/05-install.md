# Installing Jekyll Locally

This lesson will assume you know how to use Git locally on the command line. If you don't know how to do this, we'd recommend going through our Introduction to Git tutorial first.


## Jekyll on Your Computer

There are many benefits to installing Jekyll on your computer and working on your projects locally. You can more quickly test what your changes look like on the web without having to merge your branch to do so. You can start new projects from scratch instead of having to use our template. You'll be able to configure Jekyll to work for a wider variety of project types. And you can use your favorite text editor to make the process of writing your content that much faster and more pleasant.

However, Jekyll can be difficult to set up. And it isn't supported on Windows, only on Mac and Linux. We're assuming you have a Mac computer for this tutorial: if you're using Windows, you may be able to get Jeckyll to work. Here are some [instructions](http://jekyllrb.com/docs/windows/). 

Getting Jekyll set up locally and using GitHub pages will require several steps. Unfortunately, some of the most boring and finicky steps must come first, but you'll only need to perform them once to get started.

1. Install Git
2. Install Jekyll
3. Instantialize a new local Git repository
4. Connect your local repo to a remote repo on GitHub
5. Set up a new Jekyll project in that repository
6. Configure the Jekyll project based on the type of project you're building
7. Set up the templates and CSS for the project
8. Add the content

You've learned to do (7) and (8) already in this course, and (1), (3), and (4) in the Intro to Git course, so we'll be focusing on installing Jekyll, generating a new Jekyll project, and configuring that project.


## Installing Jekyll

To install Jekyll, you'll need Ruby installed as well. This comes by default on many but not all Mac computers. To check to see if you have ruby, open Terminal and type `ruby -v`. As long as you have version 2.0 or higher, you should be good to go. If your ruby version is lower than that, or you get an error, follow along below. If you have the right version of Ruby, go ahead and skip down to **Ruby Is Installed**.

### If you don't have ruby?

First, you'll need to install XCode. Check to see if you have them by typing 

```bash
$ gcc -v
```

You'll either get a version number, or a prompt to install xcode. Either say yes, or if you don't get the prompt type in 

```
$ xcode-select --install
```

XCode can take a while to install, and requires internet access.

Once that's finished installing, type

```bash
$ sudo gem install ruby
```

to update Ruby to the latest version.