# the root

**Flag:** pwn.college{4vmc_7fmPYa5VX8ZVE7giefvkMJ.QX4cTO0wiNxEzNzEzW}


```
#!/bin/bash

/pwn

flag generated
```

## What I learned

*the linux filesystem is a tree, and it has a root (/), which is a directory.
*a program can be invoked by giving its path on the command line.
*type of path that starts with the root directory is called ABSOLUTE PATH.

# program and absolute paths

**Flag:** pwn.college{ogZXR1TJweKZh3BWhnYvZnn9D4h.QX1QTN0wiNxEzNzEzW}


```
#!/bin/bash

/challenge/run
```

# position thy self

### Put challenge description here

**Flag:** pwn.college{0TPSh1d7Kp8gKqsfv1yxvH0MbiK.QX2QTN0wiNxEzNzEzW}


```
#!/bin/bash

/challenge/run
cd /
/challenge/run
```

## What I learned

* cd is the command to change directories
* cd [path of the directory] will change directory to the directory that path is pointing to
* the current working directory while using pwn.college is the bash shell.

# position elsewhere

**Flag:** pwn.college{kA3qZlUKQ4qVI5KuJnPyKlBQuGC.QX3QTN0wiNxEzNzEzW}

```
#!/bin/bash

/challenge/run
cd /proc/138

```

# position yet elsewhere

**Flag:** pwn.college{w5h6zoewgISD3QcIlQvEJHZYoKa.QX4QTN0wiNxEzNzEzW}

# implicit relative paths, from /

**Flag:** pwn.college{Msb9oAuFNHGwS-1ALNMNyQwvYCK.QX5QTN0wiNxEzNzEzW}


```
#!/bin/bash

cd /
challenge/run
```

## What I learned

* relative paths are paths that does not start at root directory.
* pwd (print working directory) is the command used to display the name of the current working directory.
* a relative path is interpreted relative to the current working directoy
* .. in a file path refers to the parent directory
  .ie. if i wanna access the file located at /tmp/a/b/my_file,
  and if my cwd is /tmp/a/b/c, then,
  a relative path to this file is ../my_file

# explicit relative paths, from /

**Flag:** pwn.college{Ehv11mMLNKzwSx1PWDUu_uyHXaL.QXwUTN0wiNxEzNzEzW}


```
#!/bin/bash

cd /
./challenge/run
```

## What I learned

* . refers to the same directory as the current working directory
  .ie. the relative paths /challenge , /challenge/. , /challenge/./././././././././ , /./././challenge/././ are all the same
  
# implicit relative path

**Flag:** pwn.college{UsuQq7FSqhzoHWNm29f4QL2YMKC.QXxUTN0wiNxEzNzEzW}


```
#!/bin/bash

cd /challenge
./run
```

# home sweet home

**Flag:** pwn.college{MsIs74NqJFcj2F00KsTSy68wEuK.QXzMDO0wiNxEzNzEzW}

```
#!/bin/bash

/challenge/run ~/~
```

## What I learned

* every user has a home directory in the file system
* usually, by default, the shell session starts in the home directory
* ~ in the prompt is shorthand for the cwd
* expansion of ~ is an absolute path
* only the initial ~ will be expanded to the home directory
  .ie. ~/~ would be expanded to /home/hacker/~ and NOT /home/hacker/home/hacker
* if we give command as "cd", the default destination will be to the home directory
