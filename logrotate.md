# Example configurations for different types of services

## Basic usage
Verify logrotate status:
```
cat /var/lib/logrotate/status
```

Manually run specyfic logrotate rule:
```
logrotate -f /etc/logrotate.d/nginx
```

Manually run rotate all the logs in verbose mode:
```
logrotate -f -v /etc/logrotate.conf
```

Now, run the logrotate command as shown below. Option -s specifies the filename to write the logrotate status.
```
logrotate -s /var/log/logstatus logrotate.conf
```

### Logrotate copytruncate option
copy of the original file and truncates the original file to zero byte size.
```
/var/log/example.log {
    size 1M
    copytruncate
    rotate 7
}
```
### Option compress
The rotated files will be compressed with gzip utility.

```
/var/log/example.log {
    size 1k
    create 640 root root
    rotate 7
    compress
}
```
### Option dateext
rotate the old log file with date in the log filename

```
/tmp/output.log {
    size 1k
    dateext
    rotate 4
}
```
### Option missingok
Dont return error if the log file is missing

```
/tmp/output.log {
        size 1k
        copytruncate
        rotate 4
        compress
        missingok
}
```

