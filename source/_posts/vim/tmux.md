---
title: tmux config
categories:
  - vim
tags:
  - vim
---

# tmux 
add `.tmux.conf` file to your home directorys

```sh
# SELF CONFIG

#-- base settins --#
set -g display-time 3000
set -g escape-time 0
set -g history-limit 65535
set -g base-index 1
set -g pane-base-index 1

# split window
unbind '"'
# vertical split (prefix -)
bind - splitw -v
#
unbind %
# horizontal split (prefix |)
bind | splitw -h

# unbind key
set -g prefix C-h
#unbind C-b

# panel select
bind-key k select-pane -U
bind-key j select-pane -D
bind-key h select-pane -R
bind-key l select-pane -L

# resize pane
bind -r ^k resizep -U 10 # upward (prefix Ctrl+k)
bind -r ^j resizep -D 10 # downward (prefix Ctrl+j)
bind -r ^h resizep -L 10 # to the left (prefix Ctrl+h)
bind -r ^l resizep -R 10 # to the right (prefix Ctrl+l)

# swap pane
# swap with the previous pane (prefix Ctrl+u)
bind ^u swapp -U
# swap with the next pane (prefix Ctrl+d)
bind ^d swapp -D

# copy mode
set-window-option -g mode-keys emacs
#set-window-option -g utf8 on


# reload config (prefix r)
bind r source ~/.tmux.conf \; display "Configuration reloaded!"


#==========================================================
# -- copy mode -----------------------------------------------------------------

#Copy tmux paste buffer to CLIPBOARD(CLIPBOARD selection integration)
#must install xclip and xsel
bind C-c run "tmux save-buffer - | xclip -i -selection clipboard"
#Copy CLIPBOARD to tmux paste buffer and paste tmux paste buffer
bind C-v run "tmux set-buffer -- \"$(xclip -o -selection clipboard)\"; tmux paste-buffer"
#=============================================
# tmux-poweline
# $ cd ~/some/path/
# $ git clone https://github.com/erikw/tmux-powerline.git
set-option -g status on
set-option -g status-interval 2
set-option -g status-justify "centre"
set-option -g status-left-length 60
set-option -g status-right-length 90
set-option -g status-left "#(~/tmux-powerline/powerline.sh left)"
set-option -g status-right "#(~/tmux-powerline/powerline.sh right)"
#set-window-option -g window-status-current-format "#[fg=colour235, bg=colour27]⮀#[fg=colour255, bg=colour27] #I ⮁ #W #[fg=colour27, bg=colour235]⮀"
# status left/right sections separators
tmux_conf_theme_left_separator_main=''
tmux_conf_theme_left_separator_sub='|'
tmux_conf_theme_right_separator_main=''
tmux_conf_theme_right_separator_sub='|'
####
bind C-[ run '~/tmux-powerline/mute_powerline.sh left'		# Mute left statusbar.
bind C-] run '~/tmux-powerline/mute_powerline.sh right'		# Mute right statusbar.
#
```