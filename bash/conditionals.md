# File conditions
[README.md - back](../README.md)

* `[[ -b FILE ]]` - True if the `FILE` exists and is a block special file.
* `[[ -c FILE ]]` - True if the `FILE` exists and is a special character file.
* `[[ -d FILE ]]` - True if the `FILE` is Directory
* `[[ -e FILE ]]` - True if the `FILE` exists
* `[[ -f FILE ]]` - True if the `FILE` is File
* `[[ -g FILE ]]` - True if the `FILE` exists and has set-group-id (sgid) flag set.
* `[[ -G FILE ]]` - True if the `FILE` exists and has the same group as the user running the command.
* `[[ -h FILE ]]` - True if the `FILE` exists and is a symbolic link.
* `[[ -h FILE ]]` - True if the `FILE` is symlink
* `[[ -k FILE ]]` - True if the `FILE` exists and has a sticky bit flag set.
* `[[ -L FILE ]]` - True if the `FILE` exists and is a symbolic link.
* `[[ -O FILE ]]` - True if the `FILE` exists and is owned by the user running the command.
* `[[ -p FILE ]]` - True if the `FILE` exists and is a pipe.
* `[[ -r FILE ]]` - True if the `FILE` readable
* `[[ -S FILE ]]` - True if the `FILE` exists and is socket.
* `[[ -s FILE ]]` - True if the `FILE` size is > 0 bytes
* `[[ -u FILE ]]` - True if the exists and set-user-id (suid) flag is set.
* `[[ -w FILE ]]` - True if the `FILE` is Writable
* `[[ -x FILE ]]` - True if the `FILE` is Executable
* `[[ FILE1 -ef FILE2 ]]` - Same files
* `[[ FILE1 -nt FILE2 ]]` - 1 is more recent than 2
* `[[ FILE1 -ot FILE2 ]]` - 2 is more recent than 1

# Conditions

* `[[ -z STRING ]]` - Empty string
* `[[ -n STRING ]]` - Not empty string
* `[[ STRING == STRING ]]` - Equal
* `[[ STRING != STRING ]]` - Not Equal
* `[[ NUM -eq NUM ]]` - Equal
* `[[ NUM -ne NUM ]]` - Not equal
* `[[ NUM -lt NUM ]]` - Less than
* `[[ NUM -le NUM ]]` - Less than or equal
* `[[ NUM -gt NUM ]]` - Greater than
* `[[ NUM -ge NUM ]]` - Greater than or equal
* `[[ STRING =~ STRING ]]` - Regexp
* `(( NUM < NUM ))` - Numeric conditions
* `[[ -o noclobber ]]` - If OPTIONNAME is enabled
* `[[ ! EXPR ]]` - Not
* `[[ X && Y ]]` - And
* `[[ X || Y ]]` - Or
