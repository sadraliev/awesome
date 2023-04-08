# Tmux

## Install
before to install `tmux` you have installed `Iterm2` and `HomeBrew` package manager.
`brew install tmux`

install [Tmux package manager](https://github.com/tmux-plugins/tpm) to install plugins for tmux

`git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`

## Setting
Now, we need to set up plugins.
create a new file `nvim ~/.tmux.conf` and paste the below.
```conf
set -g default-terminal "screen-256color"
# main prefix
set -g prefix C-a
# sort by name
bind s choose-tree -sZ -O name
#change index
set -g base-index 1
setw -g pane-base-index 1
#re-assugn keypads
unbind %
bind | split-window -h

unbind '"'
bind - split-window -v

unbind r
bind r source-file ~/.tmux.conf

bind -r j resize-pane -D 5
bind -r k resize-pane -U 5
bind -r l resize-pane -R 5
bind -r h resize-pane -L 5

bind -r m resize-pane -Z

set -g mouse on

set-window-option -g mode-keys vi

bind-key -T copy-mode-vi 'v' send -X begin-selection
bind-key -T copy-mode-vi 'y' send -X copy-selection

unbind -T copy-mode-vi MouseDragEnd1Pane

# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
# 
set -g @plugin 'christoomey/vim-tmux-navigator'
#  for tmux
set -g @plugin 'jimeh/tmux-themepack'
# store session after reboot
set -g @plugin 'tmux-plugins/tmux-resurrect'
set -g @plugin 'tmux-plugins/tmux-continuum'
# session manager
set -g @plugin 'tmux-plugins/tmux-sessionist'
# choosen theme
set -g @themepack 'powerline/default/blue'

set -g @resurrect-capture-pane-contents 'on'
set -g @continuum-restore 'on'
# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm'
```
then, go to tmux `tmux`, and install plugins.
`ctrl + a, than shift + i`.

## Most popular Shortkeys
`tmux kill-server` kill process
`ctrl + a` = prefix

`prefix, s` = session manager
`prefix, $` = rename session
`prefix, C` = create new session with custom name or `tmux new -s name`
`prefix, c` = create new tab
`prefix, &` = kill tab
`prefix, ()` = switch between tabs
`prefix, g` = switch using filter
`prefix, ,` = rename tab
`prefix, w` = list of tabs


