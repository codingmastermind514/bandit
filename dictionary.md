# Linux Command Dictionary
Short Description Here 

## Searching 
Short Description Here 


### `ssh`
`ssh` stands for **secure shell**. This command allows us to run commands in another device's shell through an encrypted channel. 

<p align="center">
<code>
ssh user@host -p 1234
</code>
</p>

**Note**: The port is usually a four-digit number. It varies based on the login. Be sure to use your own. 


`ssh` has the following options:

| Option | Meaning | 
| ---- | ---- | 
| -p | The port that you are connecting to | 
| -4 | Forces the use of IPv4 addresses | 
| -6 | Forces the use of IPv6 addresses |


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

### `sort`
The `sort` command **sorts** the contents of the file in alphabetical order. 

The format is as follows: 

<p align="center">
<code>
sort example.txt
</code>
</p>

### `uniq`
The `uniq` command smashes all duplicate adjacent lines into one. For example, 

```
hello
hello 
hello 
hi 
```

gets collapsed into
```
hello
hi
```
The format is as follows
<p align="center">
<code>
uniq -u example.txt
</code>
</p>

> **Note:** for full list of options such as `-u` see `dictionary.md`

### `Pipelines`

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
