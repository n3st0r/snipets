
# SSH conection

## Add jump/bastion host
```bash
ansible_ssh_common_args='-o ProxyCommand="ssh -W %h:%p -q user@jump_host"'
```
