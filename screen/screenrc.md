# Option for `screen` configuration

```
startup_message off
vbell off
```

bigger scrollback buffer
```
defscrollback 5000
```

Mouse tracking allows to switch region focus by clicking
```
mousetrack on
```

Window numbering starts at 1, not 0.
```
bind c screen 1
bind 0 select 10
escape ^aa
```

Nice status:
```
defutf8 on

hardstatus alwayslastline
hardstatus string '%{gk}[ %{G}%H %{g}][%= %{wk}%?%-Lw%?%{=b kR}(%{W}%n*%f %t%?(%u)%?%{=b kR})%{= kw}%?%+Lw%?%?%= %{g}][%{Y}%l%{g}]%{=b C}[ %m/%d %c ]%{W}'

```

Other two-line status, with the current window highlighted
```
hardstatus alwayslastline
hardstatus string '%{= kG}[%{G}%H%? %1`%?%{g}][%= %{= kw}%-w%{+b yk} %n*%t%?(%u)%? %{-}%+w %=%{g}][%{B}%m/%d %{W}%C%A%{g}]'
```

navigating regions with Ctrl-arrows
```
bindkey "^[[1;5D" focus left
bindkey "^[[1;5C" focus right
bindkey "^[[1;5A" focus up
bindkey "^[[1;5B" focus down
```

sets your X clipboard to the content of screens copy buffer
```
bind v eval "writebuf" "exec sh -c 'exec xsel -b --display :0 -i < /tmp/screen-exchange'"
```
