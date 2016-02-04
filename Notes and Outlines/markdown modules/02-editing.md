# Editing Your GitHub Page

We've set you up with a project to get started with. Now let's see how to make some edits to it. If you're not clear on the GitHub workflow, we recommend that you complete the [Wheelhouse GitHub Workflow course](https://learn.wheelhouse.io/events/workflow) first. 

## Profile vs. Project Pages

There are two kinds of GitHub Page projects: profile pages, and project pages. Every personal and organizational GitHub account gets one profile page. Profile pages are displayed from the `master` branch, and so are managed just like any other GitHub project. Your profile page must have the title of `username.github.io`, where `username` is your GitHub username or the name of the organization. To see your profile page, just go to the same URL as the title, so `http://username.github.io`.

While you can only have one profile page, you can have as many project pages as you have projects. To create a project page, create a branch on any project called `gh-pages`. The HTML, CSS, and Jekyll information there will be displayed at `http://username.github.io/project-name`. So if a user named Jamal has a project named "startup-landing-page" with a `gh-pages` branch, he'd be able to get to his site by navigating to `http://jamal.github.io/startup-landing-page` in his browser.

## GitHub Pages and the GitHub Workflow

Whether on a profile or project page, it's best to create a branch before you do any editing of your page. You should name the branch something related to the work that you're doing. For instance, you might want to call a branch `adding-personal-info` or `new-blog-post`. Make sure to make any edits and commits to that branch, not to `master` or `gh-pages`. 

Then once you're ready, you'd create a Pull Request comparing your branch to `master` or `gh-pages`, and merge the branch once you're sure everything is working.

![GitHub Workflow](https://github.com/wheelhouse/curriculum-patchwork/github-flow.png)

Note that you won't be able to test your page online from your branch—you won't see it until you merge the branch. So, once it's up you may need to create a bugfix branch to touch up any rough spots. If you'd like to see your site before it goes live, you'll have to do that using Jekyll locally. We'll cover how to do that in the optional fourth section of this course as it's a little complex to get set up.

## Editing Content

### Markdown
Editing the content of your site is as easy as writing plain text with a couple of added elements. These elements are called "markdown", and are used by Jekyll to format the text. 

For instance, if you wrap some text in double-asterisks, `**like so**`, you'll see bold text, **like so**. A single underscore before and after some text will _italicize_ it, `_like this_`.

Adding between one and six hash signs on a new line will make the text after it become a header.

```markdown
# Title
## Header
### Sub-Header
```

You can even add links and images using markdown using the following syntax:

```markdown
[This is the text you will see.](http://link.url)

![This is the image alt text.](http://link.url/image.jpg)
```

That's really all you need to know about markdown to get started. In the "Issues" tab at the top of your repo, you'll find a comment that explains markdown in some detail—feel free to check it out.

### Front Matter

You'll notice that all of the markdown files have some code at the beginning. This code is contained within dashes, and looks something like this:

```yaml
---
title: Hello
author: Jamal Phillips
layout: blog
---
```

This is called "front matter". It defines variables for Jekyll to use on that particular page. The word before the colon is the variable name, and text after it is the variable's value. We'll go more in depth on this later, but for right now just know that if you'd like to change the variable for a page (for instance, if you want to set your name to the author of a post), all you have to do is change the text after the colon.

## The Structure of a Jekyll Project
Let's take a look at the directory we created for you by clicking on the "Repository" button on the top-left of this page.

You'll be presented with the GitHub repository we created for you. We've already set up a template site, let's take a look at it.

In the top level directory are several folders and files. 

The `index.html` file is the home page of your site. It contains the layout that people will see when they navigate to the site.

The `_index` folder contains markdown files with the content for your index page. There are several pages in here that define your profile image, your header, and the body of the site.

The `_layouts` folder contains the layouts for the other static pages of your website. The `_pages` folder contains the content for the static pages, and the `_posts` folder contains the content for the blog posts. Every time you add a new markdown file to `_pages` or `_posts`, you'll create a new page or blog post which uses the layout that you tell it to in the frontmatter of the markdown file.

The `_includes` folder contains layout elements that will show up on every part of your web site, such as the header and footer, regardless of which layout is used.

The `css` and `_sass` folders contain the CSS design information for your site. 

The `_config.yml` file contains configuration information about the project that Jekyll will use when running the project.

The `.gitignore` file is used by git to prevent the saving of unneccessary files that Jekyll produces automatically. Finally, the `feed.xml` file allows someone subscribe to your site using an RSS reader.


## Tying It All Together

On the next page, we'll be walking you through the steps of editing the front page of your project to make it about you. You'll be editing the markdown files in the `_index` folder. 

Don't worry if you don't want to put your actual information up online. It's OK to just make stuff up. But if you do want to create an actual portfolio, we'd recommend doing that here!

- [ ] Create a branch, `profile-info`.
- [ ] Edit `index_name.md`, commit.
-     Edit `index_content.md`, commit.
-     Edit `index_img.md`, commit. You must use an image already online. You can upload and image of yourself to imgur.com if you dont' have one. Or right-click on your GitHub profile image, select "copy image URL", and use that.
- [ ] Create a PR comparing `gh-pages` to `profile-info`.
- [ ] Merge that PR.
-     Look at your creation at `http://username.github.io/profile`.