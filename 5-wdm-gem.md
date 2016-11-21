---
layout: page
title: Let Jekyll --watch
step: 5
sidebar_title: Watch
prev:
    url: 4-markdown.html
    title: Markdown
next:
    url: 6-running-jekyll.html
    title: Running Jekyll
---

Jekyll has a built-in auto-regeneration feature that watches your source folder for changes and then re-builds your site. The `jekyll serve` command has this enabled by default and you can use run `jekyll build --watch` to manually enable it there.

## Install the wdm Gem
On Windows, you need to install one extra tool, or rather Gem, to enable this functionality. Simply run the following command from the command line.

```
gem install wdm
```

## Require wdm in your Gemfile
Alternatively, if you use a Gemfile, you can check if Jekyll runs on Windows and only then install the wdm Gem.

Open the `Gemfile` file that is in the root of your jekyll site. Add the following line at the end of this file. 

```
gem 'wdm', '~> 0.1.0' if Gem.win_platform?
```

## Install working version of listen Gem
Jekyll uses the listen Gem for auto-regeneration. The listen Gem is a dependency of Jekyll. Find the version of the listen Gem installed by the Jekyll Gem.

```
gem list | findstr listen
```

Some versions of listen do not work on Windows. [jekyll/jekyll-help#64](https://github.com/jekyll/jekyll-help/issues/64) has some information on versions that worked on Windows in the past. Please refer to the [Versions table](/#versions) to learn which versions of listen have been tested as part of this guide. To install a specific version of the listen Gem, run this command and specify one of the tested versions.

```
gem install listen -v 3.1.5
```

It is recommended to use listen version 2.7.8 or later.

[Click here if you're running Jekyll 3.3.0](5x-wdm-gem-watchissue).


# Summary
Take a deep breath! You’ve now installed everything you need to run Jekyll on Windows. There are a few minor things you should know to make sure that your sites build smoothly and without problems. Click the button below to proceed.