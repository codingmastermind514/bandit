# OverTheWire Bandit 5
This is the solution to OverTheWire's Bandit Level 4→5. 

## Solution

The solution command is:

```bash
cd inhere ; ls -a ; file ./* ; cat ./-file07
``` 
## Instructions
This level asks:
> The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.


## Necessary commands


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


## Explanation
First, we have to access the game via `ssh`. We do not change from the bandit4 shell, as we need a password to access the next level, which is stored in the bandit4 home directory. 

As such, we have the same credentials as last time: 

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

First, we need to `cd` into the `inhere` directory and view the list of files. 

