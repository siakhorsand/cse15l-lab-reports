## Lab Report 1- Remote Access and FileSystem(Week1)
> **ls**

the **ls** command lists files and directories in a current working directory(*pwd*). 
  ```
[user@sahara ~]$ ls ##no argument
lecture1
```
here, ls simply lists what is in the home directory

```
[user@sahara ~]$ ls lecture1 ## directory
Hello.class  Hello.java  messages  README
```
here, ls lists the files/directories in the specified directory, in this case, lecture1. 

```
[user@sahara ~]$ ls lecture1/messages/ ##files
en-us.txt  es-mx.txt  fa-mx.txt  zh-cn.txt
[user@sahara ~]$
```
similarly, ls lists everything in the messages directory, but cannot go any further because there are no further directories. 

> **cd**

the **cd** command simply changes directories. If there is no specified argument, it changes the directory to the home directory. Otherwise, it will change to a specified directory

```
[user@sahara ~]$ cd 
[user@sahara ~]$ cd ##no argument, directory is changed to home

```
here, the directory is changed to home with no output

```
[user@sahara ~]$ cd lecture1 ## specified directory
[user@sahara ~/lecture1]$ cd messages/
```
now that we specified what directory to switch to, cd will change the directory to lecture1, and then messages
```
[user@sahara ~/lecture1/messages]$ cd en-us.txt 
bash: cd: en-us.txt: Not a directory
[user@sahara ~/lecture1/messages]$ ##cannot work with files, only directories
```
here, we get an error since en-us.txt is not a directory and it is a file and cd changes directories and not files 


>cat
```
[user@sahara ~]$ cat lecturel ## directory cat: lecturel: Is a directory
```
cat specifies if the specified path is a directory or not
in this case, lecture1 is a directory
```
[user@sahara ~]$ cat lecturel/messages/fa-mx.t×t ## file salam donya
```
cat is also able to display the content of a file as seen above.

```
[user@sahara ~]$ cat ## no argument
```
this seems to have no output intil I type words in, where my words will be displayed. 
