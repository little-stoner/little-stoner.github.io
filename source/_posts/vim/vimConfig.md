---
title: vim config
categories:
  - vim
tags:
  - vim
---


# vim config 
add `.vimrc` file to your home directorys

```sh
set clipboard=unnamed
set nocompatible
set visualbell
set showmode
set nu
set encoding=UTF-8
filetype on
filetype plugin on
filetype indent on
set smarttab
syntax on
set mouse=a

set cursorline
set cursorcolumn
" set guicursor=n-ci:hor30-iCursor-blinkwait300-blinkon200-blinkoff150
" Change cursor shape between insert and normal mode in iTerm2.app
if $TERM_PROGRAM =~ "iTerm"
    let &t_SI = "\<Esc>]50;CursorShape=0\x7" " Vertical bar in insert mode
    let &t_EI = "\<Esc>]50;CursorShape=2\x7" " Block in normal mode
endif


colorscheme slate

set shiftwidth=4
set tabstop=4
set nobackup
set wrap
set ignorecase

call plug#begin('~/.vim/plugged')
Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }
" Plug '/usr/local/opt/fzf'
Plug 'junegunn/fzf.vim'
c
```