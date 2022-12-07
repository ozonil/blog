---
title: "Globbing"
date: 2022-12-06T12:28:32-05:00
tags: [programming, unix]
---

Globbing is a built-in pattern matching system for unix systems. After a unix command like 'ls' or 'find' instead of a regular string, you can enter a wild-card pattern which is a string containing characters like '?', '*' or '[', each of which has a specific meaning associated with it. It works with all commands that take in file arguments.

'?' - matches any single character
'*' - matches any string including empty strings
'[...]' - allows specification of a range of digits or alphabets and allows matching for those specific characters. Ex: [a-z] or [1-5]

Examples:

```bash
$ find /bin -type f -name *name
/bin/uname
/bin/hostname
/bin/avahi-set-host-name
/bin/dirname
/bin/basename
```
In the above `find` command, we are giving it the /bin directory and asking it to searching for files with names ending with 'name'.

```bash
$ rm *.o
```
In the above, we are removing all the files ending with '.o'.

```bash
$ ls
file1.txt file2.txt file3.txt file4.txt file5.txt
$ rm *[1-3].txt
$ ls
file4.txt file5.txt
```
In the above, we are removing all files numbered from 1 to 3.

NOTE: though it might look similar, globbing and regex are two different things. `find` command for example provides `-regex` option to do regex search. Globbing, you get by default.

***

Other references:

[globs man pages](https://man7.org/linux/man-pages/man7/glob.7.html)

[wikipedia glob](https://en.wikipedia.org/wiki/Glob_(programming))

