# Files

Config file location: `/etc/sysconfig/cloudinit`

Cloud-init output log file: `/var/log/cloud-init-output.log`

#To add additional users to the instance

### Setup hostname:

```yaml
fqdn: myhostname.com
```

### Add groups to the system
```yaml
groups:
  - group1
  - group2: [user1, user2]
```

### Add users to the system
```yaml
users:
  - name: alice
    sudo: ALL=(ALL) NOPASSWD: ALL
    groups: admin, root
    expiredate: '2032-09-01'
    passwd: $6$j212wezy$7H/1LT4f9/N3wpgNunhsIqtMj62OKiS3nyNwuizouQc3u7MbYCarYeAHWYPYb2FT.lbioDm2RrkJPb9BZMN1O/
  - name: bob
    sudo: False
    ssh_authorized_keys:
      - <ssh pub key 1>
      - <ssh pub key 2> 
    plain_text_passwd: 'ubuntu'
    home: /home/ubuntu
    shell: /bin/bash
    lock_passwd: True
```

Change Passwords for Existing Users
```yaml
chpasswd:
  list: |
    user1: password1
    user2: password2
  expire: False
```

### Write Files to the Disk
```yaml
#cloud-config
write_files:
  - path: /test.txt
    content: |
      First line.
      Second line.
```

### To update packages and install new ones:
```yaml
package_update: true
packages:
  - package_1
  - [package_2, version_number]
```

### Configure an instances resolv.conf
```yaml
manage_resolv_conf: true

resolv_conf:
  nameservers:
    - '1.1.1.1'
    - '8.8.8.8'
  searchdomains:
    - foo.example.com
    - bar.example.com
  domain: example.com
  options:
    rotate: true
    timeout: 1
```

