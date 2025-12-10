# Vi Commands

| **Command** | **Description** |
|---|---|
| h | Move cursor left  |
| l | Move cursor right |
| j | Move cursor down  |
| k | Move cursor up    |
| w | Move cursor to beginning of next word     |
| e | Move cursor to end of current word        |
| b | Move cursor to beginning of previous word |
| 0 | Move cursor to beginning of current line  |
| $ | Move cursor to end of current line        |
| nG  | Jump to line *n*                        |
| G   | Jump to last line                       |
| dw  | Delete word                             |
| ndw | Delete *n* words                        |
| x   | Delete character under cursor           |
| nx  | Delete *n* characters                   | 
| dd  | Delete current line                     |
| ndd | Delete *n* lines starting from current  |
| D   | Delete from cursor to end of line       |
| yw  | Yank (copy) current word                |
| yy  | Yank (copy) current line                |
| p   | Paste after cursor                      |
| P   | Paste before cursor                     |
| J   | Join current line with next             |
| nJ  | Join *n* lines starting from current    |
| cw  | Change (replace) word                   |
| i, I, a, A,   | Enter insert mode             |
| o        | Open new line below current        |
| O        | Open new line above current        |
| u        | Undo last change                   |
| Ctrl+r   | Redo last undone change               |
| ~        | Toggle case of character under cursor |
| guw      | Change word to lowercase              |
| gUw      | Change word to uppercase              |
| :w       | Save file                             |
| :x       | Save and exit                         |
| :wq      | Write and quit                            |
| :wq!     | Force write and quit (even if read-only)  |
| ZZ       | Save and quit (no colon needed)           |
| :q!      | Quit without saving                       |
| :e!      | Reload file, discarding changes           |
| :w!      | Force write to read-only file             |
| /word    | Search forward for "word"                 |
| ?word    | Search backward for "word"                |
| n        | Repeat search in same direction           |
| N        | Repeat search in opposite direction       |
| :%s/text//g | Search and delete all occurrences of "text" |