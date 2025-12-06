# Manage files and directories

## Directories Structure
| **Directory** | **Description** |
|---|---|
| /bin 		| Essential binaries for basic system commands |
| /boot 	| Files required for system booting |
| /dev 		| Device files (disks, ports, etc.) |
| /etc 		| System configuration files |
| /home 	| Personal directories for users |
| /lib 		| Shared libraries for binaries in /bin and /sbin |
| /media	| Mount point for removable media |
| /mnt		| Temporary mount point for file systems |
| /opt		| Optional add-on software packages |
| /proc		| Virtual filesystem providing kernel and process information |
| /root		| Home directory for the root user |
| /run		| Runtime data for system processes |
| /sbin		| System binaries used by the administrator |
| /srv		| Data for services provided by the system |
| /sys		| Virtual info about devices and the kernel |
| /tmp		| Temporary files, often deleted on reboot |
| /usr		| Unix system resources (binaries, libraries, docs) |
| /var		| Frequently changing files (logs, caches, etc.) |


## Paths

###  Absolute Paths
Absolute paths specify the exact location of a file or directory in the filesystem.
It always starts at the root directory, and therefore it always begins with the / character.

### Relative Paths
Relative paths start from the current directory. 
A relative path gives directions to a file relative to the current location in the filesystem.
They do not start with the / character. Instead, they start with the name of a directory


## File Type
| **Symbol** | **File Type** | **Description** | 
|---|---|---|
| d | directory | A file used to store other files. |
| - | regular file | Includes readable files, images, binaries, and compressed files. |
| l | symbolic link | Points to another file. |
| s | socket | Enables communication between processes. |
| p | pipe   | Facilitates communication between processes. |
| b | block device | Used to communicate with hardware. 	|
| c | character device | Also used to communicate with hardware.  |


| **Command** | **Description** |
| --- | --- |
| `pwd` | Display path of the current directory. |
| `cd /` | Move to the root directory  |
| `cd ..` | Previous directory	 |
| `cd ~` | Move to the home directory | 
| `cd ~user` | Move to another user's  home directory |
| `ls` | Displays the files inside a directory. |
| `ls -a`	| Listing w/ hidden files |
| `ls -lr`	| Long display and reverse listing |
| `ls -lh`	| Human-readable sizes |
| `ls -d`	| Listing directories; it refers to the current directory, and not the contents within it.  |
| `ls –d /etc/[abc]*` | Execute the following command to display all of the files in the /etc directory that begin with letters a, b, or c. |
| `ls -R /path/` | Recursive Listing |
| `ls -S /path/` | Sort a listing (By size, largest to smallest) |
| `ls -rS /path/` | Reverse a sort listing (By size, smallest to largest ) |
| `ls -t` | Sorts files based on the time |
| `tree` | Directories structure |

## ASCII
The character standard used for Linux is the UTF-8 standard which is based on the ASCII. For more information, execute `man -s 7 ascii`.
| **Command** | **Description** |
| --- | --- |
| `ascii` | Display ASCII character table |

## Globbing
Glob characters are often referred to as wild cards. These are symbol characters that have special meaning to the shell.

**Asterisk (\*)** character is used to represent zero or more of any character in a filename.

**The question mark (?)** represents any single character. Each question mark character matches exactly one character, no more and no less.

**The brackets [ ]** characters are used to match a single character by representing a range of characters that are possible match characters.

**The exclamation point (!)** character is used in conjunction with the brackets to negate a range.


## Files and Directories
| **Command** | **Description** |
| --- | --- |
| `touch <file>` | Creating files. |
| `mkdir <directory>`	| Creating directories. |
| `file -i <file>` | Determine file type. |
| `stat <file>` | Display file or file system status. |


## Copying Files
| **Command** | **Description** |
| --- | --- |
| `cp <source> <destination>`	| This command is used to copy files. |
| `cp -a <dir1/> <dir2/>` | Copy directories. Copies everything, preserving structure and metadata |
| `cp -v <source> <destination>` | Verbose mode of copy command. |
| `cp -i <source> <destination>` | Interactive mode of copy command. |
| `cp -n <source> <destination>` | No clobber, no overwrite mode. |
| `cp -r <source> <destination>` | Copying directories. Copies contents, but may lose metadata. |


## Moving Files
| **Command** | **Description** |
| --- | --- |
| `mv -v -i -n <source> <destination>` | Move Files. (-v) Verbose: show what’s being moved. (-i) Interactive: prompt before overwrite. (-n) No-clobber: never overwrite existing files. |
| `mv <fileNewName> <fileOldName>` | Rename Files. |


## Removing Files
| **Command** | **Description** |
| --- | --- |
| `rm -i <file>` | Remove files interactively. |
| `rm -f <file>` | Force to remove the file. |
| `rmdir -i <directory>` | Remove directory interactively. |
| `rm -rf <dir>` | Removing empty directories. |