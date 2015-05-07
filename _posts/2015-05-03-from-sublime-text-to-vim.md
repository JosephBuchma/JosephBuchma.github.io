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
<script src="https://gist.github.com/JosephBuchma/fc857d7c14c0ea2c475a.js"></script>

### My current .vimrc.after and .vimrc.before
<script src="https://gist.github.com/JosephBuchma/650d0dd87b553ca2c8a0.js"></script>