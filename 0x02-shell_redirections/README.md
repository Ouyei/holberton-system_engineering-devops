# 0x02. Shell, I/O Redirections and filters


Permissions
>chmod u+x "file1"


## **0. Hello World**
Write a script that prints “Hello, World”, followed by a new line to the standard output.

```
#!/bin/bash
echo "Hello, World"
```

## **1. Confused smiley**
Write a script that displays a confused smiley "(Ôo)'.

```
#!/bin/bash
echo \"\(\Ôo\)\'
```

## **2. Let's display a file**
Display the content of the /etc/passwd file.

```
#!/bin/bash
cat /etc/passwd
```

## **3. What about 2?**
Display the content of /etc/passwd and /etc/hosts

```
#!/bin/bash
cat /etc/passwd /etc/hosts
```

## **4. Last lines of a file**
Display the last 10 lines of /etc/passwd

```
#!/bin/bash
tail /etc/passwd
```

## **5. I'd prefer the first ones actually**
Display the first 10 lines of /etc/passwd

```
#!/bin/bash
head /etc/passwd
```

## **6. Line #2**
Write a script that displays the third line of the file iacta.

The file iacta will be in the working directory

You’re not allowed to use sed

```
#!/bin/bash
head -n 3 iacta | tail -n 1
```

## **7. It is a good file that cuts iron without making a noise**
Write a shell script that creates a file named exactly \*\\'"Best School"\'\\*$\?\*\*\*\*\*:) containing the text Best School ending by a new line.


```
#!/bin/bash
echo "Best School" > '\*\\'\''"Best School"\'\''\\*$\?\*\*\*\*\*:)'
```

## **8. Save current state of directory**
Write a script that writes into the file ls_cwd_content the result of the command ls -la. If the file ls_cwd_content already exists, it should be overwritten. If the file ls_cwd_content does not exist, create it.

```
#!/bin/bash
ls -la > ls_cwd_content
```

## **9. Duplicate last line**
Write a script that duplicates the last line of the file iacta

The file iacta will be in the working directory

```
#!/bin/bash
tail -1 iacta >> iacta
```

## **10. No more javascript**
Write a script that deletes all the regular files (not the directories) with a .js extension that are present in the current directory and all its subfolders.

```
#!/bin/bash
find . -name '*.js' -type f -delete
```

>**find . -name '*.js'| xargs rm**


## **11. Don't just count your directories, make your directories count**
Write a script that counts the number of directories and sub-directories in the current directory.

The current and parent directories should not be taken into account
Hidden directories should be counted

```
#!/bin/bash
find ./* -type d -print | wc -l
```

## **12. What’s new**
Create a script that displays the 10 newest files in the current directory.

Requirements:

One file per line
Sorted from the newest to the oldest

```
#!/bin/bash
ls -t | head
```

## **13. Being unique is better than being perfect**
Create a script that takes a list of words as input and prints only words that appear exactly once.

Input format: One line, one word
Output format: One line, one word
Words should be sorted

```
#!/bin/bash
sort | uniq -u
```

## **14. It must be in that file**
Display lines containing the pattern “root” from the file /etc/passwd

```
#!/bin/bash
grep root /etc/passwd
```

## **15. Count that word**
Display the number of lines that contain the pattern “bin” in the file /etc/passwd

```
#!/bin/bash
grep -c bin /etc/passwd
```

## **16. What's next?**
Display lines containing the pattern “root” and 3 lines after them in the file /etc/passwd.

```
#!/bin/bash
grep -A 3 root /etc/passwd
```

## **17. I hate bins**
Display all the lines in the file /etc/passwd that do not contain the pattern “bin”.

```
#!/bin/bash
grep -v bin /etc/passwd
```

## **18. Letters only please**
Display all lines of the file /etc/ssh/sshd_config starting with a letter.

include capital letters as well

```
#!/bin/bash
grep ^[[:alpha:]]  /etc/ssh/sshd_config
```

>**grep ^[[:alpha:]*] /etc/ssh/sshd_config**

## **19. A to Z**
Replace all characters A and c from input to Z and e respectively.

```
#!/bin/bash
tr "Ac" "Ze"
```

## **20. Without C, you would live in hiago**
Create a script that removes all letters c and C from input.

```
#!/bin/bash
tr -d 'Cc'
```

>**tr -d [cC]**

## **21. esreveR**
Write a script that reverse its input.

```
#!/bin/bash
rev
```

## **22. DJ Cut Killer**
Write a script that displays all users and their home directories, sorted by users.

```
#!/bin/bash
cut -d":" -f 1,6 /etc/passwd | sort

## **23. Empty casks make the most noise**
Write a command that finds all empty files and directories in the current directory and all sub-directories.

    *Only the names of the files and directories should be displayed (not the entire path)
    *Hidden files should be listed
    *One file name per line
    *The listing should end with a new line
    *You are not allowed to use basename, grep, egrep, fgrep or rgrep

```
#!/bin/bash
find . -empty -printf "%f\n"
```
```












