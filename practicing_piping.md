# redirecting output

### redirecting output to a particular file

**Flag:** pwn.college{08P-_Yilh759AqYufeQWqDJ3J3O.QX0YTN0wiNxEzNzEzW}

printing "PWN" , 
but redirecting the output to a file called "COLLEGE"

```
#!/bin/bash

echo PWN > COLLEGE

flag generated
```

## What I learned

redirection of output to a file is possible using ">"

## References

# redirecting more output

### redirecting output of any command to a file

**Flag:** pwn.college{kbJzYvUXNFbdr_mMVnDkTFz30F2.QX1YTN0wiNxEzNzEzW}

type command /challenge/run 
redirect output of the command to the file "myflag"
open the file to generate flag
```
#!/bin/bash

/challenge/run > myflag
cat myflag

flag generated
```

## What I learned

redirection of output of any command to any file can be done using ">"

## References

# appending output

### redirection of output of commands into the same file

**Flag:** pwn.college{w3-y3WMU11w_Yonlz6_dcFbtL9H.QX3ATO0wiNxEzNzEzW}

type command "/challenge/run" , 
redirection of output is done to a file in truncated mode,
this ensures both parts of flag to be redirected to said file,
open said file to generate flag
```
#!/bin/bash

/challenge/run >> /home/hacker/the-flag
cat /home/hacker/the-flag

flag generated
```

## What I learned

">" redirects output to individual files
everytime we > , a new output file is created and the old contents are OVERWRITTEN
">>" is used for appending of outputs into the same file

## References

# redirecting errors

### redirecting errors of command to a particular file

**Flag:** pwn.college{M2-MLusdUO_6tG65tz1ZmTlcDFQ.QX3YTN0wiNxEzNzEzW}

redirecting output and error of a challenge command to 2 separate files,
opening the file to which output was redirected to generate flag
```
#!/bin/bash

/challenge/run 1> myflag 2> instructions
cat myflag

flag generated
```

## What I learned

FILE DESCRIPTOR (FD) numbers represent a communication channel in Linux
FD 0 : standard input
FD 1 : standard output
FD 2 : standard error
we can redirect multiple file descriptors at the same time

## References

# redirecting input

### redirecting input to programs

**Flag:** pwn.college{Ib70PnOpLoBHYkPtpKiosLbUBPS.QXwcTN0wiNxEzNzEzW}

redirecting output of a command to a file,
redirecting input(which is now the contecnt of the file to which output is redirected) to a command
generate flag
```
#!/bin/bash

echo COLLEGE 1> PWN
/challenge/run 0< PWN

flag generated
```

## What I learned

input can be redirected INTO  a program
using "<" and "0<" both redirects input to a command

## References

# grepping stored results

### Put challenge description here

**Flag:** pwn.college{EbkA03n-rXyT0UBFCOJKrEqg78S.QX4EDO0wiNxEzNzEzW}

redirecting output to a file, grepping that file for the flag
```
#!/bin/bash

/challenge/run 1> /tmp/data.txt
grep pwn.college /tmp/data.txt

flag generated
```

## What I learned

output redirection to a file done use 1>

## References

# grepping live output

### usage of pipe (|) operator

**Flag:** pwn.college{g4nS4mlQJXyDJaU4HsPlvf3tBLs.QX5EDO0wiNxEzNzEzW}

runa command to generate multiple lines of text 
multiple lines of text is the output
that is to the lest of pipe operator
grep for flag to the rhs of |

```
#!/bin/bash

/challenge/run | grep pwn.college

flag generated
```

## What I learned

redirection into a file can be avoided using |
stdout to the cmd at lhs of | will be stdin of cmd to rhs of |

## References

# grepping errors

### Put challenge description here

**Flag:** pwn.college{8kHDuE3WfLPccfJtpMRQa2T_kGW.QX1ATO0wiNxEzNzEzW}

run a command to run multiple lines of text which is stderr,
redirect stderr to stdout using ">&",
this is the output which is used as input to rhs of pipe operator
```
#!/bin/bash

/challenge/run 2>&1 | grep pwn.college

flag generated
```

