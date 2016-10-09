---
layout: page
title: Run Jekyll without errors
step: 6
sidebar_title: Run it
prev:
    url: 5-wdm-gem.html
    title: Watch
---

# No BOM allowed
If there are <a href="https://en.wikipedia.org/wiki/Byte_order_mark">BOM (Byte order mark)</a> header characters in your UTF-8-encoded files, Jekyll will break. Make sure there are none. This will require you to open and re-save all of the files that have BOM characters.

# Set your encoding to UTF-8
Depending on the version of Ruby and/or Jekyll you’re using, your site’s content, and maybe other factors, you may need to make sure Jekyll will read your site’s source as UTF-8.

Add the following line to your `_config.yml` file

```
encoding: utf-8
```

# Use subfolders
Jekyll cannot build or serve sites from certain system-reserved folders on Windows, like your user folder. Instead, it will output an error looking like this:

```
C:\Users\You>jekyll serve
Configuration file: C:\Users\You\_config.yml
            Source: C:\Users\You
       Destination: C:\Users\You\_site
      Generating...
jekyll 2.4.0 | Error: Permission denied - .
```

If you encounter such an error, simply move your site to a subdirectory (e.g., `C:\Users\You\awesome-jekyll-site`) and try again.

# The End

```
jekyll build
jekyll build --watch
jekyll build -w
jekyll serve
jekyll serve --watch
jekyll serve -w
```

You can now run all of the above commands on your Windows machine. Congratulations! You have successfully set up Jekyll on Windows.

Found something that wasn’t quite clear? Is something in this guide outdated? Did I forget something? Please look if somebody else noticed it already or file a new issue on GitHub if that’s not the case. Thanks!

If you need help with using Jekyll in general, please visit the official Jekyll website by clicking the button below.