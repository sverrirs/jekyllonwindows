---
layout: page
title: Error installing the Ruby DevKit
prev:
  url: 1-ruby-and-devkit.html
  title: Ruby and DevKit
next:
  url: 1-ruby-and-devkit.html
  title: Ruby and DevKit
---

### Error while installing Ruby Devkit
The output should display the path your Ruby install (e.g. ``` - C:\Ruby23-x64```). On 64-bit Windows, you may receive the error message _"Invalid configuration. Please fix 'config.yml'"_ when running the review command. 

> It seems the problem is that that the 64bit version of Ruby 2.0.0 creates a registry entry in a location that the Devkit initilisation script (dk.rb) is not aware of ('Software\Wow6432Node\RubyInstaller\MRI').
> 
> Until the Devkit installer is updated, you can get the installation to work by opening %DevKitExtractionDir%\dk.rb in a text editor and changing the REG_KEYS array to include the 64-bit registry path, so it looks like this:
> 
>```
>REG_KEYS = [
>    'Software\RubyInstaller\MRI',
>    'Software\RubyInstaller\Rubinius',
>    'Software\Wow6432Node\RubyInstaller\MRI'
>]
>```
> From [Dr.Seuss on StackOverflow](http://stackoverflow.com/a/17148987/779521)

Then run both the init and review commands again. 

Alternatively, open `C:\RubyDevKit\config.yml`, enter the path of your Ruby install (preceded by a dash character) on its own line (e.g. ``` - C:\Ruby23-x64```), save the file, and then run the review command again to confirm the text was entered correctly.