## What I learned

a file descriptor can be redirected to another file descriptor using ">&"

## References

# filtering with grep -v

### Put challenge description here

**Flag:** pwn.college{Ux17aRp7pyIKqOXVLQF7iLEzGiy.0FOxEzNxwiNxEzNzEzW}

run a challenge which generates multiple flags
use pipe operator to make sure the output of this(generation of multiple flags) is the
input to grep -v DECOY which filters out all the decoy flags and gives the real flag
```
#!/bin/bash

/challenge/run grep -v DECOY

flag generated
```

## What I learned

we can use grep -v "keyword" to filter out all the documents/files containing that keyword
and to generate all the files that does NOT have that keyword

## References

# duplicating piped data with tee

### a way to show the output that we're piping to be the input of what's on the rhs of |

**Flag:** pwn.college{w7Uvrw7Gd4cGmOwuuaJa3rUOlmI.QXxITO0wiNxEzNzEzW}

use pipe operator to make stdout of lhs of | as stdin of rhs of | ,
use "tee" to copy output of lhs of | into a file,
cat that file to see output and find out what's needed to generate flag

```
#!/bin/bash

/challenge/pwn | tee pwn | /challenge/college
cat pwn
/challenge/pwn --secret w7Uvrw7G |  /challenge/college

flag generated
```

## What I learned

we can use "tee" to store stdout of lhs of | to a file

## References

# process substitution for input

### 

**Flag:** pwn.college{YM2rsXJDONR7hb_BqHeqOh7sfgU.0lNwMDOxwiNxEzNzEzW}


```
diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)

flag generated

pwn.college{helloworld}
```

## What I learned
*input and output of programs can be hooked to arguments of commands using "process substitution"
*stdout of a command is hooked to a "file" that is not real (called named pipe)
using <(command).

## References

# writing to multiple programs

### Put challenge description here

**Flag:** pwn.college{UqXcrIsO_d0QMZzM5pWYS_EcUw9.QXwgDN1wiNxEzNzEzW}

explain your solve and how you got to it, explain any incorrect tangents you went on while solving.

to put code snippets, put three backticks and for images and all other stuff you wish to put here, refer to the documentation given to you.

don't style it too much, your solve should be readable and understandable by you so that when you have doubts, you refer to your own writeups, instead of gpt.

```
#!/bin/bash

/challenge/hack | tee >(/challenge/the) >(/challenge/planet)

flage generated
```

## What I learned

explain what you learned

## References

# split-piping stderr and stdout

### Put challenge description here

**Flag:** pwn.college{o6YyVeeOPEttK6q0EiAXoGDf1vs.QXxQDM2wiNxEzNzEzW}

explain your solve and how you got to it, explain any incorrect tangents you went on while solving.

to put code snippets, put three backticks and for images and all other stuff you wish to put here, refer to the documentation given to you.

don't style it too much, your solve should be readable and understandable by you so that when you have doubts, you refer to your own writeups, instead of gpt.

```
#!/bin/bash

/challenge/hack 1> >(/challenge/planet) 2> >(/challenge/the)
```

## What I learned

explain what you learned

## References

# named pipes

### Put challenge description here

**Flag:** pwn.college{0mTEZCW6csKwMTHMuA7sV-ZDdQ1.01MzMDOxwiNxEzNzEzW}

explain your solve and how you got to it, explain any incorrect tangents you went on while solving.

to put code snippets, put three backticks and for images and all other stuff you wish to put here, refer to the documentation given to you.

don't style it too much, your solve should be readable and understandable by you so that when you have doubts, you refer to your own writeups, instead of gpt.

```
#!/bin/bash

mkfifo /tmp/flag_fifo
/challenge/run 1> /tmp/flag_fifo
 cat /tmp/flag_fifo
 flag generated
 (confirm)
```

## What I learned

explain what you learned

## References

Add an references or videos you used while solving the challenge.
