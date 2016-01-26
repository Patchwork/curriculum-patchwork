# Templates and Design

In this lesson, we'll teach you how to edit templates in Jekyll so that you can create new page types and change your current design. This lesson assumes knowledge of HTML and CSS. If you'd like to learn, there are a bunch of free resources online. We'd recommend (and will at times link to) the <a href="http://www.w3schools.com/" target="_blank">W3Schools tutorials</a>.

## HTML Templates

Jekyll uses a templating engine called Liquid. Liquid works by creating HTML templates with little snippets of code in them. When displaying, Jekyll will execute the code, then display the results along with the HTML.

For instance, this is the default blog post template included in all new Jekyll installs. It's found in the `_layouts` folder and is called `post.html`.

```html
---
layout: default
---
<div class="post">

  <header class="post-header">
    <h1 class="post-title">{{ page.title }}</h1>
    <p class="post-meta">{{ page.date | date: "%b %-d, %Y" }}{% if page.author %} • {{ page.author }}{% endif %}{% if page.meta %} • {{ page.meta }}{% endif %}</p>
  </header>

  <article class="post-content">
    {{ content }}
  </article>

</div>
```


Let's look at how this works. First, there is front matter just like with our markdown files. This front matter says that this template also uses another template. Templates can be embedded within each other in this way—so you might have one basic template with stuff like a header and footer, then more specific templates that fit inside that one for static pages and blog posts.

Next up comes the HTML. As usual, we have tags with classes. 

Finally, inside the `<h1>` tag, we get our first look at liquid.

All liquid commands are placed inside either a block with two curly brackets `{{ }}` or a block with a curly bracket and a percent symbol `{% %}`. The former are commands that will render text inside the HTML. The latter are just logic commands that won't output any text.

Our first liquid command is `{{ page.title }}`. This command is telling the template to display the text found in the `title:` variable in the page's front matter. You'll see this syntax, `object.variable` using a period a lot in liquid. When you use it, you're telling liquid to look inside the object to find and return that specific variable. 

Next, inside the `<p>` tag, comes some more complicated liquid. It starts off with `{{ page.date | date: "%b %-d, %Y" }}`. Here, we're telling liquid to display the date found in the page, but also how to display it. The pipe `|` character passes the content returned by the command on the left through the process to the right. Here, the 

