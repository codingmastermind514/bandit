# OverTheWire Bandit 3
This is the solution to OverTheWire's Bandit Level 3. 

### Solution

The solution command is:
```bash
cat ./-
``` 

### Explanation
First, we have to access the game via `ssh`. We do not change from the bandit1 shell, as we need a password to access the next level, which is stored in the bandit1 home directory. 

As such, we have the same credentials as last time: 

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

From there, this level asks: 

> The password for the next level is stored in a file called `--spaces in this filename--`located in the home directory

First, we list the contents of the directory using `ls`. This showed: 

<img src = "./img/bandit4.png"> 

From there, we decided to open and read the file with `cat readme` This command works as such:

```bash
    cat ./"--spaces in this filename"
    "The password you are looking for is: password hidden for ethics purposes "
``` 


Giving us the password to SSH into level 2.


From here, we need to exit the Level 1 SSH connection and SSH into the Level 2 connection, where we paste the password.