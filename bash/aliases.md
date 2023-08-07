# Bash aliases
[README.md - back](../README.md)

```bash
alias free="free -mt"
```
copy with progress bar
```bash
alias cpv='rsync -ah --info=progress2'
```

Print ip output with colors
```bash
alias ip="ip -color"
```

Print my public IP
```bash
alias myip='curl ipinfo.io/ip'
```

ll - better ls
```bash
alias ll="ls -lhA"
```

mkcd - create a directory and enter it
```bash
mkcd ()
{
  mkdir -p -- "$1" && cd -P -- "$1"
}
```

Create and use a Python virtual environment
```bash
alias pyvenv='python3 -m venv ./venv'
alias pysource='source ./venv/bin/activate'
```

Debian/Ubuntu package management
```bash
alias apt='sudo apt'
alias upgrade='apt list --upgradable && apt -u --yes dist-upgrade'
```
