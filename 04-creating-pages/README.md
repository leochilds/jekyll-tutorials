# Creating Pages

For creating a page you can have a look at `about.md` in the main jekyll directory. The first 5 lines read:

    ---
    layout: page
    title: About
    permalink: /about/
    ---

Where the value of layout is page, the file will take on the page format which has been set out in `_layouts`. The `page.html` file looks like this:

    ---
    layout: default
    ---
    <div class="post">
    
      <header class="post-header">
        <h1 class="post-title">{{ page.title }}</h1>
      </header>
    
      <article class="post-content">
        {{ content }}
      </article>
    
    </div>

Again the layout used for this layout is default. You can create a new page by creating a new markdown file using the page layout. If we look at the default layout we see:

    <!DOCTYPE html>
    <html>
    
      {% include head.html %}
    
      <body>
    
        {% include header.html %}

        <div class="page-content">
          <div class="wrapper">
            {{ content }}
          </div>
        </div>
    
        {% include footer.html %}
    
      </body>

    </html>

This should be very familiar now. The default layout has the important tages from creating a html document. The doctype decaration, the html tag and the body tag are all here and therefore don't need to be put anywhere else. In this file there are some other useful liquid tages called includes. These tage partial file from the includes directory. For example `{% include head.html %}` will find the file `head.html` from the `_layouts` folder and will use its content on any page that uses the default layout.

In this way, if you create a new page file, you can just write the content of the page, then jekyll will add the doctype declaration, html tages, head, body tags, header and footer around your content. This gives your site a consistent look. It also means if you want to edit parts of your site that appear on all pages, you only have to do it once. This makes a Jekyll blog site highly customizable. 
