Ques: 1
What is the use of echo command?
echo is a command that outputs the strings that are passed to it
as arguments.
echo "Hello World!"

Ques: 2
How to check the computer name or hostname in Linux?
Using 'hostname' command

Ques: 3
How to check the name of current user in Linux terminal?
whoami


Ques: 4
How to check your current path/directory you are working in?
pwd

Ques: 5
Explain the difference between relative and absolute path?
Relative path: Start from current working directory
Absolute path: The full path to a file or directory

Ques: 6
Which command to be used to create a file in Linux?
touch
vi
vim
nano...

Ques: 7
How will you edit an existing file on a Linux server?
Using vi, vim, nano etc

Ques: 8
How to rename a file in Linux?
Using mv command

Ques: 9
How to search for a string in a file?
Using grep command

Ques: 10
Difference between grep and egrep?
In egrep, you can search for more than one strings at same time
egrep "key1|key2|key4"

Ques: 11
How can you read a file without using cat command?
Using less, more, vi command and bat command 

Ques: 12
What is the advantage of using less command?
We can easily read big files.
Forward and backward search is easy.
Navigation from top to bottom is easy.

Ques: 13
How to check a file's permission?
ls -l
ll
getfacl file_name

Ques: 14
How to check the IP of your Linux server?
ifconfig
ip addr

Ques: 15
How to read the top 5 lines in a file?
head -5 file_name

Ques: 16
How to read the last 5 lines in a file?
tail -5 file_name

Ques: 17
How to list hidden files?
ls -la

Ques: 18
How to see all the recently used commands?
history

Ques: 19
What is root?
Admin or super user
/root home directory for root user
/ root directory

Ques: 20
What is inode and how to find it for a file?
ls -li
inode is an index node. It serves as a unique identifier for a
specific piece of metadata on a given filesystem

Ques: 21
Which command can you use for finding files on a Linux system?
using find and locate command

Ques: 22
Command for counting words and lines?
wc
wc -l

Ques: 23
How can you combine two commands? or What is pipe used for?
We can combine two commands using |
ex: command1 | command2
Pipe is used to combine two commands and redirect output of command1
to command2

Ques: 24
How to view the difference between two files?
diff file1 file2

Ques: 25
What is the use of the shred command do? (permanently delete a file
which is unable to recover)
shred -u file_name
shred --remove file_name

Ques: 26
How to check system architecture info?
dmidecode and lscpu

Ques: 27
How to combine two files?
cat file1 file2
cat file1 file2 > file3

Ques: 28
How can you find the type of file?
file file_name

Ques: 29
How to sort the content of a file?
sort file_name
cat file_name | sort

Ques: 30
Different ways to access a Linux server remotely (from a Windows
machine)?
Using some tools and terminal like
- putty
- git bash
- ssh

Ques: 31
What are different types of permissions for a file in Linux?
- Read (r)
- Write (w)
- Executable (x)

Ques: 32
How to check the permissions given to a file?
ls -l
ll
getfacl file_name

Ques: 33
Which permission allow a user to run an executable file (script)
We need to provide executable (x) permission to the user.

Ques: 34
How to write the output of a command into a file?
command > file_name

Ques: 35
How to write something in a file without deleting the existing
content?
We can append the file using >>

Ques: 36
How to redirect an error of a command into a file?
To redirect an error we need to use 2>
To redirect both error and output, 2>&1

Ques: 37
How to Automate any task or script?
Using cron jobs
For which we have crontab and at command.

Ques: 38
How to check scheduled jobs?
crontab -l

Ques: 39
What is the meaning of this cron job? * * * * *
min.hour.dayofmonth.month.dayofweek

Ques: 40
What is daemon service?
Service that keep running in background.
Example: httpd, sshd, chronyd

Ques: 41
How to check if a service is running or not?
systemctl status service_name

Ques: 42
How to start/stop any service?
systemctl start service_name
systemctl stop service_name

Ques: 43
How to check for free disk space?
We can use df command

Ques: 44
How to check the size of a directory's content?
We can use du command

Ques: 45
How to check CPU usage for a process?
We can use top command

Ques: 46
What is a process in Linux?
An instance of a running program.
Whenever you start a program/application or execute a command, a process is
created.
For every process a unique no. is assigned which is called PID (Process ID)

Ques: 47
How to check if a process/application is running or not?
Using ps command

Ques: 48
How to terminate/stop a running process?
Using kill command

Ques: 50
Difference between kill and kill -9
kill -9 will terminate a program forcefully

Ques: 51
How to check if a IP/Server is accessible or not?
We can use ping or telnet command

Ques: 52
Which command to use to get info about ports?
We can use netstat command

Ques: 53
How to check open port on Linux system?
netstat putan | grep port_no

Ques: 54
How to check network interfaces in Linux?
We can use ifconfig and netstat command

Ques: 55
Difference between Telnet and SSH?
SSH is secured and telnet is not.

Ques: 56
Which service should be running on server to allow you to connect
remotely?
ssh or sshd

Ques: 57
What is SSH?
SSH or Secure Shell is a
network communication protocol that enables two computers/devices to
communicate and share data.

Ques: 58
Why it is called as Secure Shell?
Because communication between host and client will be in encrypted format.

Ques: 59
WHat id default port for SSH?
22

Ques: 60
Which command is used to access a linux system from a terminal or
another linux server?
ssh user@198.168.x.x
