---
layout: page
title: Issue with watch in Jekyll 3.3.0 
prev:
    url: 5-wdm-gem.html
    title: Watch
next:
    url: 5-wdm-gem.html
    title: Watch
---

## Watch does not work in Jekyll 3.3.0
In jekyll v3.3.0 there is currently code blocking the use of the `--watch` feature on Windows.

> This issue has been fixed in v3.3.1 and onward. 
> 
> If possible an upgrade is strongly recommended. 

If you need to run v3.3.0 for some reason then there is a temporary work-around that involves disabling this code in the Jekyll source.  

Open file `%RUBY_INSTALL_DIR%\lib\ruby\gems\2.2.0\gems\jekyll-3.3.0\lib\jekyll\commands\build.rb`. 

Update line 74 to include a `false &&` block like so

```
73: def watch(site, options)
74:  if false && Utils::Platforms.windows?
75:   Jekyll.logger.warn "", "--watch arg is unsupported on Windows."
```
Save and close this file. Now when you use `jekyll serve` it should monitor file changes without problems.