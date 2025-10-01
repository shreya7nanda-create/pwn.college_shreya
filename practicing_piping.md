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

###usage of pipe (|) operator

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

# Challenge Name

### Put challenge description here

**Flag:** `pwn.college{helloworld}`

explain your solve and how you got to it, explain any incorrect tangents you went on while solving.

to put code snippets, put three backticks and for images and all other stuff you wish to put here, refer to the documentation given to you.

don't style it too much, your solve should be readable and understandable by you so that when you have doubts, you refer to your own writeups, instead of gpt.

```
#!/bin/bash

example triple ticks for bash

pwn.college{helloworld}
```

## What I learned

explain what you learned

## References

Add an references or videos you used while solving the challenge.
