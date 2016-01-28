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

### Content in Liquid

Our first liquid command is `{{ page.title }}`. This command is telling the template to display the text found in the `title:` variable in the page's front matter. You'll see this syntax, `object.variable` using a period a lot in liquid. When you use it, you're telling liquid to look inside the object to find and return that specific variable. 

Next, inside the `<p>` tag, comes some more complicated liquid. It starts off with `{{ page.date | date: "%b %-d, %Y" }}`. Here, we're telling liquid to display the date found in the page, but also how to display it. The pipe `|` character passes the content returned by the command on the left through the process to the right. The `date:` command accepts a date from liquid, and then formats it in a specific way. Here we started with the abreviated month name `%b`, a space, then the day of the month without a leading zero `%-d`, then a comma and space, then the 4-digit year `%Y`. So `Jan 5, 2016` would be the output for the post from the last lesson.

### Logic in Liquid

After that, we have our first logic command, found inside a curly bracket with percent symbol. This is an `if` command. It tells liquid to only display the contents between the `if` and `endif` commands if the condition in the `if` command is true. Here, `if page.author` will only be true if the post has an `author:` variable defined in the front matter. For instance, if the post had Jamal listed as an author, liquid would display ` • Jamal`, while if it didn't have an author listed, liquid would not display the name or the bullet point. The same is true for the `page.meta` variable.

Finally, liquid will display the content of the post using a special keyword, `content`. Unlike with our other variables, in templates we don't need to specificy the object we're calling the content from.

There is one more logical operator you should know about. The `for` command allows you to cycle through multiple objects. For example, let's look at the following code excerpted from our blog page found in `/_pages/03_blog.md`

```html

  <ul class="post-list">
    {% for post in site.posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>

        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
      </li>
    {% endfor %}
  </ul>

```

Here, the `for` command takes every file in the `_posts` folder (called with `site.post`), creates a temporary object called `post` for that file, and then populates the content below for each of those files. 

You can combine for and if statements, for instance, consider the following hypothetical code from a template:

```html

<ul class="author-list">
  {% for post in site.posts %}
    {% if post.title %}
      <li>{{ post.author }}</li>
    {% endif %}
  {% endfor %}
</ul>

```

This will list the author of every post that has a title. If a post doesn't have a title, the author will not be shown. While this example might be impractical, you'll find uses for using `for` and `if` together the further into templates you delve.


## CSS Templates

Jekyll uses a CSS preprocessor called SASS to generate CSS files. SASS is a lot like Liquid, but for CSS instead of HTML. 

The biggest thing that SASS lets you do is break up your CSS files into little pieces and then include them in one final large file. However, it also has some other handy features including Nesting and Variables.

You can find out about all of SASS's features at <a href="http://sass-lang.com/guide" target="_blank">the SASS website</a>, but we'll explain a few below as well.

### Including files

One way to make writing CSS easier is to separate your functions. One file might be for text, 