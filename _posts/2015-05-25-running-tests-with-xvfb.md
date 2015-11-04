---
layout: post
title: "Running tests with Xvfb"
description: "My experience with Xvfb"
category: "dev"
tags:
 - rspec
 - xvfb
---

Xvfb (short for X virtual framebuffer) is an in-memory display server for
UNIX-like operating system (e.g., Linux). It enables you to run graphical
applications without a display (e.g., browser tests on a CI server) while also
having the ability to take screenshots.

### Installation on Ubuntu
{% highlight bash %}
sudo apt-get install xvfb

#also make sure you have firefox installed
sudo apt-get install firefox

{% endhighlight %}

### Run RoR project tests with Xvfb
Go to your project folder and run
{% highlight bash %}

xvfb-run bundle exec rspec

{% endhighlight %}

## Gotchas
Sometimes it behaves differently from regular selenium local testing. For
example it will not be able to click on 'overlapped' element, and test will fail,
while the same test passes wen running without Xvfb.

### Links
  * [Xvfb](http://www.x.org/releases/X11R7.6/doc/man/man1/Xvfb.1.xhtml)
  * [How To Run Your Tests Headlessly with
    Xvfb](http://elementalselenium.com/tips/38-headless)
