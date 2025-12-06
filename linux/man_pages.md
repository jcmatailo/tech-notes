## Man (Manual) Pages

| **Key & Command** | **Description** |
| --- | --- |
| **H** or **h** | Display the help |
| **Q** or **q** | Quit the help or manual page |
| **Spacebar** or **f** or **PageDown** | Move a screen forward |
| **b** or **PageUp** | Move a screen backward |
| **Enter** or **down arrow** | Move down one line |
| **Up arrow** | Move up one line |
| **/text** | Start searching forward |
| **?text** | Start searching backward |
| **n** | Move to next that matches search |
| **N** | Move to previous matching text |


## Structure of a Man Page:
Each man page is divided into sections that explain different aspects of a command:
* Name: Command name and a brief summary.
* Synopsis: Syntax and usage examples.
* Description: Detailed explanation of the command’s functionality.
* Options: List of flags and parameters with descriptions.
* Files: Related files and their roles.
* Author: Creator of the man page (sometimes includes contact info).
* Reporting Bugs: Instructions for submitting bug reports.
* Copyright: Licensing and copyright details.
* See Also: Related commands or documentation.


## Man Pages Sections (Categories):
* General Commands – User-level commands
* System Calls – Kernel-level functions
* Library Calls – Functions from system libraries
* Special Files – Device files and drivers
- File Formats and Conventions – Configuration files and syntax
- Games – Game-related commands
- Miscellaneous – Macro packages, conventions, etc.
- System Administration Commands – Admin tools 
- Kernel Routines – Internal kernel documentation

### Commands for Documentation & Search
| **Key & Command** | **Description** |
| --- | --- |
| `man <command>` | Display the manual page for a command | 
| `man -s <section> <command>` | View the man page from a specific section | 
| `man -a <command>` | Show all available man pages for a command | 
| `man -f <command>` or `whatis <command>` | Show a brief description of the command | 
| `man -k <keyword>` or `apropos <keyword>` | Search man pages by keyword | 
| `man -w <command>` or `whereis <command>` | Show location of man page or binary | 
| `which <command>` | Show full path of an executable | 
| `locate <file>` | Search for files using the locate database | 
| `locate -c <file>` | Count how many matches exist | 
| `locate -c -b <file>` | Count matches where the basename matches | 
| `locate -b \filename` | Match exact filename only | 
| `updatedb` | Update the locate database manually | 


## Info Documentation
Unlike man pages, info documents are more tutorial-style and hierarchical.
| **Key & Command** | **Description** |
| --- | --- |
| `info <command>` | Open the info documentation for a command | 
| `Shift + H` | Display movement commands within info | 
| `l` | Return to the top-level directory of the info system | 


## Help Option
| **Command** | **Description** |
| --- | --- |
| `<command> --help` | Show usage and options for a command | 


### Additional System Documentation
These directories contain supplementary documentation, changelogs, and examples:
* /usr/share/doc
* /usr/doc