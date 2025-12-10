# Basic Scripting

A *shell script* is a file of executable commands that has been stored in a text file. Shell scripts have access to all the commands of the shell, including logic.

Complicated scripts will indicate a particular shell by specifying the absolute path to the interpreter as the first line, prefixed by #! (hash/bang, shebang, crunchbang).

```
#!/bin/sh
echo "Hello, World!"
```

```
#!/bin/bash
echo "Hello, World!"
```

If the script is invoked directly as an argument to an interpreter, such as **sh script** or **bash script**, the given shell will be used no matter what’s in the shebang line.

**Text editors:** nano, vi, vim (vi improved).

### Terminology:
- **Variables:** Store values (such as text, numbers, or command output) for use within the script.  
- **Conditionals:** Allow the script to make decisions and execute different commands based on tests or comparisons.  
- **Loops:** Repeat a block of commands multiple times, either over a list of items or until a condition is met.  

---

## Variables

```
#!/bin/bash
ANIMAL=”penguin”
SOMETHING=$ANIMAL
echo “My favorite animal is a $SOMETHING”
```

It is important that there are no spaces between the name of the variable, the equals sign, and the item to be assigned to the variable.

Capitalizing the name of the variable is not necessary but it is useful convention to separate variables from commands to be executed.

```
#!/bin/bash
CURRENT_DIRECTORY=´pwd´
Echo “You are in $CURRENT_DIRECTORY”
```

This pattern is often used to process text. You might take text from one variable or an input file and pass it through another command like **sed** or **awk** to extract certain parts and keep the result in a variable. 

- **sed:** stream editor, often used for substitutions or deletions.
- **awk:** pattern scanning and processing language, useful for field-based text manipulation.

It is possible to get input from the user of your script and assign it to a variable through the **read** command:

```
#!/bin/bash
echo -n "What is your name? "
read NAME
echo "Hello $NAME!"
```

You can set the exit code of your own script with the exit command:
```
#!/bin/bash
# Something bad happened!
exit 1
```

Running `echo $?` returns the exit status of the last command. An exit code of 0 means the command executed successfully, while a code greater than 0 indicates an error.

---

## Conditionals

### Structure:
```
if somecommand; then
  # do this if somecommand has an exit code of 0
fi
```

### Conditional Operators

#### Numeric Comparisons
* -eq =  equal 
* -ne =  not equal 
* -gt  =  greater than 
* -lt   =  less than 
* -ge =  greater or equal 
* -le  =  less or equal 

#### String Comparisons
* =   >> equal
* !=   >> not equal
* -z   >> string is empty
* -n   >> string is not empty

### Example:
```
#!/bin/bash
#conditional example
if grep -q root /etc/passwd; then
  echo root is in the password file
else
  echo root is missing from the password file
fi
```

The test command gives you easy access to comparison and file test operators.

| **Command** | **Description** |
|---|---|
| `test -f /dev/ttys0`| 0 if the file exists |
| `test ! -f /dev/ttys0` | 0 if the file doesn’t exist |
| `test -d /temp` | 0 if the directory exists |
| `test -x $(which ls)` | Check if the `ls` command exists and is executable by the current user. |
| `test 1 -eq 1` | 0 if the numeric comparison succeeds |
| `test 1 -ne 1` | Test for numeric inequality |
| `test “a” = “a”` | 0 if the string comparison succeeds |
| `test 1 -eq 1 -o 2 -eq 2` | -o is OR: either can be the same |
| `test 1 -eq 1 -a 2 -eq 2` | -a is AND: both must be the same |

The test statement is automatically called when you place its arguments within square brackets [ ] surrounded by spaces: `if [ $age -lt 16 ]`

There must be spaces around the square brackets. 
`[$age -lt 16]` would fail, but `[ $age -lt 16 ]` would work.

Often the `seq` command is used in conjunction with the for statement. The `seq` command generates a sequence of numbers, which can then be iterated over in a loop.

| **Command** | **Description** | **Example Output** |
|---|---|---|
| `seq 5` | Generate numbers from 1 to 5. | `1 2 3 4 5` |
| `seq 1 5` | Generate numbers from 1 to 5 (explicit start/end) | `1 2 3 4 5` |
| `seq 2 6` | Generate numbers from 2 to 6. | `2 3 4 5 6` |
| `seq 1 2 10` | Generate numbers from 1 to 10 with step 2. | `1 3 5 7 9` |
| `seq -w 1 5` | Pad numbers with leading zeros (equal width). | `01 02 03 04 05` |
| `seq -s , 1 5` | Use a custom separator (comma). | `1,2,3,4,5` |
| `seq 10 -2 0` | Generate numbers from 10 down to 0 with step -2. | `10 8 6 4 2 0` |


---

## Loops

### FOR Loops
This loop is used when you have a finite collection over which you want to iterate, such as a list of files, or a list of server names.

```
#!/bin/bash
# for loop example

SERVERS=”servera serverb serverc”

for S in $SERVERS; do
   echo “Doing something to $S”
done
```

### WHILE Loops
This loop operates on a list of unknown sizes. 
Its job is to keep running and on each iteration perform a test to see if it should run another time.

```
#!/bin/bash
# while loop example

i=0
while [ $i -lt 10 ]; do
   echo $i
   i=$ ( ( $i + 1) )
done

echo “Done counting”
```

Finding the length of a string
```
length=${#variable}
```

The **let** command can be used to perform basic operations directly.
* Increment operation:
```
let number++
```
  
* Decrement operation:
```
let number--
```

* Shorthands:
```
let number+=5
let number-=5
```


The **bc** command is an advanced utility for mathematical operations.
```
echo "$number1 * 1.5" | bc
echo "scale=2;4/5" | bc
echo "obase=2;$number" | bc
```

## Arrays
```
myArray=(1 2 3 4 5)
```
Values will be stored in consecutive locations starting from index 0.

Index-value pair:
```
myArray[0]="test"
```

Print the contents of an array
```
echo ${myArray[0]}
echo ${myArray[$index]}
```

Print all of the values in an array as a list:
echo ${myArray[*]}

Print the length of an array
echo ${#myArray[*]}