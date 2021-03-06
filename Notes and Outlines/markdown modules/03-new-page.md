# Creating New Pages and Posts with Jekyll

Now that you've learned how to edit content, let's go through how to add your own pages and blog posts.

Jekyll makes this easy. All you have to do is add a markdown file with proper front matter to the right folder. In this lesson, we're going to teach you how to format your page and post files so that you can blog on your new site, and add any permanent pages that you want. When you're finished, you'll be able to customize and add any information you want to your new website.

## Front Matter

The hardest part about creating new pages is that you have to create the proper front matter along with the markdown content. The good news is that this "hardest part" is really easy!

Let's take a look at the front matter on our "about" page.

```markdown
---
layout: page
title: About
permalink: /about/
---

This is the base Jekyll theme. You can find out more info about customizing your Jekyll theme, as well as basic Jekyll usage documentation at [jekyllrb.com](http://jekyllrb.com/)

You can find the source code for the Jekyll new theme at: [github.com/jglovier/jekyll-new](https://github.com/jglovier/jekyll-new)

You can find the source code for Jekyll at [github.com/jekyll/jekyll](https://github.com/jekyll/jekyll)
```

First, you'll notice that the front matter is wrapped in two lines containing three dashes each. This is mandatory! It tells Jekyll what is front matter and what is markdown.

Inside you see three defined terms. Jekyll's front matter uses a syntax called YAML (pronounced to rhyme with camel) to define its terms. Each new line of YAML starts with a single word followed by a colon. This is the "variable", and is the term you're defining. Following that is the text that the variable will refer to for this file.

Our file has 3 variables defined. `layout:` tells Jekyll which layout file to use for this page. We're using the "page" layout, as opposed to the blog post layout. As long as you have a file in your `_layouts` folder with the same filename as your variable definition, you're good to go here.

`title:` defines the name of this page. This is what will show up in the menu and in certain places in the "page" layout.

`permalink:` tells Jekyll where to serve this page from. So in this case, you can get to this page by going to `http://username.github.io/profile/about/`.

Let's look at the front matter for a blog post.

```markdown
---
layout: post
title:  "Welcome to Jekyll!"
date:   2016-01-07 11:35:18
categories: jekyll update
---
```

Here you can see that we use a different layout for our blog posts than we do for our pages. The title is also wrapped in quotes. This is not necessary with most titles, but if you have a colon in your title or other punctuation marks, it prevents those marks from breaking the YAML parser.

There are also two new variables. `date:` is the date and time that you published this post at. We use this variable to order the posts on the blog. `categories:` defines the tags that will appear with the blog content. You can either include a space between each category, or create a list of categories using square brackets and commas.

```markdown
---
categories: [jekyll, update, tutorial, example]
---
```

That's about all you need to know about front matter. If you get confused, just refer to the examples that already exist in your repo.

## Creating a New Page

To create a new page, you'll use the "new file" functionality in GitHub to create a new file inside the `_pages` folder. The name of the file should be your page title + the `.md` extension. Make sure there are no spaces or special characters besides dashes in the title. 

Now add your front matter. Two lines with nothing but three dashes on each line, and then define your `layout:`, `title:`, and `permalink:` variables.

After that, it's as easy as adding new markdown to the file below. For instance, if you wanted to add a page with your work history, you might include the following in a file called `work-history.md`.

```markdown
---
layout: page
title: Work History
permalink: /work-history/
---

## Web Developer
### Acme Inc.
#### March 2001 — January, 2005

_Created websites for clients._

* Developed on average 1 new website per month.
* Responsible for accounts totaling $3,000,000 in value.
* Managed part-time visual and UX designers.


## Job Title
### Company
#### Date Started - Date Ended

_Description of the job and duties._

* Accomplishment 1
* Accomplishment 2
* Accomplishment 3
```

The post should look something like this:

![New Page Screenshot](page-screenshot.jpg)

## Creating a New Post

Creating a new blog post is in many ways like creating a new page, but Jekyll needs a different set of information about the post, and it needs to be named in a special way.

Create a new file in the `_posts` folder. The filename should start with the date, followed by a title separated by dashes. The date should be formatted `YYYY-MM-DD`. So a post about tacos published on January 5th, 2016 would be titled `2016-01-05-why-i-love-tacos.md`. 

Then you need to write the front matter and text of the post. Remember, the `title:` tag will show up on the page, so you don't need to include it in the markdown.

```markdown
---
layout: post
title:  Why I love tacos
date:   2016-01-05 10:30:00
categories: [tacos, food, explainer]
---

Tacos are my favorite food. Why? Because they are the most delicious. Little bite-sized snacks full of meat, veggies, and sauce wrapped up in little corn tortillas.

Tacos are incredibly versatile. You can put meat in them. You can make them vegetarian. You can use soft or hard shells. One taco may be bite-sized or large enough to provide an entire meal. 

![Taco Inspiration](https://upload.wikimedia.org/wikipedia/commons/thumb/7/73/001_Tacos_de_carnitas%2C_carne_asada_y_al_pastor.jpg)

The next time you're not sure what to eat, try going to the best local Mexican restaurant and ordering the chef's choice of tacos. They're sure to be extra-yummy!
```

This will display something like this:

![Blog Post Screenshot](blog-post-screenshot.jpg)

## Your Turn!

-     Create a new branch, `new-page`.
-     Create a new file for your job history page.
-     Add your job history, commit. If you don't want to add anything, copy/paste from the prevous lesson.
-     PR.
-     Merge.
-     Create a new file in the posts.
-     Write a blog post.
-     Commit it to a new branch, `new-post`.
-     PR, merge.
- Go to your website and look at the changes you've made.
