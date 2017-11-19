---
layout: post
title:  "Welcome Jekyll; goodbye, Blogspot!"
date:   2017-11-18 17:46:13 +0100
categories: jekyll update
---
While hosting my blog at inreoh.blogspot.de served me quite well for a couple of years,
I recently began to get annoyed by the limitations of this approach, namely:
 - having to use an inferior editor (the web-based one) as opposed to vim


Getting started is quite easy:

{% highlight ruby %}
 gem install jekyll bundler
 jekyll new my-awesome-site
 cd my-awesome-site
 bundle exec jekyll serve
#=> starts a new Jekyll project, and serves it at localhost:4000
{% endhighlight %}

To convert an existing Blogger blog:
{% highlight ruby %}
 gem install jekyll-import

 export your blog as blog-MM-DD-YYYY.xml

cat > import.rb
require "jekyll-import";
        JekyllImport::Importers::Blogger.run({
          "source"                => "/path/to/blog-MM-DD-YYYY.xml",
          "no-blogger-info"       => false, # not to leave blogger-URL info (id and old URL) in the front matter
          "replace-internal-link" => false, # replace internal links using the post_url liquid tag.
        })

 ruby -rubygems import.rb
#=> imports your blog posts by adding a file in \_static/ for each of them
{% endhighlight %}


