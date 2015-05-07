---
layout: post
title: "From Sublime Text to Vim"
description: "Migration from Sublime Text and regular Terminal
to Vim and Tmux"
category: programming
tags: [vim, tmux, editors, workflow]
---
{% include JB/setup %}

Vim is all about `~/.vimrc` file. There is no superhandy "Package control", but
there are [vimawesome.com](http://vimawesome.com/) with over 11K (!) plugins available, and
tools like [NeoBundle](https://github.com/Shougo/neobundle.vim) for managing your plugins.
While swithcing to Vim I also found [Tmux](http://tmux.sourceforge.net/).
Using Vim and Tmux together lets you burn your mouse and/or drill out touchpad with pleasure.

The simplest way to quickly make your Vim ready to code is to install
one of ready to use plugin packs (which are finally just .vimrc). I used [dotvim](https://github.com/astrails/dotvim).

### Let's bash

{% highlight bash %}
#!/bin/bash

# This script setting up ready to use Tmux and Vim with plugins
# run with sudo
# Tested on Ubuntu 14.04

# install Tmux
apt-get install tmux

# remove vim-tiny installed by default
apt-get remove vim-tiny

# install full Vim
apt-get install vim

# install astrails/dotvim plugins pack for Vim
# following installation guide
# https://github.com/astrails/dotvim#installation
cd
rm -rf .vim .vimrc > /dev/null 2>&1
# for convenience let's group everything inside ~/vimrc directory
# as I also have my personal adjustments for Vim
# and other related stuff will be stored here
sudo -u $SUDO_USER mkdir vimrc 
sudo -u $SUDO_USER git clone https://github.com/JosephBuchma/dotvim.git vimrc/dotvim/
sudo -u $SUDO_USER ln -sfn vimrc/dotvim .vim
sudo -u $SUDO_USER ln -sfn vimrc/dotvim/vimrc .vimrc
cd .vim
sudo -u $SUDO_USER make install


cd
# At this point you can create new session in tmux 
# and run vim inside. In my case I see that colors are not being displayed correctly
# so let's fix it. First of all set 256-colors mode for terminal:
sudo -u $SUDO_USER printf '\nexport TERM="xterm-256color"\n' >> .bashrc

# Also there is gotcha with freezing terminal when hitting Ctrl-s
# (which you will do quite frequently after switching from Sublime)
# here is fix
sudo -u $SUDO_USER printf 'stty -ixon\n' >> .bashrc

# also you need to add 'set t_ut=' (without quotes) to your .vimrc 
# (.vimrc.after in case of using dotvim)
# see also http://snk.tuxfamily.org/log/vim-256color-bce.html
# I created github repo for my .vimrc.before and .vimrc.after
# so let's clone it and link ~/.vimrc.before/after to files from repo
sudo -u $SUDO_USER git clone https://github.com/JosephBuchma/mydotvim.git vimrc/mydotvim/
sudo -u $SUDO_USER ln -sfn vimrc/mydotvim/vimrc.before .vimrc.before
sudo -u $SUDO_USER ln -sfn vimrc/mydotvim/vimrc.after .vimrc.after

# Look for content of .vimrc.before/after below. Installation is complete!

# Just one last thing.
# Unfortunately, There is no "true" Monokai (my favorite) color scheme
# so I migrated to Solarized Dark. Let's install Solarized for Terminal too 
# source: http://www.webupd8.org/2011/04/solarized-must-have-color-paletter-for.html
sudo -u $SUDO_USER wget --no-check-certificate https://raw.github.com/seebi/dircolors-solarized/master/dircolors.ansi-dark
sudo -u $SUDO_USER mv dircolors.ansi-dark .dircolors
sudo -u $SUDO_USER eval `dircolors ~/.dircolors`
cd vimrc
sudo -u $SUDO_USER git clone https://github.com/sigurdga/gnome-terminal-colors-solarized.git
cd gnome-terminal-colors-solarized
sudo -u $SUDO_USER /bin/bash set_dark.sh

echo 'Tmux and Vim with plugins are being successfully installed!'




# Finish! Enjoy :)

{% endhighlight %}

### My current .vimrc.after and .vimrc.before

#### vimrc.before
```
coming soon
```

#### vimrc.after
```
coming soon
```



