# Lab Report #1

## *cd* - change directory 
- Here is an example of using *cd* with *no* arguments:
  
`cd`

  This command simply takes the user to the home directory.
![cd_noArg](cd_noArg.png)

- Here is an example of using *cd* with a path to an example *directory*:

`cd/Users/siakhorsand/cs11`

This command takes the terminal to the cs11 folder (*ls* and *pwd* are then used to check the contents of the folder/current directory).
![cd_Direct](cd_Direct.png)

- Here is an example of using *cd* with a direct path to a file:

`cd /Users/siakhorsand/Documents/Github/COGS108_Repo/README.md`

As you can see in the image below, *cd* does not work with a path to a file because it does not open files or show contents. However, it can navigate to the folder in which the file is in. 
![cd_file](cd_file.png)


## *ls* - list

- Here is an example of using *ls* with *no* arguments:

`ls`

This command simply shows the contents of the current directory.

![ls_noArg](ls_noArg.png)

- Here is an example of using *ls* with a path to a directory:

`ls /Users/siakhorsand/Documents/`


This argument simply shows the contents of the directory to which the terminal has traveled. 

![ls_Direct](ls_Direct.png)

- Here is an example of using *ls* with a path to a file in a directory:

`ls /Users/siakhorsand/Documents/text.txt`

This argument takes the terminal to the path of the file, if the file exists. 
![ls_file](ls_file.png)


## *cat* - concatenate and display 

- Here is an example of using *cat* with *no* arguments:

`cat`

As shown in the image below, *cat* with no arguments has no output, as it waits for more input.

![cat_noArg](cat_noArg.png)
- Here is an example of using *cat* with a path to a directory:
`cat /Users/siakhorsand/Documents`

This argument states that the Documents folder is a directory and not a file. 
![cat_Direct](cat_Direct.png)

- Here is an example of using *cat* with a path to a file:
  
`cat /Users/siakhorsand/Documents/text.txt`

This argument shows the contents of the specific text file in the directory that is specified. 

![cat_file](cat_file.png)
