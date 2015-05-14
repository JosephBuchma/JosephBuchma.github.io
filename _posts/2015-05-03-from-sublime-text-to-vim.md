---
layout: post
title: "From Sublime Text to Vim"
description: "Migration from Sublime Text and regular Terminal
to Vim and Tmux"
category: devtools
tags: [vim, tmux, editors, workflow, devtools]
---
{% include JB/setup %}

_This post is beginning of my 'best workflow exploration'. During this journey I'll write shell script for quick bootstrap of this perfect workspace on fresh Ubuntu machine._

Vim is all about `~/.vimrc` file. There is no superhandy "Package control", but
there are [vimawesome.com](http://vimawesome.com/) with over 11K (!) plugins available, and
tools like [NeoBundle](https://github.com/Shougo/neobundle.vim) for managing your plugins.
While swithcing to Vim I also found [Tmux](http://tmux.sourceforge.net/).
Using Vim and Tmux together lets you burn your mouse and/or drill out touchpad with pleasure.

The simplest way to quickly make your Vim ready to code is to install
one of ready to use plugin packs (which are finally just .vimrc). I used [dotvim](https://github.com/astrails/dotvim).

#### Useful links & tips
   - __Tmux__
      + look into __tmux.conf__ for remappings
      + [complete cheat sheet](https://gist.github.com/MohamedAlaa/2961058) 
   - __Vim__
      + [Vim movement cheat sheet](https://raw.githubusercontent.com/LevelbossMike/vim_shortcut_wallpaper/master/vim-shortcuts_1280x800.png)
      + press `?` inside nerdtree, helpful
      + select visually and press `Ctrl-n` / `Ctrl-p` for multiple cursors
      + surround: `cs"'`-change; `ds"`-delete; `ysiw"`-wrap. [See all](https://github.com/tpope/vim-surround#surroundvim)
      + look for all available features of [dotvim](https://github.com/astrails/dotvim)

### Let's bash
<script src="https://gist.github.com/JosephBuchma/fc857d7c14c0ea2c475a.js"></script>

### My current .vimrc.after and .vimrc.before
<script src="https://gist.github.com/JosephBuchma/650d0dd87b553ca2c8a0.js"></script>

### My tmux.conf
_todo:_ update bash script to include tmux config

<script src="https://gist.github.com/JosephBuchma/72709f7b22655f7ce339.js"></script>