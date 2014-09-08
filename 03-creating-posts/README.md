# Creating Blog Posts

Go to your site and open the `_posts` directory. Open the file `2014-03-21-welcome-to-jekyll.markdown`. The first 6 lines should read:

    ---
    layout: post
    title:  "Welcome to Jekyll!"
    date:   2014-08-21 11:03:14
    categories: jekyll update
    ---
    
This is how Jekyll uses layouts to structure your website. Where the value of layout is post, the file uses the file `post.html` from the `_layouts` folder. `post.html` looks like this:

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

You'll recognise some the the html tags and you'll also see that the post layout uses another layout called default. We will look at this more later. Also included in this layout are liquid html tags. For example on line 7, there is the tag `{{ page.title }}` which will use the value of title from your post markdown file. Very importantly there is the liquid tag `{{ content }}` which is where your content from your post file will be placed. 

By creating a new markdown file in the `_posts` directory you can create a new post that will appear on the index page and on another page dedicated to the post. Try now, create a new file in the format of `yyyy-mm-dd-my-first-blog-post.markdown` and in that file put in the first 6 lines:

    ---
    layout: post
    title:  "My First Blog Post!"
    date:   yyyy-mm-dd hh:mm:ss
    categories: General
    ---
    
Feel free to write something on the 7th line, save and preview your site. 