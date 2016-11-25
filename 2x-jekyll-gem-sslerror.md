---
layout: page
title: SSL_connect error when installing gems
prev:
    url: 2-jekyll-gem.html
    title: Jekyll Gem
next:
    url: 2-jekyll-gem.html
    title: Jekyll Gem
---

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

Try issuing the `gem install` command again and if it works you should [add a new environment variable](2x-jekyll-gem-windows-path.html) `SSL_CERT_FILE` with this same path.

More information about this issue can be found on [Luis Lavena's Gist](https://gist.github.com/luislavena/f064211759ee0f806c88).



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