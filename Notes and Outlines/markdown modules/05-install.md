# Installing Jekyll Locally

This lesson will assume you know how to use Git locally on the command line. If you don't know how to do this, we'd recommend going through our Introduction to Git tutorial first.


## Jekyll on Your Computer

There are many benefits to installing Jekyll on your computer and working on your projects locally. You can more quickly test what your changes look like on the web without having to merge your branch to do so. You can start new projects from scratch instead of having to use our template. You'll be able to configure Jekyll to work for a wider variety of project types. And you can use your favorite text editor to make the process of writing your content that much faster and more pleasant.

However, Jekyll can be difficult to set up. Getting Jekyll set up locally and using GitHub pages will require several steps. Unfortunately, some of the most boring and finicky steps must come first, but you'll only need to perform them once to get started.

1. Install Ruby
2. Install Jekyll
3. Install Git
4. Instantialize a new local Git repository
5. Connect your local repo to a remote repo on GitHub
6. Use Jekyll to create a new project in that repository
7. Configure the Jekyll project based on the type of project you're building
8. Set up the templates and CSS for the project
9. Add the content
10. Push the changes to the `gh-pages` branch on GitHub

You've learned to do (8), and (9) already in this course, and (3), (4), (5), and (10) in the Intro to Git course, so we'll be focusing on installing Jekyll, generating a new Jekyll project, and configuring that project.

In this lesson, instead of giving you step-by-step instructions, we're going to link you to outside tutorials that cover the different parts. It's important to learn how to read these tutorials, as reading and writing tutorials is an important way to learn about Open Source projects. 

Remember that you can always ask a mentor for help if you need it!

## Installing Jekyll

Jekyll requires that you have ruby (a programming language and environment) installed before it will work. Jekyll is designed to be run on Mac and Linux computers. It isn't officially supported on Windows. 

If you're using a Mac, <a href="http://digitalshore.io/how-to-install-jekyll-mac-osx-yosemite/" target="_blank">this tutorial</a> will walk you through the steps of installing Ruby and Jekyll. You have to install Xcode, Apple's own developer environment.

If you're using Windows, you still may be able to get Jeckyll to work. <a href="http://jekyll-windows.juthilo.com/" target="_blank">This tutorial</a> offers a really comprehensive list of steps to take, and ways to troubleshoot any issues you come across. 

If you're using Linux, you can install Ruby and Jekyll using whichever package manager you use. 


### Your Project

At this point, you could clone your current GitHub Page and run and edit it locally. Just `git clone` the repository, `pull` the `gh-pages` branch, navigate to the folder in your command line interface, and then run `jekyll serve --config _config.yml,_config_local.yml`. Then you can see your site at `http://localhost:4000` in your browser, and any edits you make will show up there. This is a great way to quickly test out changes to your site. Once you like it, `git commit` the changes and then `push` them up to your remote `gh-pages` branch.


## Generating a New Jekyll Project

Now that you have Jekyll installed, it's going to do a lot of the heavy lifting for you setting up your project. 

Using the command line, navigate to the folder that you want your Jekyll project to live in. So if you have a `/projects` folder, where each folder inside of that is its own project, you'd navigate to `/projects`.

Here, type `jekyll new project-name`, where `project-name` will be the name of your github repo. This will cause Jekyll to create a new folder with the contents of the Jeykll project—default template, CSS, and config, and content files. 

### Connecting with GitHub Pages

Now, navigate into the folder (`cd project-name`) and type `git init`. This sets up the folder so that it is being watched by git locally. Commit the project to the `gh-pages` branch by typing:

    $ git checkout -b gh-pages

    $ git add .

    $ git commit -m "First commit: Jekyll Project created."

Now you need to push the changes up to GitHub. On GitHub, create a new repo with the same name as your project folder. **Do not tell GitHub to automatically create a Readme file.** Once you've done that, copy the HTTPS url under the "Quick setup" section.

Now on the command line, type

    $ git remote add origin <<URL>>

    $ git push --set-upstream origin gh-pages

This connects your repo to your GitHub account, creates a `gh-pages` branch on GitHub, and pushes the Jekyll project to that branch.

From now on, just typing `git push` from this branch will push all of your local commits.


## Setting Up Your Jekyll Project

A good complete step-by-step tutorial for setting up your Jekyll project can be found at <a href="https://www.taniarascia.com/make-a-static-website-with-jekyll/" target="_blank">Tania Rascia's site</a>. We'll hit the highlights below, but her post is one of the best, most thorough places for a beginner to learn about the inner workings of Jekyll and how to create your own themes.

First, you need to get your `_config.yml` file working both locally and on GitHub. 

The best way to do this is to create two config files: `_config.yml` and `_config_local.yml`. GitHub Pages will automatically call `_config.yml`, and when you want to run your page locally, instead of calling `jekyll serve`, you'll type the following into your CLI:

    $ jekyll serve --config _config.yml,_config_local.yml

You should remove the content from the `_config.yml` file that Jekyll automatically creates, and add this instead:

    # Site settings
    title: "The title of your website."
    email: "Your contact email"
    description: "The description of your website."
    baseurl: "/your-repo-name"
    url: "http://githubusername.github.io"
    twitter_username: "TwitterHandle"
    github_username:  "GitHubUsername"
    permalink: /blog/:year/:title/


    # Build settings
    sass:
      sass_dir: _sass
    include: ['_pages']
    kramdown:
      input: GFM

    collections:
        + index

The `_config_local.yml` file should be the same except for the `baseurl:` and `url:` variables. Those should be blank and `http://localhost:4000`, respectively. Now when you're using `jekyll serve` to look at your site locally, you can just go to `localhost:4000` in your browser to see it.

Next, you'll want to create a `_pages` folder. Add all of the static pages to this folder (except the `index.html` file). Then create an `_index` folder—this is where you'll put the files with content for your `index.html` page.

Next, you need to set up your `index.html` page. How you do this is going to depend on how you want to structure the data and content in your `_index` files. Just remember the skills we taught you in the templating lesson, and you'll do fine. You can look at the `index.html` file that we provided in your profile project to get a sense of what can be done.

Finally, it's up to you to add content to your site and update the designs. To update the design, you can check out the themes at <a href="http://jekyllthemes.org/" target="_blank">jekyllthemes.org</a> or <a href="http://jekyllthemes.io" target="_blank">jekyllthemes.io</a>, and more free themes are just a Google search away. Beware, these might over-write the changes you made earlier, so you'd do best to install the theme first then see how that theme handles pages and the index file. 