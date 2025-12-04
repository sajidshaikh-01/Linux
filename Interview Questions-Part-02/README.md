Ques: 3
What is kernel?
The Linux kernel is the main component of a Linux OS and is the core interface
between a computer’s hardware and its processes.
It communicates between the 2, managing resources as efficiently as possible.

Ques: 4
What is swap space?
Swap space in Linux is used when the amount of physical memory (RAM) is
full. If the system needs more memory resources and the RAM is full, inactive
pages in memory are moved to the swap space.

Ques: 5
Search a word in a file and replace it in entire file?
Using sed command.
sed 's/<string_to_change>/<new_string>/g' file_name

Ques: 6
What is use of SCP command?
The scp command copies files or directories between a local and a
remote system or between two remote systems.
SCP uses SSH for data transfer.

Ques: 7
What is use of FTP command?
FTP is the file transfer protocol to exchange files to
and from a remote computer or network.

Ques: 8
What is alias and how to setup?
To create shortcut to the command or task
alias d="ls -ltr | awk '{print \$9}'"

Ques: 9
Difference between upgrade and update system?
Update: updates all the presently installed packages to their latest
versions that are available in the repositories
Upgrade: performs the same action as “yum update”
, but once finished
it also removes all of the obsolete packages from the system.

Ques: 10
Name default ports used for DNS, SMTP, FTP, SSH, DHCP and squid.
DNS - 53
SMTP - 25
FTP - 21
SSH - 22
DHCP - 67,68
Squid - 3128
Http - 80
Https - 443

Ques: 11
How to check if a package is installed or not?
rpm -qa | grep <package_name>

Ques: 12
Which of the following commands sends exactly three
ping packets to google.com?
ping -c 3 google.com

Ques: 13
Which file contains a list of group names and GIDs?
/etc/group/

Ques: 14
Which of the following contains the value of the
exit status of the previously executed command?
$?

Ques: 15
Which command displays the number and type of
processors used by a Linux system?
cat /proc/cpuinfo
lscpu

Ques: 19
What are the valid values of the exit status?
0-255

Ques: 20
According to the FHS, what is the correct directory for
log files?
/var/log/

Ques: 21
What port must be open to ping a given host?
Ping don't use port

Ques: 22
How will you transfer file from a Linux server to your
windows OS and vice versa?
Using SSH, FTP, SFTP and tools like WinSCP, FileZilla

Ques: 23
Can you split a file into two? If yes, then how?
split -l 3 file_name

Ques: 24
How you can get the unique values from a list?
sort file_name | uniq

Ques: 25
Using VI editor, how you will edit and save a file?
vi file_name
i - for insert
ESC - to come out of insert mode
wq - to save

Ques: 26
What is the difference between find and locate
command?
locate command search in it's own db and you
will need to keep updating db.

Ques: 29
How you can find no. of files, folders in a directory?
ls -1 | wc -l

Ques: 30
I want to read only line 26 to 30th Line, how you
will do it?
head -30 file_name | tail -5

Ques: 31
What is the use of Tar command?
The tar command is used to compress a group of files into an archive.
Tar archives combine multiple files and/or directories together into a
single file.

Ques: 32
How to redirect both standard output and error to
a file?
command > file 2>&1

Ques: 33
Name some commands for DNS resolution?
ping, nslookup, dig and host

Ques: 34
What is use of At command?
Command used to schedule a task once.

Ques: 35
Which service is used by At command?
Atd

Ques: 39
What is ACL and it's advantage?
Access Control List is used to modify the permissions of files.
for this we use setfacl and getfacl commands
Advantage: We can provide permission to a specific user.

Ques: 41
Difference between Hard and Soft links?


Ques: 42
What command you can use to see all the environment
variables?
env or printenv

Ques: 44
How can you set environment variables in Linux?
using export command
to set variable for the current user -
.bashrc
to set variable for globally - /etc/bashrc or /etc/profile

Ques: 45
What command allows you to display all the process IDs of the
running nginx processes?
pidof httpd

Ques: 46
What is nice value of a process?

Ques: 47
How to check the nice value of a process?
ps -l PID

Ques: 48
You want a process with a PID of 8675 to complete its task faster than the default
rate. Which command should you run to accomplish this goal?
renice -20 -p 8675,
this can be done by top command also

Ques: 49
What command can be used to check the %CPU and %Memory
of a process?
top command

Ques: 50
If you want to run a task/script in background even if you
close your terminal, what is the way?

Ques: 51
How to see all the active jobs?
jobs

Ques: 52
How to resume a stopped job in background or foreground?
bg
fg

Ques: 53
Which command displays information about kernel-related messages along with
hardware and system startup messages stored in kernel ring buffer?
dmesg

Ques: 54
In a directory you have a combination of files like xml, yml, scripts, logs etc,
how you will get/see only xml files?
ls -l *.xml

Ques: 55
Create 100 files with naming file1, file2 file3... file100.
touch file{1..100}

Ques: 56
How would you display all the files in the present working
directory that start with either the letter "c" or "m"?
ls [cm]*

Ques: 57
Run a command that shows all the lines except any lines starting
with the a character # in a file?
cat file | grep -v ^#

Ques: 58
Which of the following commands lists all files and
directories except those beginning with the letter "e"?
ls -1 | grep -v ^a

Ques: 61
You have a windows machine and you want to test an
application on Linux, what you can do?
We can use VM to use multiple OS like Linux on our windows
machine and test our application.

Ques: 66
Which command displays memory usage, including the amount
of swap space being used?
free command

Ques: 68

A user reports that they are receiving a "Connection timed out" error when
attempting to SSH into a Linux server you support.

You suspect a firewall is blocking inbound SSH attempts, and you contact the
networking team to investigate.

Assuming SSH is using the default port, which port number do you provide to
the networking team to investigate?

Answer: 22
Ques: 70
How to check your Linux FileSystem?
lsblk -f
