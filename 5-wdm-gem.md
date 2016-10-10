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


## May not work
For jekyll v3.0.x, until v3.3.x there is code blocking the use of the `--watch` feature on Windows. At the time of writing this <a href="https://github.com/jekyll/jekyll/commit/17bd63fa195083992b4493ee521729e84373ad77">issue has been fixed</a> but not yet released.

There is a temporary work-around that involves disabling this code in the Jekyll source.  

Open file `%RUBY_INSTALL_DIR%\lib\ruby\gems\2.2.0\gems\jekyll-3.3.0\lib\jekyll\commands\build.rb`. 

Update line 74 to include a `false &&` block like so

```
73: def watch(site, options)
74:  if false && Utils::Platforms.windows?
75:   Jekyll.logger.warn "", "--watch arg is unsupported on Windows."
```
Save and close this file. Now when you use `jekyll serve` it should monitor file changes without problems.


# Summary
Take a deep breath! You’ve now installed everything you need to run Jekyll on Windows. There are a few minor things you should know to make sure that your sites build smoothly and without problems. Click the button below to proceed.