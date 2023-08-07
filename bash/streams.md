# Streams and pipes
[README.md - back](../README.md)

## Three standard streams as file descriptors
Below is a table to help understand the relationship.
| File descriptor | Stream | Strean name |
|---|---|---|
| 0 | stdin | Standard Input |
| 1 | stdout | Standard Output |
| 2 | stderr | Standard Error |

## Redirection Operators

Redirection operators are a subset of control operators. They allow you to direct the input or output `stream` of your command.

## `<` -  Input Operator

The `<` operator gives input to a command or process.


## `<>` Input Operator (rw)

The `<>` operator does the same as the input operator only it opens the file in read/write mode If the file does not exist, it will be created. Since most input is from the keyboard or read from a file, this is rarely used.

## `>` Output Operator

The `>` operator controls the command output stream. The file optput are redirecting will be overwritten or created if dosn't exist.

## The `>>` Append Output Operator

The `>>` operator controls the command output like `>` operator, but add to the existing file, instead of overwriting.

## The Non-Standard Operators
Non-standard operators direct both standard output (stdout) and standard error (stderr):
* `&>` - overwrites existing files
* `&>>` - append to existing files

## `|` (pipe) Operator

The `|` operator pass output of command to another command.
