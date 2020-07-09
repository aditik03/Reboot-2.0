Assignment 

Q1) Block System call : 

-block system call for date command 
  --that means you don't have to uninstall date command but if you run kernel must not accept 
-do the same Firefox as well

sol (1.1)

By using a tool STRACE we can see how Linux Kernel processes command by getting the trace of the system calls made for that particular command.
1) Login to root account -> terminal
2) Install strace if not installed
3) strace -o d.log date    /* this file will have output of the strace which contains system calls for the command */
4) grep date d.log    /* this will filter out the system calls which contains date as argument */
5) output -- execve("/usr/bin/date", ["date"], 0x7ffd5b29a750 /* 45 vars */) = 0
6) If we can change the first argument passed in execve for date command which is the absolute path for the date file and pass other path except of date of file then on running 
   date command kernel will not respond to it.

sol(1.2)   

1) By same approach we can do it for firefox.

Q2) Play with directory: 

--create a directory without name from command line

sol(2.1)

1) mkdir ''$'\t'     /* use escape character which is not visible */
2) Open files and in Home directory you can see a directory without any name.

--create a directory with name "-okgoogle"

sol(2.2)

1) mkdir -- -okgoogle   /* pass argument '--' with mkdir command which specifies no option and removes the meaning of the operator '-' */
2) Open files and in Home directory you can see a directory with name -okgoogle.

Q3) Create a directory structure 

Note :   You are only allowed to use a single command and only one time


![rb](https://user-images.githubusercontent.com/53777994/86042045-37918100-ba64-11ea-9f46-6ce78386a129.png)


sol(3)


![dir](https://user-images.githubusercontent.com/53777994/86041734-bb973900-ba63-11ea-8e7a-906ce5875f4a.PNG)


Q4) Share and files and folder 


1) create two users name jack and Jill  from command line
2) create all the data under home directory of each users 
3) login with jack user and create a file name  jack.txt using vim editor and write "hello jack"
4) from jack user also create two directories name jack1 & jack2 
5) now login from Jill user and create a file. Jill.txt using vim editor and write "hey jiil"
6) from Jill also create two directoires named jill1 & jill2 

Important :  swap these files and directories in between users  and to swap don't use root account.

sol(4)

1) Adding User

![user](https://user-images.githubusercontent.com/53777994/86048577-5d238800-ba6e-11ea-960e-958a782e27b3.PNG)

2) Creating file

![file](https://user-images.githubusercontent.com/53777994/86048579-5dbc1e80-ba6e-11ea-9fbd-6abe734b4b33.PNG)


3) Swapping files

![swap](https://user-images.githubusercontent.com/53777994/86048592-6280d280-ba6e-11ea-9629-077dee25ee9c.PNG)


Q5)  Play with files and directories 

 1) create  3 files named   abc.txt  ok  fine  g.txt  /tmp directory 
 2) create  4  directories   aa aaa aaaa  under  /tmp directory 
 3) give ls command to  list the content of  /tmp directory 
 4) make sure it will only list the content (file|directory)  having 2 char in their name.
 
 sol(5)
 
 1) Open Terminal
 2) cd /tmp
 3) touch abc.txt 'ok fine' g.txt
 4) mkdir aa aaa aaaa
 5) ls   ## this will list the files|directory of tmp ##
 6) ls -d ?? ## will list the files|directory containing only 2 char in their name ##
 
 ![pd](https://user-images.githubusercontent.com/53777994/87022338-fa5f8880-c1f3-11ea-9b79-1cab98cf7c35.PNG)
 
 
 
 
 


