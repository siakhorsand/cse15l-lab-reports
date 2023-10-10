## Lab Report 1- Remote Access and FileSystem(Week1)
> **ls**

the **ls** command lists files and directories in a current working directory(*pwd*). 
  ```
[user@sahara ~]$ ls ##no argument
lecture1

[user@sahara ~]$ ls lecture1 ## directory
Hello.class  Hello.java  messages  README
[user@sahara ~]$ ls lecture1/messages/ ##files
en-us.txt  es-mx.txt  fa-mx.txt  zh-cn.txt
[user@sahara ~]$
```
> **cd**

the **cd** command simply changes directories. If there is no specified argument, it changes the directory to the home directory. Otherwise, it will change to a specified directory

```
[user@sahara ~]$ cd 
[user@sahara ~]$ cd ##no argument, directory is changed to home 
[user@sahara ~]$ cd lecture1 ## specified directory
[user@sahara ~/lecture1]$ cd messages/
[user@sahara ~/lecture1/messages]$ cd en-us.txt 
bash: cd: en-us.txt: Not a directory
[user@sahara ~/lecture1/messages]$ ##cannot work with files, only directories
```

