The shell is a command-line interpreter that translates user-entered commands into actions executed by the operating system. The most widely used shell in Linux distributions is **Bash**.


## Prompt Structure
- User Name: **sysadmin**@localhost:~$
- System Name: sysadmin@**localhost**:~$
- Current Directory: sysadmin@localhost:**~**$
(*Note: The ~ symbol is shorthand for the user’s home directory.*)


## Command Format:
command [ options ] [ arguments ]

### Command History
| **Command** | **Description** |
| --- | --- |
| `history` | Display the command history list |
| `history n` | Display the last *n* commands |
| `!n` | Execute the command with history number *n* |
| `!-n` | Execute the nth command from the end of the history list |
| `!!` | Execute the most recent command |
| `!ls` | Execute the most recent `ls` command |

### Date and Time Commands
| **Command** | **Description** |
| --- | --- |
| `clock -w` | Save the current date and time to the BIOS |
| `cal [month] [year]` | Display a calendar |
| `date` | Show the current date and time |
| `date -u` | Show the date in universal (UTC) format |
| `date 041217002011` | Set the system date and time |
| `date +%D:%d/%m/%y%t%T` | Display the date and time in a custom format |
| `date --set "yyyy-mm-dd hh:mm"` | Set the system date and time |

### System Information and Utilities
| **Command** | **Description** |
| --- | --- |
| `who`, `w`, `users` | Display who is logged in |
| `whoami` | Display the username of the current user |
| `tty` | Display the terminal (console) the user is working on |
| `uname` | Display system information |
| `uname -a` | Display detailed kernel information |
| `uname -r` | Display the kernel version |
| `uname -n` / `uname --nodename` | Display the network node hostname (also shown in the prompt) |
| `pwd` | Display the current working directory |
| `clear` | Clear the terminal screen |
| `set +o history` | Disable command history |
| `set -o history` | Enable command history |
| `fc -l` | List commands |
| `fc -l command1 command2` | List commands from command1 to command2 |
| `fc -n` | Edit and run commands |
| `finger user` | Display information about a user |

## Aliases
| **Command** | **Description** |
| --- | --- |
| `alias` | List aliases currently defined in the shell |
| `alias name="command"` | Create a new alias to map longer commands to shorter key sequences |
| `unalias name` | Remove an alias |

## File Search with find
| **Command** | **Description** |
| --- | --- |
| `find / -name file` | Search for files and directories starting from the system root |
| `find / -user user1` | Search for files and directories owned by user1 |
| `find / -type d -name dir1` | Find all directories named *dir1* |
| `find / -type f -name "*.jpg"` | Find all `.jpg` files |
| `find / -type f -size +100M` | Find all files larger than 100 MB |
| `find / -type f -mtime -1` | Find all files modified within the last 24 hours |
| `find / -type f -name "*.tmp" -delete` | Find and delete all `.tmp` files |
| `find / -type f -amin -60` | Find all files accessed within the last hour |
