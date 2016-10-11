---
layout: page
title: Install a Syntax Highlighter
step: 3
sidebar_title: Syntax
prev:
    url: 2-jekyll-gem.html
    title: Jekyll Gem
next:
    url: 4-markdown.html
    title: Markdown
---
## Overview
Whether you’re using Markdown or HTML, Jekyll makes it easy for you to insert beautiful code blocks into your pages.
 
As of v3.x Jekyll now uses Rouge as the default syntax highlighter. <a href="https://help.github.com/articles/using-syntax-highlighting-on-github-pages/">Github</a> only supports Rouge. 

There is still support for the older Pygments.rb highlighter but its use for new projects is not recommended. More information can be found on the [official Jekyll website](http://jekyllrb.com/docs/templates/#code-snippet-highlighting).

## Install Rouge
Quick and painless: Open your favorite command line tool and enter the following command.
 
```
gem install rouge
```

Then, in your `_config.yml`, set Rouge as your syntax highlighter:

```
highlighter: rouge
```

Done!