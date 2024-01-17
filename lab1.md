Lab 1
---	
## command `cd`
1) An example of using the command with no arguments:
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd
[user@sahara ~]$
[user@sahara ~]$ pwd
/home
[user@sahara ~]$
```

Working directory: Before the command was run, `/home` was the working directory. After the command was run, the working directory didn't change.

Why I got this output: The command `cd` requires an argument, which would specify what directory to change to, and if there's no argument, the directory can't be changed since no new directory is specified. The command `cd` anyways doesn't output anything, and in the next line's prefix, you can see that the directory hasn't changed from `/home`. 

Error: none

2) An example of using the command with a path to a directory as an argument:

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$
[user@sahara ~]$ pwd
/home/lecture1
[user@sahara ~]$
```

Working directory: Before the command was run, `/home` was the working directory. After the command was run, the working directory was changed to `/home/lecture1`.

Why I got this output: The command `cd` requires a path to a drectory as an argument, which is `lecture1/` here. The command `cd` anyways doesn't output anything, but in the next line's prefix, you can see the new directory since `lecture1/` is a correct path to a directory. 

Error: none

3) An example of using the command with a path to a file as an argument:

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$ cd messages/
[user@sahara ~/lecture1/messages]$ cd en-us.txt
bash: cd: en-us.txt: Not a directory
[user@sahara ~/lecture1/messages]$ pwd
/home/lecture1/messages
[user@sahara ~/lecture1/messages]$ 
```
Working directory: Before the `cd en-us.txt` command was run, `/home/lecture1/messages` was the working directory. After the command was run, the working directory was still `/home/lecture1/messages`.

Why I got this output: The command `cd` requires a path to a directory as the argument, but `en-us.txt`, a path to a file name, is given here. The command `cd` anyways doesn't output anything anyways, but an error is thrown. 

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
[user@sahara ~]$
```

Working directory: Before the command was run, `/home` was the working directory. After the command was run, the working directory was still `/home`.

Why I got this output: The command `ls` doesn't require an argument, and since here there is no argument, the command gave an output of all the files and folders of the working directory, which here was only the folder **lecture1**. The working directory doesn't change with this command.

Error: none 

2. An example of using the command with a path to a directory as an argument:

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README
[user@sahara ~]$ pwd
/home
[user@sahara ~]$
```

Working directory: Before the command was run, `/home` was the working directory. After the command was run, the working directory was still `/home`.

Why I got this output: The command `ls` can take an argument, which is `lecture1/` here. The command thus gave an output of all the files and folders of the given path of `lecture1/`, without changing the directory as seen in the following line's prefix.

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
[user@sahara ~/lecture1/messages]$
```

Working directory: Before the command `ls en-us.txt` was run, `/home/lecture1/messages` was the working directory. After the command was run, the working directory was still `/home/lecture1/messages`.

Why I got this output: The command `ls` can take an argument, which is `en-us.txt` here. The command thus gave an output of all the files and folders of the given path, which would just be the file name `en-us.txt`.

Error: none 

## command `cat`
1. An example of using the command with no arguments:

```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cat

```

Working directory: Before the command was run, `/home` was the working directory. After the command was run, ^D was used to stop the `cat` command from continually running and taking further commands, which caused the prefix of `[user@sahara ~]$` to show up, revealing that the working directory was still `/home`.

Why I got this output: The command `cat` needs an argument, which is not provided here. This causes the `cat` command to continually read from the terminal, which then causes the command to output back anything typed into it.

Error: none

2. An example of using the command with a path to a directory as an argument:
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cat lecture1/ lecture1/
cat: lecture1/: Is a directory
cat: lecture1/: Is a directory
[user@sahara ~]$ pwd
/home
[user@sahara ~]$
```

Working directory: Before the command was run, `/home` was the working directory. After the command was run, the working directory was still `/home`.

Why I got this output: The command `cat` requires one or more path to files as the argument, which it will then output the content of all the files in order. The argument here was `lecture1/ lecture1/`, which are the paths to directories and not files.

Error: Since the arguments were paths to directories instead of files, two of the same error were thrown saying that `lecture1/` is a directory since the same path was given twice.

3. An example of using the command with a path to a file as an argument:
```
[user@sahara ~]$ pwd
/home
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$ cd messages/
[user@sahara ~/lecture1/messages]$ cat en-us.txt
Hello World!
[user@sahara ~/lecture1/messages]$ cat en-us.txt es-mx.txt 
Hello World!
¡Hola Mundo!
[user@sahara ~/lecture1/messages]$ pwd
/home/lecture1/messages
[user@sahara ~/lecture1/messages]$
```

Working directory: Before the command `cat en-us.txt es-mx.txt`was run, `/home/lecture1/messages` was the working directory. After the command was run, the working directory was still `/home/lecture1/messages`.

Why I got this output: The command `cat` requires one or more path to files as the argument, which it will then output the content of all the files in order. Here, the argument(s) were paths to files, so the `cat` command output the contents of the file(s) in the argument. 

Error: none
