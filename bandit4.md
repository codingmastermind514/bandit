# OverTheWire Bandit 4
This is the solution to OverTheWire's Bandit Level 3→4. 

## Solution

The solution command is:
```bash
cd inhere ; ls -a ; cat ...Hiding-From-You
``` 
## Instructions
This level asks:
> The password for the next level is stored in a hidden file in the inhere directory.

## Background
See <a href='./dictionary'>`dictionary.md`</a> for a full list of commands.

**Previous Commands:** `cat`

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



## Explanation
First, we have to access the game via `ssh`.

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

Then, let's check out the available directories and files with `ls`. This shows us a directory called `inhere`, which we can `cd` into. 

<img src="./img/bandit4-1.png">

Then, we `cd` in and list the contents of the directory `inhere` using `ls -a`, as we need to view a hidden file. This showed: 

<img src="./img/bandit4-4.png">

From there, we decided to open and read the file with `cat ...Hiding-From-You`. 

> NOTES:
> 
> The `-a` option on `ls` indicates that hidden files ("a" for "all") must also be shown.

<img src="./img/bandit4-2.png">


Giving us the password to SSH into level 4.

<img src="./img/bandit4-3.png">

From here, we need to exit the Level 3 SSH connection and SSH into the Level 4 connection, where we paste the password.

<h2 style="text-align:center;"> ​✰ Navigation ​✰ </h2>
<table style="width: 100%;">
<tr>
<td style="text-align:left;"><a href='./bandit3'>
​​✰🇵​​🇷​​🇪​​🇻​​​✰</a></td>
<td style="text-align:center;"><a href='./index'>​✰​🇭​​🇴​​🇲​​🇪​✰​​</a></td>
<td style="text-align:right;"><a href='./bandit5'>​✰​🇳​​🇪​​🇽​​🇹​✰​​</a></td>
</tr>

</table>