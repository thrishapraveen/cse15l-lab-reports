Lab 1
---	
## command `cd`
1. An example of using the command with no arguments:
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd
[user@sahara ~]$
[user@sahara ~]$ pwd
/home
```
Working directory: Before the command was run, `/home` was the working directory. After the command was run, the working directory didn't change.

Why I got this output: The command `cd` requires an argument, which would specify what directory to change to, and if there's no argument, the directory can't be changed since no new directory is specified. The command `cd` anyways doesn't output anything, but in the next line, you can see that the directory hasn't changed from `/home`. 

Error: none

2. An example of using the command with a path to a directory as an argument:

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$
[user@sahara ~]$ pwd
/home/lecture1
```

Working directory: Before the command was run, `/home` was the working directory. After the command was run, the working directory was still `/home`.

Why I got this output: The command `cd` requires a path to a drectory as an argument, which is `lecture1/` here. The command `cd` anyways doesn't output anything, but in the next line, you can see the new directory since `lecture1/` is a correct path to a directory. 

Error: none

3. An example of using the command with a path to a file as an argument:
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$ cd messages/
[user@sahara ~/lecture1/messages]$ cd en-us.txt
bash: cd: en-us.txt: Not a directory
[user@sahara ~/lecture1/messages]$ pwd
/home/lecture1/messages
```
Working directory: Before the commands was run, `/home` was the working directory. After all the commands were run, the working directory changed to `/home/lecture1/messages`.

Why I got this output: The command `cd` requires an argument, which is `en-us.txt` here. The command `cd` anyways doesn't output anything anyways, but an error is thrown. 

QUESTION: IS THIS THE RIGHT WAY TO EXPLAIN THE OUTPUT?

Error: The command `cd` requires a path to a directory as an argument, but here the argument `en-us.txt` is a path to a file, which causes an error. 

## command `ls`
1. An example of using the command with no arguments:
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls
lecture1
[user@sahara ~]$ pwd
/home
```
Working directory: Before the command was run, `/home` was the working directory. After the command was run, the working directory was still `/home`.

Why I got this output: The command `ls` doesn't require an argument, and since here there is no argument, the command gave an output of all the files and folders of the working directory, which here was only the folder **lecture1**.  

Error: none 

2. An example of using the command with a path to a directory as an argument:

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README
[user@sahara ~]$ pwd
/home
```
Working directory: Before the command was run, `/home` was the working directory. After the command was run, the working directory was still `/home`.

Why I got this output: The command `ls` can take an argument, which is `lecture1/` here. The command thus gave an output of all the files and folders of the given path of `lecture1/`.

Error: none 

3. An example of using the command with a path to a file as an argument:

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$ cd messages/
[user@sahara ~/lecture1/messages]$ ls en-us.txt
en-us.txt
[user@sahara ~/lecture1/messages]$ pwd
/home/lecture1/messages
```
Working directory: Before the command was run, `/home` was the working directory. After the command was run, the working directory was changed to `/home/lecture1/messages`.

Why I got this output: The command `ls` can take an argument, which is `en-us.txt` here. The command thus gave an output of all the files and folders of the given path, which would just be the file `en-us.txt`.

Error: none 

## command `cat`
1. An example of using the command with no arguments:

2. An example of using the command with a path to a directory as an argument:

3. An example of using the command with a path to a file as an argument:
