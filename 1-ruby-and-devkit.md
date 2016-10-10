---
layout: page
title: Install Ruby and the Ruby DevKit
step: 1
sidebar_title: Ruby
next:
    url: 2-jekyll-gem.html
    title: Jenkyl Gem
---

Ruby is the programming language that Jekyll is written in. You’ll need to install Ruby and the corresponding DevKit, which is needed to build some of Jekyll’s dependencies as “native extensions”.

## Install Ruby
As of writing the recommended version of Ruby is v2.2.5. Click on the button below and download the installer for that version that matches your system’s architecture (x86/x64).

<div class="pagination">
    <a class="pagination-item full" href="http://rubyinstaller.org/downloads/">Download Ruby for Windows</a>
    <span></span>
</div>

> Jekyll v3.x requires Ruby version >= 2.0.0.

Execute the installer and go through the steps of the installation. When you get to the screen below, make sure to check the “Add Ruby executables to your PATH” box.

<img src="img/1_rubyinstaller.png">

Click Install and Ruby will be installed within seconds.

## Install the Ruby DevKit
Jekyll has some dependencies which, out of the box, only provide raw source code. To make them into fully functional executables, you’ll probably need to install the Development Kit.

Click the button below and download the DevKit archive that corresponds to your Ruby installation and system architecture. Choose the file marked as _For use with Ruby 2.0 and above_. 

Select either the 32bits or 64bits version depending on your system.

<div class="pagination">
    <a class="pagination-item full" href="http://rubyinstaller.org/downloads/">Download the Ruby Devkit</a>
    <span></span>
</div>

The download is a self-extracting archive. When you execute the file, it’ll ask you for a destination for the files. Enter a path that has no spaces in it. We recommend something simple, like `C:\RubyDevKit\`. Click Extract and wait until the process is finished.

Next, you need to initialize the DevKit and bind it to your Ruby installation. Open your favorite command line tool and navigate to the folder you extracted the DevKit into.

```
cd C:\RubyDevKit
```

Auto-detect Ruby installations and add them to a configuration file for the next step.

```
ruby dk.rb init
```

Now ensure the init command completed successfully.

```
ruby dk.rb review
```

### In case of an error
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


Continue on and complete installing the DevKit, binding it to your Ruby installation.

```
ruby dk.rb install
```



## Summary
That’s it! If all went well, you now have a working Ruby installation on your machine and you can build fully functional executables using the Ruby Development Kit. Ruby includes a way to install so-called gems—software packages that you can use from the command line. Jekyll is one of them! Click the button below to find out how you can successfully install it.

