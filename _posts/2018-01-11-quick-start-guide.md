---
layout: post
title:  "Quick Start Guide"
author: sal
categories: [ Jekyll, tutorial ]
image: assets/images/12.jpg
featured: true
hidden: true
---

If you already have a full Ruby development environment with all headers and RubyGems installed (see Jekyll’s requirements), you can create a new Jekyll site by doing the following:


<p><iframe style="width:100%;" height="315" src="https://www.youtube.com/embed/W9dP6tEfiNY?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe></p>

If this project help you reduce time to develop, you can give me a cup of coffee :)

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=JXNKK6FFUSHBQ)


```ruby
# Install Jekyll and Bundler gems through RubyGems
gem install jekyll bundler

# Create a new Jekyll site at ./myblog
jekyll new myblog

# Change into your new directory
cd myblog

# Build the site on the preview server
bundle exec jekyll serve

# Now browse to http://localhost:4000
```