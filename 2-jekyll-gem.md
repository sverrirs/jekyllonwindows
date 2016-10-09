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

## SSL_connect error
You can encounter an SSL_connect error when issuing `gem install` similar to

```
ERROR: Could not find a valid gem 'jekyll' (>= 0), here is why: 
Unable to download data from https://rubygems.org/ 
- SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed (https://rubygems.org/latest_specs.4.8.gz)
```

To fix this issue download the `GlobalSignRootCA.pem` from <a href="https://raw.githubusercontent.com/rubygems/rubygems/master/lib/rubygems/ssl_certs/index.rubygems.org/GlobalSignRootCA.pem">Github</a> and place it in a folder inside your ruby install folder, e.g. `%RUBY_DIR%\ssl_cert\`

Then execute the following command in your console to test
```
SET SSL_CERT_FILE=%RUBY_DIR%\ssl_cert\GlobalSignRootCA.pem
```
Replacing _%RUBY_DIR%_ with your actual path.

Try issuing the `gem install` command again and if it works you should add a new environment variable `SSL_CERT_FILE` with this same path.

## Adding environment variables in Windows

### Windows 10 and Windows 8
* In Search, search for and then select: System (Control Panel)
* Click the Advanced system settings link.
* Click _Environment Variables_. In the section System Variables, find the SSL_CERT_FILE environment variable and select it. Click Edit. If the SSL_CERT_FILE environment variable does not exist, click New.
* In the Edit System Variable (or New System Variable) window, specify the full path to the GlobalSignRootCA.pem file. Click OK. Close all remaining windows by clicking OK.
* Reopen Command prompt window, and run your gem commands.

### Windows 7
* From the desktop, right click the Computer icon.
* Choose Properties from the context menu.
* Click the Advanced system settings link.
* Click _Environment Variables_. In the section System Variables, find the SSL_CERT_FILE environment variable and select it. Click Edit. If the SSL_CERT_FILE environment variable does not exist, click New.
* In the Edit System Variable (or New System Variable) window, specify the full path to the GlobalSignRootCA.pem file. Click OK. Close all remaining windows by clicking OK.
* Reopen Command prompt window, and run your gem commands.

### Windows Vista
* From the desktop, right click the My Computer icon.
* Choose Properties from the context menu.
* Click the Advanced tab (Advanced system settings link in Vista).
* Click Environment Variables. In the section System Variables, find the SSL_CERT_FILE environment variable and select it. Click Edit. If the SSL_CERT_FILE environment variable does not exist, click New.
* In the Edit System Variable (or New System Variable) window, specify the full path to the GlobalSignRootCA.pem file. Click OK. Close all remaining windows by clicking OK.
* Reopen Command prompt window, and run your gem commands.

### Windows XP
* Select Start, select Control Panel. double click System, and select the Advanced tab.
* Click Environment Variables. In the section System Variables, find the SSL_CERT_FILE environment variable and select it. Click Edit. If the SSL_CERT_FILE environment variable does not exist, click New.
* In the Edit System Variable (or New System Variable) window, specify the full path to the GlobalSignRootCA.pem file. Click OK. Close all remaining windows by clicking OK.
* Reopen Command prompt window, and run your gem commands.

## Still having SSL_connect issues?
I know, it is super frustrating. But try updating the RubyGems software within your Ruby installation. For this you can use the rubygems-update gem, but you need to download it manually.

* Find the version of RubyGems you have by issuing a `gem -v`. You are interested in the major and minor version, which are the first two numbers. 
> For example, if gem -v reports “2.4.5.1” then you care about the leading “2.4”

* Now go to [rubygems.org/gems/rubygems-update/versions](https://rubygems.org/gems/rubygems-update/versions) and look for the rubygems-update that has the first two numbers matching your RubyGem version and the largest third number. For example, my gem -v reported “2.4.2”; the highest number I see for “2.4” is 2.4.8 so that’s the one I want.

* Click the link for the rubygems-update version you want. That will take you to a page discussing that version of RubyGems. On the right side of the page there is sidebar that has a list of links. Click the “Download” link and save the gem file somewhere accessible to your command line.

* Install the gem using `gem install --local ~\where-I-saved-it\rubygems-update-2.4.8.gem`.

* Update RubyGems using the command `update_rubygems`. Then try `gem -v` again to see that the RubyGems version is updated to the version expected.

* Uninstall rubygems-update using the command `gem uninstall rubygems-update -x`

Try installing a gem. If it succeeds, you are done!

> If you are still getting some kind of SSL or certificate error, then you will need to do the steps discussed above and download the latest `GlobalSignRootCA.pem` certificate.

## Other useful GEMs
There are many enhancements available for jekyll sites. Most of them are distributed in the form of GEMs. Below are a few that are most commonly required when installing custom themes:

```
gem install jekyll-paginate
gem install jekyll-feed
gem install jekyll-gist
```

## Summary
Tada! You have successfully installed Jekyll. In fact, you can already build and serve sites without errors, unless there are blocks of code in there and you want to use syntax highlighting. To find out how to properly set up one of two syntax highlighters, click on the button below.