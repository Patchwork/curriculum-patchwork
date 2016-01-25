# Creating New Pages and Posts with Jekyll

OK, so now you know how to edit information in an existing page, but how about creating a new page or blog post? Jekyll makes this very easy as well, and we'll show you how now.

## Front Matter

The hardest part about creating new pages is that you have to create the proper front matter along with the markdown content. Don't worry though, this "hardest part" is actually quite easy once you know what you're doing.

Front matter in Jekyll refers to a little block of code that you put at the beginning of a file in order to tell Jekyll how to handle the content. It defines what the title of the page is, what layout it will use, and more.

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

Here you can see that we use a different layout for our blog posts than we do for our pages. The title is also wrapped in quotes. This is not necessary with most titles, but if you have a colon in your title or other punctuation marks, it can prevent the YAML from being parsed incorrectly.

There are also two new variables. `date:` is the date and time that you published this post at. We use this variable to order the posts on the blog. `categories:` defines the tags that will appear with the blog content. This defines only one category, "jekyll update". If you'd like to define multiple, then you can wrap the whole thing in square brackets and include spaces between the tags.

```markdown
---
categories: [jekyll update, tutorial, example]
---
```

That's about all you need to know about front matter. If you get confused, just refer to the examples that already exist in your repo.

## Creating a New Page

## Creating a New Post