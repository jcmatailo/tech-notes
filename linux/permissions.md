# Permissions

| **Value** | **Permission** | **Description** |
|---|---|---|
| 0 | \---  | no permission          |
| 1 | \--x  | execute                |
| 2 | \-w-  | write                  |
| 3 | \-wx  | execute + write        |
| 4 | r--   | read                   |
| 5 | r-x   | read + execute         |
| 6 | rw-   | read + write           |
| 7 | rwx   | read + write + execute |

| **Command** | **Description** |
|---|---|
| `id`      | Show the current user ID, group ID, and group memberships.  |
| `newgrp groupname`    | Temporarily switch to another primary group.    |
| `groups`              | Display all groups the current user belongs to. |
| `usermod -g groupname username` | Permanently change a user's primary group (requires admin privileges). |
| `chgrp groupname file` or `chgrp -R groupname file` | Change the group ownership of a file or directory. |
| `stat /tmp/file` | Display detailed file information, including owner, group, and permissions. |
| `chown user /path/to/file` | Change the owner of a file or directory. |
| `chown user:group path/to/file` | Change both owner and group. |
| `chown :group /path/to/file` | Change only the group. |
| `chmod u+x file` | Add execute permission for the owner. |
| `chmod g+rw file` | Add read and write permissions for the group. |
| `chmod o-w file` | Remove write permission for others. |
| `chmod u=rx g=rx: o=r file` | Set explicit permissions using symbolic mode. |
| `chmod 774 file` | Set permissions using numeric mode. |
| `umask 002` | Modify default permission mask for new files and directories. |

# Special Permissions

## Setuid
When set on an executable, the program runs with the file owner's privileges, not the user's.
Lowercase `s` -> setuid + execute bit are set
Uppercase `S` -> setuid is set but execute bit is not set

| **Command** | **Description** |
|---|---|
| chmod u+s file    | Add setuid                            |
| chmod u-s file    | Remove setuid                         |
| chmod 4775 file   | Add setuid numerically (4000 + 775)   |
| chmod 0775 file   | Remove setuid numerically             |


## Setgid
Setgid behaves differently depending on whether it is applied to a file or a directory:
- On files: the program runs with the group owner's permissions.
- On directories: new files inherit the directory’s group.

| **Command** | **Description** |
|---|---|
| ls -ld directory          | View directory permissions            |
| chmod g+s file \| directory  | Add setgid                            |
| chmod g-s file \| directory  | Remove setgid                         |
| chmod 2775 file \| directory | Add setgid numerically (2000 + 775)   |
| chmod 0775 file \| directory | Remove setgid numerically             |


### Sticky Bit
Used on shared directories (e.g., /tmp) to prevent users from deleting files they do not own.
| **Command** | **Description** |
|---|---|
| chmod o+t directory  | Add sticky bit                             |
| chmod o-t directory  | Remove sticky bit                          |
| chmod 1775 directory | Add sticky bit numerically (1000 + 775)    |
| chmod 0775 directory | Remove sticky bit numerically              |