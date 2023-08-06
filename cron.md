# CRON

## Cron explaining
```
* * * * *  command_to_execute
│ │ │ │ │
│ │ │ │ └───────────── day of week (0 - 7)
│ │ │ └───────────── month (1 - 12)
│ │ └───────────── day of month (1 - 31)
│ └───────────── hour (0 - 23)
└───────────── minute (0 - 59)

```
# Values in place of asterisks may be
* numerical values
* `*`	any value
* `,`	value list separator
* `-`	range of values
* `/`	step values
* @reboot	(non-standard)
* @yearly	(non-standard)
* @annually	(non-standard)
* @monthly	(non-standard)
* @weekly	(non-standard)
* @daily	(non-standard)
* @midnight (non-standard) - the same as daily, but at midnight
* @hourly	(non-standard)

Day of the week start from the `0` means Sunday, then `1` means Monday, and so on up to `6` means Saturday and finish with `7` as Sunday. Because different calendars/locations have different start of the week: Sunday or Monday.

# Examples

Every day at 0:00
```
0 0 * * * /some/directory/command
```

Run command every 10 minutes
```
*/10 * * * *             /some/directory/command
0-59/10 * * * *          root  /bin/run-parts /etc/cron.10min
0,10,20,30,40,50 * * * * /some/directory/command
```
