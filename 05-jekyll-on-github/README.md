# Jekyll on GitHUb

So you have created a beautiful website on Jekyll andd you want to host your site on your gh-pages branch in your github repository. You do a `git push` and go to your site at githubusername.github.io/githubrepo and you discover something is very wrong with your site. This is where we have to use our config file again. Going to to your config file you will see:

    baseurl: "" # the subpath of your site, e.g. /blog/
    url: "http://yourdomain.com" # the base hostname & protocol for your site
    
These two values are referenced at different points in your site code. For example line 9 of the head.html file reads:

    <link rel="stylesheet" href="{{ "/css/main.css" | prepend: site.baseurl }}">

Where it is written `site.baseurl` the file is using the data in our config file. The url will need to be changed to the url of your site on github which follows the format githubusername.hithub.io