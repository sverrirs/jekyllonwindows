---
layout: page
title: Install the Jekyll Gem
step: 2
sidebar_title: Jekyll
prev:
    url: 1-ruby-and-devkit.html
    title: Ruby and DevKit
next:
    url: 3-syntax-highlighting.html
    title: Syntax Highlighting
---
## Compatibility
The latest version of Jekyll at the time of writing is v3.3.0, which is compatible with Windows and requires ruby version >= 2.0.0. 
> It is not recommended to install versions prior to v3.x due to incompatibilities and breaking changes that were introduced in v3.x.
If you are upgrading from an older version please consult this <a href="http://jekyllrb.com/docs/upgrading/2-to-3/">migration guide</a> for details.

## Installation
Jekyll itself comes in the form of a Ruby Gem, which is an easy-to-install software package. To install Jekyll and all its default dependencies, launch your favorite command line tool and enter the following command.

```
gem install jekyll bundler
```

Hit enter, watch, enjoy. This might take a while due to the number of dependencies.

Did you get an [SSL_connection error](2x-jekyll-gem-sslerror)?

### If you use a proxy
If behind a proxy, then you need to specify the proxy address in your gem command like so

```
gem install --http-proxy http://PROXY.ADDRESS:PORT jekyll bundler
```

You can specify a username and password as well

```
gem install --http-proxy http://USER:PASSWORD@PROXY.ADDRESS:PORT jekyll bundler
```

You can make these settings permanent by setting your `HTTP_PROXY` [environment variable](2x-jekyll-gem-windows-path) to the same proxy value.

```
SET HTTP_PROXY=http://USER:PASSWORD@PROXY.ADDRESS:PORT
```

## Useful GEMs
There are many enhancements available for jekyll sites. Most of them are distributed in the form of GEMs. Below are a few that are most commonly required when installing custom themes:

```
gem install jekyll-paginate-v2
gem install jekyll-feed
gem install jekyll-gist
```

## Summary
Tada! You have successfully installed Jekyll. In fact, you can already build and serve sites without errors, unless there are blocks of code in there and you want to use syntax highlighting. To find out how to properly set up one of two syntax highlighters, click on the button below.