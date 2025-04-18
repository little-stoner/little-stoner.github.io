---
title: learn vim
categories:
  - vim
tags:
  - vim
---

# Learn Vim
I need to use vim to do something.
[Vim] (https://vimdoc.sourceforge.net/)

## Text Editor
When I use emacs and vscode, I prefer to use keyboard to mouse.
What we can do with text editor
- open file
- move cursor
- edit text
- save file

The core of text editor is edit text, so we need move cursor 
and edit text more efficient.

How can we be more efficient with `Vim` ?

#### open file
```sh
vim file.txt
```
#### save file
```sh
:wq
```

### Mode
What is mode ? 
- what you do to the text

### Move cursor
How to move cursor ? 
- character by character
- word by word
- line by time
- paragraph by time
- screen by time
- file by time
- jump

#### character by character
```sh
       ^
       k              
 < h       l >        
       j              
       v
```

Example: `(word) word`
type `w` move forwart to start of next word
type `W` move forwart to start of next word, ignore punctuation
type `e` move to end of current word
type `E` move to end of current word, ignore punctuation
type `b` move back to start of a word
type `B` move back to start of a word, ignore punctuation
type `ge` move to backwords to the end of a word
type `gE` move backwords to eht end of a word, ignore punctuation

type `G` move to the end of the file
type `gg` move to the start of the file





### Edit text
- insert
- append
- delete
- copy
- paste
- mark
- search
- replace
- diff
- format
- undo
- repeat action

#### insert
press `i` to insert text

#### append
press `a` to append text after the cursor

#### delete
press `x` to delete the character under the cursor
type `dw` to delete until the start of the next word
type `de` to delete to the end of the current word
type `d$` to delete from the cursor to the end of the line
type `dd` to delete a line

#### undo
type `u` to undo the last change
type `U` to undo all changes on the current line

#### repeat action
type `2w` to repeat the last action 2 times


#### copy
type `y` to copy the text
type `yy` to copy the current line
type `yw` to copy the current word
type `y$` to copy from the cursor to the end of the line
type `y2w` to copy the next two wordss

#### paste
type `p` to paste the text after the cursor
type `P` to paste the text before the cursor

#### replace
type `r` to replace the character under the cursor
type `R` to replace the character under the cursor and enter replace mode
type `ce` to change the current word
type `c$` to change the current line

type `:s/old/new/g` to replace all old with new in the current line
type `:s/old/new/g` to replace all old with new in the line
type `#,#s/old/new/g` to replae phrases between two line #'s type
type `:%s/old/new/g` to replace all old with new in the file
type `:%s/old/new/gc` to replace all old with new in the file and ask for confirmation

#### search
type `/` to search for a string
type `?` to search for a string backwards
type `n` to repeat the last search
type `N` to repeat the last search backwards

#### match
type `%` to jump to the matching parenthesis

#### virtual edit
type `v` to enter visual mode
type `V` to enter visual line mode

#### manipulate line 
type `o` to open a new line below the current line
type `O` to open a new line above the current line
type `a` to append text after the cursor
type `A` to append text at the end of the line
