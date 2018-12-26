# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

1. show current working directory path: `pwd`
2. creating a directory: `mkdir mydirectory`
3. deleting a directory: `rm -r mydirectory`
4. creating a file using `touch` command: `touch myfile.txt`
5. deleting a file: `rm myfile.txt`
6. renaming a file: `mv myfile1.txt myfile2.txt`
7. listing hidden files: `ls -a`
8. copying a file from one directory to another: `cp /path/myfile.txt /new/path/`
9. find an expression in a file: `grep "expression" myfile.txt`
10. sort entries in a file: `sort myfile.txt`
11. remove identical entries on consecutive lines in a file: `uniq myfile.txt`
12. find and replace expressions in a file: `sed '/s/text/newtext/g' myfile.txt`

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

* `ls`: list non-hidden contents of a directory
* `ls -a`: list all contents of a directory
* `ls -l`: list contents of a directory with additional information
* `ls -lh`: list contents of a directory with unit suffixes for file size information
* `ls -lah`: list all contents of a directory with additional information and unit suffixes for file sizes
* `ls -t`: list contents of a directory sorted by time modified
* `ls -Glp`: list colorized contents of a directory with additional information and with slashes following directory names

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

* `ls -r`: list contents of a directory in reverse order
* `ls -R`: list contents of a directory and include subdirectory contents
* `ls -u`: list contents of a directory sorted by file access time
* `ls -x`: list contents of a directory displayed as rows instead of columns
* `ls -m`: list contents of a directory as a comma-separated list

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

`xargs` converts standard input into arguments for a command. You can either pipe standard input to it or use it alone before a command, which will allow you to type standard input and pass it as an argument to the command. Pressing `ctrl+d` tells `xargs` that you are done passing arguments.

One way to use `xargs` is for removing a list of files in a directory by typing `find /path/to/directory -type f -print / xargs rm`. This pipes the standard out of the `find` command as an argument to the `rm` command, which in this case would be a list of files. 
