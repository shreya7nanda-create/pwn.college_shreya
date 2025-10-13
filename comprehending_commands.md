# cat : not the pet, but the command!

**Flag:**pwn.college{otpdUPV3gs_6rf9qkXPAXlud5HL.QXxcTN0wiNxEzNzEzW}


```
#!/bin/bash

cat flag
```

## What I learned

* cat reads out files given as its argument
* multiple files can be given as argument to cat (cat concatenates the multiple files and prints the contents of each of those   files)

# catting absolute paths

**Flag:** pwn.college{AV9SiV4ds6aig3EQpS0DvBj2yn-.QX5ETO0wiNxEzNzEzW}


```
#!/bin/bash

cat /flag
```

## What I learned

* the arguments of cat can be absolute paths

# more catting practice

**Flag:** pwn.college{cOtFDJieUP_5DVc9YM7ApN49JPk.QXwITO0wiNxEzNzEzW}


```
#!/bin/bash

cat /usr/share/mime-info/flag
```

# grepping for a needle in a haystack

**Flag:** pwn.college{wPIK6amzqAwHWwZNx00vK-H9ZF6.QX3EDO0wiNxEzNzEzW}

```
#!/bin/bash

grep pwn.college /challenge/data.txt
```

## What I learned

* grep [string_to_be_found] [file_name/path]

# comparing files

**Flag:** 

explain your solve and how you got to it, explain any incorrect tangents you went on while solving.

to put code snippets, put three backticks and for images and all other stuff you wish to put here, refer to the documentation given to you.

don't style it too much, your solve should be readable and understandable by you so that when you have doubts, you refer to your own writeups, instead of gpt.

```
#!/bin/bash

example triple ticks for bash

pwn.college{helloworld}
```

## What I learned

* "diff" is the command which compares 2 files line by line

## References

Add an references or videos you used while solving the challenge.
