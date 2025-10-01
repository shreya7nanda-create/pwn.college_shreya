# matching with *

### * matches with a part of the filename or path

**Flag:** pwn.college{cGGdGU0uiRX9WBPKWXxzchrVy-l.QXxIDO0wiNxEzNzEzW}

i referenced to the directory "/challenge"(which was the argument to command cd) using *. 
```
#!/bin/bash
cd /ch*
/challenge/run

flag generated
```

## What I learned

1. the shell treats * as a wildcard. on encountering it, it matches it to a file with similar pattern.
2. * matches any part of a file name EXCEPT / or a leading .

## References

# matching with ?

### ? matches all files with similar pattern BUT matches it to 1 character ONLY

**Flag:** pwn.college{8NOYAmsA8eH6P_Cf8kpdRMwOouJ.QXyIDO0wiNxEzNzEzW}

i refernced c and l in /challenge using ?
```
#!/bin/bash

cd /?ha??enge
/challenge/run

flag generated
```

## What I learned

we can reference to any one character in a filename using ?

## References

# matching with []

### the wildcard [] matches with any of the choice of characters entered within

**Flag:** pwn.college{km5pPZL-OtzWeVPIT_Cy9Eg1D-a.QXzIDO0wiNxEzNzEzW}

referenced to file_a file_b file_s and file_h using [] to get flag.
```
#!/bin/bash

cd /challenge/files
/challenge/run file_[absh]

flag generated
```

## What I learned

we can refernce to a variety of characters with []

## References

# matching paths with []

### we can expand our entire paths using globbed arguments to the command

**Flag:** pwn.college{cxD-560GI8azzicIgecd9SpQIgu.QX0IDO0wiNxEzNzEzW}

bracket-globbed the absolute paths to the files
```
#!/bin/bash

/challenge/run /challenge/files/file_[bash]

flag generated
```

## What I learned

we can glob the absolute paths to the files using [] wildcard

## References

# multiple globs

### expansion of multiple globs in a single word

**Flag:** pwn.college{c1dwH97N3bwe6Tlho9dJKN-lrVx.0lM3kjNxwiNxEzNzEzW}

changed directories, ran the challenge command and for its argument, i gave *p* to match every filename with a letter p
```
#!/bin/bash

cd /challenge/files
/challenge/run *p*

flag generated
```

## What I learned

we can glob multiple times in a single word and it will be expanded

## References

# mixing globs

### using all types of globbing prev learned in this module

**Flag:** pwn.college{wfx7xrJB6FlMPfmp2TM24CQrKPN.QX1IDO0wiNxEzNzEzW}

cd into the specified directory,
run the challenge command and into its argument, use globbing to match the specified files
```
#!/bin/bash

cd /challenge/files
/challenge/run [cpe]*

flag generated
```

## What I learned

learned to use multiple globs in a single argument to generate multiple files

## References

# exclusionary globbing

### filtering out files while trying to match arguments using globbing

**Flag:** pwn.college{krrllfblTOvHuce6ofu43Sx2HNN.QX2IDO0wiNxEzNzEzW}

cd into specified directory,
into the argument of the specified challenge cmd, glob to filter out all files containg p,w or n
** both ! and ^ can be used for specifying exclusionary globbing
**if we use !, remember that it has other meanings when not used in the BEGINNING of the []wildcard

```
#!/bin/bash

 cd /challenge/files
 /challenge/run [^pwn]*
 
 flag generated
```

## What I learned

we can conduct exclusionary searches to match files using globbing

## References

# tab completion

### using "autocomplete" to specify files 

**Flag:** pwn.college{oewBpwh-ZqE_QhO5hF0SH6ipEI_.0FN0EzNxwiNxEzNzEzW}

opened /challenge/pwncollege file by clicking tab after typing pwn for autocompletion
```
#!/bin/bash

/challenge/pwncollege

flag generated
```

## What I learned

we can use tab to autocomplete file names for SAFER GLOBBING,
since this avoids errors like accidentally specifying and working on the wrong file

## References

# multiple options for tab completion

### keep tabbing for generating multiple options to autocomplete the filename

**Flag:** pwn.college{sWHeC7ya-cmfX4c2vTMlblPQWOD.0lN0EzNxwiNxEzNzEzW}

open /challenge/files/p, 
tab after typing p to get /challemge/files/pwn,
tab after typing c to get /challenge/files/pwncollege-,
type flag to generate flag 
```
#!/bin/bash

cat /challenge/files/pwn
cat /challenge/files/pwncollge-
cat /challenge/files/pwncollege-flag

flag generated
```

## What I learned

we can use tab multiple times to obtain automplete options

## References

# tab completion on commands

### using "autocomplete" on commands

**Flag:** pwn.college{kZBL03VKzmFM0lEK7bvQAazjUw0.0VN0EzNxwiNxEzNzEzW}

autocomplete the "pwncollege" command to generate the rest of the command to obtain flag
```
#!/bin/bash

pwncollege-15283

flag generated
```

## What I learned

it is possible to autocomplete commands
MUST BE CAREFUL while doing so(make sure to double check if the command is crct)

## References

