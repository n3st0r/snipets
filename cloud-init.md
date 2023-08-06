# Files

Config file location: `/etc/sysconfig/cloudinit`

Cloud-init output log file: `/var/log/cloud-init-output.log`

# Setup hostname:

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

### Change Passwords for Existing Users
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

### Example write SSH config file
```yaml
write_files:
  - path: /etc/ssh/sshd_config
    content: |
         Port 22
         Protocol 2
         HostKey /etc/ssh/ssh_host_ed25519_key
         UsePrivilegeSeparation yes
         KeyRegenerationInterval 3600
         ServerKeyBits 2048
         SyslogFacility AUTH
         LogLevel INFO
         LoginGraceTime 120
         PermitRootLogin no
         StrictModes yes
         RSAAuthentication yes
         PubkeyAuthentication yes
         IgnoreRhosts yes
         RhostsRSAAuthentication no
         HostbasedAuthentication no
         PermitEmptyPasswords no
         ChallengeResponseAuthentication no
         X11Forwarding yes
         X11DisplayOffset 10
         PrintMotd no
         PrintLastLog yes
         TCPKeepAlive yes
         AcceptEnv LANG LC_*
         Subsystem sftp /usr/lib/openssh/sftp-server
         UsePAM yes
         UseDNS no
         AllowGroups sshusers
```

### Run commands
```yaml
runcmd:
  - sed -i -e '/^Port/s/^.*$/Port 4444/' /etc/ssh/sshd_config
  - sed -i -e '/^PermitRootLogin/s/^.*$/PermitRootLogin no/' /etc/ssh/sshd_config
  - sed -i -e '$aAllowUsers demo' /etc/ssh/sshd_config
  - restart ssh
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

# Disk Setup and mounts the additional volumes.

### Mounts
If device does not exist at the time, an entry will still be written to /etc/fstab
```yaml
mounts:
  - [ xvdb, /data,"auto","defaults,nofail", "0", "0" ]
  - [ sdc, /opt/data ]
```

>To override the default SWAP configuration
```yaml
mounts:
- [ swap, null ]
```

>To configure SWAP as file
```yaml
swap:
  filename: /swap.img
  size: "auto" # or size in bytes
  maxsize: size in bytes
```

### Option `mount_default_fields`
These values are used to fill in any entries in 'mounts' that are not complete.  This must be an array, and must have 6 fields.
```yaml
mount_default_fields: [ None, None, "auto", "defaults,nofail", "0", "2" ]
```

# setup the file system on the device
```yaml
fs_setup:
 - label: data
   filesystem: 'ext4'
   device: '/dev/xvdb'
   partition: auto
runcmd:
 - mkdir /data
```


# Links and docs:

* [cloud-init Documentation](https://cloudinit.readthedocs.io/en/latest/)
