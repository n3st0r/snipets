
```bash
alias free="free -mt"
```

Print ip output with colors
```bash
alias ip="ip -color"
```

ll - better ls
```bash
alias ll="ls -lhA"
```

psg
```bash
alias psg="ps aux | grep -v grep | grep -i -e VSZ -e"
```

mkcd - create a directory and enter it
```bash
mkcd ()
{
  mkdir -p -- "$1" && cd -P -- "$1"
}
```
