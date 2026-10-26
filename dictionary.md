# Linux Command Dictionary
This file contains a "dictionary" of Linux commands that you may use to solve the `bandit` levels, plus extras! 


## Basic Commands
### `ssh`
`ssh` stands for **secure shell**. This command allows us to run commands in another device's shell through an encrypted channel. 

<p align="center">
<code>
ssh user@host -p 1234
</code>
</p>

**Note**: The port is usually a four-digit number. It varies based on the login and service. Be sure to use the right one.

`ssh` has the following options:

| Option | Meaning | 
| ---- | ---- | 
| -p | The port that you are connecting to | 
| -4 | Forces the use of IPv4 addresses | 
| -6 | Forces the use of IPv6 addresses |

&nbsp;

---

&nbsp;

### `cd`
`cd` indexes into a specific directory. 
<p align="center">
<code>
cd path/to/directory
</code>
</p>

Here are some examples:

| Example | Meaning | 
| ---- | ---- | 
| `cd ..` | Indexes into the parent directory | 
| `cd` | Indexes into the home directory | 
| `cd /` | Takes you to the absolute root of the computer |
| `cd ./` | Indexes into the current directory |
| `cd -` | Takes you back to the previous folder you came from |

&nbsp;

---

&nbsp;


### `ls`
`ls`, which stands for list, **lists** the contents of a directory

<p align="center">
<code>
ls -la /directory
</code>
</p>

It has the following options:

| Option | Meaning | 
| ---- | ---- | 
| -a | Shows all files, including hidden files. ✪ | 
| -l | Long format; perms, owner, size, date |
| -h | With -l, prints sizes as K, M, G ✪✪ |
| -R | Recurse into every subdirectory |

> ✪ Hidden files are ones whose name starts with a dot, for example `.bashrc`

> ✪ ✪ K means kilobytes, M means megabytes, and G means gigabytes

&nbsp;

---

&nbsp;

## Reading Files
### `cat`
`cat` takes one or more files and pours out the content in order as a single stream. 
<p align="center">
<code>
cat -n a.txt b.txt
</code>
</p>

It has the following options:

| Option | Meaning | 
| ---- | ---- | 
| -n | Numbers the lines | 
| -s | Squeezes the blank lines into one | 
| -T | Shows all tab characters as ^I |
| -b | Numbers only the non-blank lines |

&nbsp;

---

&nbsp;

### `strings`
`strings` reads a file byte by byte and prints every run pf 4 or more printable characters in a row. It works on *any* file, even ones that `cat` can't show. Sometimes unreadable files contain messages, file paths, URLs and maybe passwords someone forgot to remove. It's safer than `cat` because it never runs the file.
<p align="center">
<code>
strings -n 8 mystery.bin
</code>
</p>

It has the following options:

| Option | Meaning | 
| ---- | ---- | 
| -n 8 | Only shows runs of 8 or more characters | 
| -t d | Shows where each string starts in the file | 
| -e l | Looks or 16-bit text (common in Windows programs) |

&nbsp;

---

&nbsp;

## File Information
### `file`
`file` displays information about a file by searching for signatures in the file that indicate its type, regardless of its name or file extension. They can be useful for identifying whether a file is human-readable or not. 

<p align="center">
<code>
file -b mysteryfile
</code>
</p>

It has the following options:

| Option | Meaning | 
| ---- | ---- | 
| -b | Only shows the file type | 
| -i | Outputs the MIME type |
| -z | Looks inside compressed files |
| -s | Forces `file` to read things it would usually ignore. |

&nbsp;

---

&nbsp;

### `du`

`du` estimates how much space files take up on your computer.

<p align="center">
<code>
du -ab file.txt
</code>
</p>

It has the following options:

| Option | Meaning | 
| ---- | ---- | 
| -b | Shows the size in bytes | 
| -a | Estimates the size for all files |
| -c | Produces a grand total |
| -h | Prints sizes in a human-readable format |

&nbsp;

---

&nbsp;


## Searching and Sorting
### `grep`

`grep` searches for content within files. It then prints out the matching lines.

<p align="center">
<code>
grep -i 'hello world' menu.h main.c
</code>
</p>

It has the following options:

| Option | Meaning | 
| ---- | ---- | 
| -i | Ignores the case | 
| -w | Matches whole words |
| -x | Matches whole lines |
| -v | Displays non-matching lines |

&nbsp;

---

&nbsp;

### `find`

`find` searches for file names and specifications such as the user and group who own the file as well as the file size.

<p align="center">
<code>
find / example.txt
</code>
</p>

It has the following options:

| Option | Meaning | 
| ---- | ---- | 
| -E | Searches using `regex` ✪ | 
| -f | Adds the path provided to the list of paths that need to be recursed into|
| -x | Prevents `find` recursing into a directory with a device number different from the original |

> ✪ Regex (a.k.a regular expressions) are basically patterns in text, with special characters that indicate special things, such as `*` which means **all**.

&nbsp;

---

&nbsp;

### `sort`
The `sort` command **sorts** the contents of the file in alphabetical order. 

<p align="center">
<code>
sort file.txt
</code>
</p>

It has the following options:

| Option | Meaning | 
| ---- | ---- | 
| -f | Ignores the case | 
| -u | Only displays unique items |
| -n | Sorts based on numeric value |
| -R | Random sort|


&nbsp;

---

&nbsp;


### `uniq`
The `uniq` command smashes all duplicate adjacent lines into one. For example, 

```
hello
hello
hello
hi
```

becomes 

```
hello
hi
```

It is often used in conjunction with `sort` because the duplicate lines must be adjacent to collapse them. When you sort something, the duplicate lines will be next to each other, and a **pipeline** is used in between the commands.

<p align="center">
<code>
sort file.txt | uniq 
</code>
</p>

It has the following options:

| Option | Meaning | 
| ---- | ---- | 
| -f | Ignores the case | 
| -u | Only displays unique items |
| -n | Sorts based on numeric value |
| -R | Random sort|

&nbsp;

---

&nbsp;

## Theory
### `pipelines`

In the previous subsection, a `|` character was used to separate the two commands. This is known as a **pipeline**. It makes the *output* of the first command the *input* to the second, and so on if there are more than two comands strung together. 

**For example,**

<p align="center">
<code>
ls /sandbox
</code>
</p>

returns `people.txt`, and the full command is 

<p align="center">
<code>
ls /sandbox | cat
</code>
</p>

the end result would be the contents of `people.txt`.

&nbsp;

---

&nbsp;

### `Redirection`

`Redirection` sends output, input or errors of commands to different locations. The three streams it works on are `0, stdin` (all input), `1, stdout` (all output) and `2, stderr` (all errors). 

Here's what each symbol for redirection means:

| Symbol | Meaning | 
| ---- | ---- | 
| >> | Appends output to the end of a file, new or preexisting | 
| > | Sends output to a file, overwriting its contents | 
| < | Sends the contents of a file to the input of a command | 
| 2>> | Appends errors to the end of a file, new or preexisting. | 
| 2> | Sends errors to a file, overwriting its contents | 
| &> | Sends errors and output to a file, overwriting its contents | 
| &>> | Appends errors and output to the end of a file, new or preexisting. | 

To use these, simply put them at the ends of commands:

<p align="center">
<code>
cat passwords.txt >> confidental.txt
</code>
</p>

This would redirect the output of the first command to `confidential.txt`, perhaps creating the new file or appending to the end of a preexisting one.


&nbsp;

---

&nbsp;