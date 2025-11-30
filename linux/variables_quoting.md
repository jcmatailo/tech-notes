## Variables
In the Bash shell, there are two types of variables: local and environment.

### Local Variables
**Local (or shell) variables** exist only in the current shell session and do not affect other commands or applications.

### Environment Variables
**Environment (or global) variables** are available system-wide, across all Bash shells when interpreting commands and performing tasks.

| **Command** | **Description** |
| --- | --- |
| `variable=value` | Set the value of a variable (creates a new local variable if it does not exist) |
| `echo $variable` | Display the value of a variable |
| `echo -e "message"` | Interpret escape characters in the message |
| `echo -n "message"` | Display a message without the trailing newline |
| `env` | List all environment variables |
| `declare variable` | Define or modify variables with specific attributes |
| `declare -i variable` | Treat the variable as an integer |
| `declare -r variable` | Make the variable read-only |
| `export variable` | Convert a local variable into an environment variable |
| `unset variable` | Remove a variable |
| `type command` | Display information about a command type |
| `type -a command` | Display all locations containing the command |


## Internal Commands
Internal commands (built-ins) are part of the shell itself. 

## External Commands
External commands are binary executables stored in directories searched by the shell.

| **Command** | **Description** |
| --- | --- |
| `which command` | Show the full path of an external command |


## Functions
Functions allow you to group multiple commands under a single name, making them reusable.

```
function_name () {
	commands
}
```


## Quoting

### Double quotes "..."
Double quotes prevent the shell from interpreting most special characters, but still allow variable and command substitution.

```bash
sysadmin@localhost:~$ echo "The glob characters are *, ? and [ ]"
OUTPUT: The glob characters are *, ? and [ ]**
```

Double quotes still allow for command substitution, variable substitution, and permit some other shell metacharacters.

```bash
sysadmin@localhost:~$ echo "The path is $PATH"
OUTPUT: The path is /usr/bin/custom:/home/sysadmin/bin:/usr/local/sbin**
```

### Single quotes '...'
Single quotes prevent all interpretation of special characters, variables, and substitutions.

```bash
sysadmin@localhost:~$ echo The car costs $100
OUTPUT: The car costs 00**
```

```bash
sysadmin@localhost:~$ echo 'The car costs $100'
OUTPUT: The car costs $100**
```

### Backslash 
Use a backslash to escape individual characters and prevent their interpretation.

```bash
sysadmin@localhost:~$ echo The service costs \$1 and the path is $PATH
OUTPUT: The service costs $1 and the path is /usr/bin/custom:/home/sysadmin/bin:/usr/local/sbin**
```

### Backquotes
Backquotes (backticks) perform command substitution. The preferred modern syntax is $(command).

```bash
sysadmin@localhost:~$ echo Today is date
OUTPUT: Today is date**
```

```bash
sysadmin@localhost:~$ echo Today is `date`
OUTPUT: Today is Mon Dec 3 21:33:41 UTC 2018**
```


## Control Operators

### Semicolon (;)
| **Command** | **Description** |
| --- | --- |
| `command1; command2` | Run command1, then run command2 |

### Double Ampersand (&&)
| **Command** | **Description** |
| --- | --- |
| `command1 && command2` | Run command2 only if command1 succeeds (exit code 0) |

### Double Pipe (||)
| **Command** | **Description** |
| --- | --- |
| `command1 \|\| command2` | Run command2 only if command1 fails (non-zero exit code) |
