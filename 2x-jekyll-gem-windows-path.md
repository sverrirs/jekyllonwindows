---
layout: page
title: Adding environment variables in Windows
prev:
    url: 2-jekyll-gem.html
    title: Jekyll Gem
next:
    url: 2-jekyll-gem.html
    title: Jekyll Gem
---

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