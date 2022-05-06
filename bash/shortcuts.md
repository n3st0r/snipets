
Control Keys combinations
* `ctrl` + `a` - move your cursor to the beginning of the line
* `ctrl` + `e` - move your cursor to the end of the line
* `ctrl` + `k` - delete any characters from your cursor to the end of the line
* `ctrl` + `u` - delete any characters from your cursor to the beginning of the line
* `ctrl` + `w` - delete the previous word
* `ctrl` + `t` - transpose two previous characters
* `ctrl` + `y` - yank/recover the last deletion
* `ctrl` + `d` - delete one character at the cursor position
* `ctrl` + `h` - delete one character before the cursor
* `ctrl` + `f` - move forward (or use the right arrow)
* `ctrl` + `b` - move backward (or use the left arrow)
* `ctrl` + `r` - find character sequence in history (completion mode)
* `ctrl` + `g` - escape from completion mode
* `ctrl` + `v` - Literal next (LNEXT)
* `ctrl` + `XX` - Switch cursor position between start of the command line and the current position
* `ctrl` + `]` + `x` Moves the cursor forward to next occurrence of x
* `alt` + `F`/`Esc` + `F` - Moves the cursor one word forward
* `alt` + `B`/`Esc` + `B` - Moves the cursor one word backward

Bash History
* `CTRL` + `r` - Incremental reverse search of bash history
* `ALT` + `p` - Non-incremental reverse search of bash history
* `CTRL` + `j` - Ends history search at current command
* `CTRL` + `_` - Undo previous command
* `CTRL` + `p` / `Up arrow` - Moves to previous command
* `CTRL` + `n` / `Down arrow` - Moves to next command
* `CTRL` + `s` - Gets the next most recent command
* `CTRL` + `o` - Runs and re-enters the command found via Ctrl + S and Ctrl + R
* `CTRL` + `g` - Exits history search mode
* `!!` - Runs last command
* `!*` - Runs previous command except its first word
* `!*:p` - Displays what !* substitutes
* `!x` - Runs recent command in the bash history that begins with x
* `!x:p` - Displays the x command and adds it as the recent command in history
* `!$` - Same as OPTION+., brings forth last argument of the previous command
* `!^` - Substitutes first argument of last command in the current command
* `!$:p` - Displays the word that !$ substitutes
* `^123^abc` - Replaces 123 with abc
* `!n:m` - Repeats argument within a range (i.e, m 2-3)
* `!fi` - Repeats latest command in history that begins with fi
* `!n` - Run nth command from the bash history
* `!n:p` - Prints the command !n executes
* `!n:$` - Repeat arguments from the last command (i.e, from argument n to $)
