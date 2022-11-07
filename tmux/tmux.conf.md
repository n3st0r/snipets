
## Lets change prefix
remap prefix from `Ctrl + b` to `Ctrl+a`
```
unbind C-b
set-option -g prefix C-a
bind-key C-a send-prefix
```

## Shortcut to config reload
```
bind r source-file ~/.tmux.conf
```
