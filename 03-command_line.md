# Learn command line

Please follow and complete the free online [Command Line Crash Course
tutorial](https://web.archive.org/web/20160708171659/http://cli.learncodethehardway.org/book/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. Each "chapter" focuses on a command. Type the commands you see in the _Do This_ section, and read the _You Learned This_ section. Move on to the next chapter. You should be able to go through these in a couple of hours.

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

- `ls`  list items in current directory
- `ls -l`  list items in current directory and show in long format to see permissions, size, and modification date
- `ls -a`  list all items in current directory, including hidden files
- `ls -F`  list all items in current directory and show directories with a slash and executables with a star
- `ls dir`  list all items in directory dir
- `cd dir`  change directory to dir
- `cd ..`  go up one directory
- `cd ~`  go to your home directory
- `cd -`  go to the last directory you were just in
- `pwd`  show present working directory
- `mkdir dir`  make directory dir
- `rm file`  rm file
- `rm -r dir`  remove direcotry dir recursively
- `cp file1 file2`  copy file1 to file2
- `cp -r dir1 dir2`  copy directory dir1 to dir2 recursively
- `mv file1 file2`  move (rename) file1 to file2
- `ln -s file link`  create symbolic link to file
- `touch file`  create or update file
- `cat file`  output the contents of file
- `less file`  view file with page navigation
- `head file`  output the first 10 lines of file
- `tail file`  output the last 10 lines of file
- `tail -f file`  output the contents of file as it grows, starting with the last 10 lines
- `vim file`  edit file
- `alias name 'command'`  create an alias for a command

---

### Q2.  List Files in Unix   

What do the following commands do:  
- `ls`  list files in current directory
- `ls -a`  list files in current directory, including hidden files
- `ls -l`  list files in current directory, shown in long format
- `ls -lh`  list total directory size and files in current directory with size including units
- `ls -lah`  same as -lh, but including hidden files
- `ls -t`  list files in current directory, sorted by date modified/created
- `ls -Glp`  ?

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

1. `ls -R`  displays subdirectories as well
2. `ls -u`  displays files by file access time
3. `ls -m`  displays the names as a comma-separated list
4. `ls -c`  displays files by file timestamp
5. `ls -p`  displays directories with /

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

`xargs` is used to build and execute commands from standard input. It allows you to run a sequence of commands from a single execution.

Simple example:
```console
$seq 5
1
2
3
4
5

$seq 5 | xargs echo "Hello"
Hello 1 2 3 4 5

$seq 5 | xargs -n 1 echo "Hello"
Hello 1
Hello 2
Hello 3
Hello 4
Hello 5
```

More practical example - convert ownership of all .dat files in a folder to "cdrom":
```console
$find / -name .dat | xargs -I{} -n 1 chgrp cdrom {}
```
