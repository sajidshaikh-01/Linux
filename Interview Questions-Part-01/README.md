# Linux Basic Interview Questions – Complete README

 These questions cover basic commands, networking, file operations, permissions, process management, SSH, cron jobs, and more.

---

# 📌 **Q1. What is the use of the `echo` command?**

`echo` prints text/strings to the terminal.

```
echo "Hello World!"
```

---

# 📌 **Q2. How to check the computer name or hostname in Linux?**

```
hostname
```

---

# 📌 **Q3. How to check the name of the current user?**

```
whoami
```

---

# 📌 **Q4. How to check your current working directory?**

```
pwd
```

---

# 📌 **Q5. Difference between relative and absolute path?**

* **Relative Path** → Starts from current directory
* **Absolute Path** → Complete full path from root `/`

---

# 📌 **Q6. Which command is used to create a file?**

```
touch file
vi file
vim file
nano file
```

---

# 📌 **Q7. How to edit an existing file?**

Using text editors like `vi`, `vim`, `nano`, etc.

---

# 📌 **Q8. How to rename a file in Linux?**

```
mv oldname newname
```

---

# 📌 **Q9. How to search for a string in a file?**

```
grep "pattern" file
```

---

# 📌 **Q10. Difference between grep and egrep?**

* `grep` → Basic search
* `egrep` → Extended regex, supports `|` for multiple patterns

```
egrep "key1|key2|key3"
```

---

# 📌 **Q11. How can you read a file without using cat?**

Using:

```
less
more
vi
bat
```

---

# 📌 **Q12. Advantage of using `less` command?**

* Best for large files
* Easy forward/backward navigation
* Supports searching

---

# 📌 **Q13. How to check file permissions?**

```
ls -l
ll
getfacl file
```

---

# 📌 **Q14. How to check server IP?**

```
ifconfig
ip addr
```

---

# 📌 **Q15. How to read top 5 lines of a file?**

```
head -5 file
```

---

# 📌 **Q16. How to read last 5 lines of a file?**

```
tail -5 file
```

---

# 📌 **Q17. How to list hidden files?**

```
ls -la
```

---

# 📌 **Q18. How to see recently used commands?**

```
history
```

---

# 📌 **Q19. What is root in Linux?**

* Superuser / Administrator
* `/root` is root’s home directory
* `/` is root filesystem

---

# 📌 **Q20. What is an inode and how to check it?**

```
ls -li
```

Inode = data structure storing metadata.

---

# 📌 **Q21. Command to find files?**

```
find
locate
```

---

# 📌 **Q22. Command for counting words and lines?**

```
wc
wc -l
```

---

# 📌 **Q23. How to combine two commands? What is a pipe?**

```
command1 | command2
```

Pipe sends output of command1 → command2.

---

# 📌 **Q24. How to view difference between two files?**

```
diff file1 file2
```

---

# 📌 **Q25. What does shred do?**

Permanently deletes file so it cannot be recovered.

```
shred -u file
```

---

# 📌 **Q26. How to check system architecture?**

```
lscpu
dmidecode
```

---

# 📌 **Q27. How to combine two files?**

```
cat file1 file2
cat file1 file2 > newfile
```

---

# 📌 **Q28. Command to find file type?**

```
file filename
```

---

# 📌 **Q29. How to sort file content?**

```
sort file
cat file | sort
```

---

# 📌 **Q30. Ways to access a Linux server remotely?**

* Putty
* Git Bash
* SSH client

---

# 📌 **Q31. Types of file permissions?**

* `r` → read
* `w` → write
* `x` → execute

---

# 📌 **Q32. How to check permissions of a file?**

```
ls -l
getfacl file
```

---

# 📌 **Q33. Which permission allows executing a script?**

`x` (execute permission)

---

# 📌 **Q34. Redirect output to a file?**

```
command > file
```

---

# 📌 **Q35. Append output to a file without overwriting?**

```
command >> file
```

---

# 📌 **Q36. Redirect errors to a file?**

```
command 2> error.log
```

Redirect output + error:

```
command > file 2>&1
```

---

# 📌 **Q37. How to automate tasks?**

Using cron jobs:

```
crontab -e
```

---

# 📌 **Q38. How to check scheduled jobs?**

```
crontab -l
```

---

# 📌 **Q39. Meaning of cron pattern `* * * * *`?**

```
min hour day month day_of_week
```

Runs every minute.

---

# 📌 **Q40. What is a daemon service?**

Background service (e.g., sshd, httpd, chronyd).

---

# 📌 **Q41. How to check if a service is running?**

```
systemctl status service
```

---

# 📌 **Q42. Start/stop a service?**

```
systemctl start service
systemctl stop service
```

---

# 📌 **Q43. How to check free disk space?**

```
df -h
```

---

# 📌 **Q44. How to check directory size?**

```
du -sh directory
```

---

# 📌 **Q45. How to check CPU usage of a process?**

```
top
```

---

# 📌 **Q46. What is a process?**

A running instance of a program, identified by a PID.

---

# 📌 **Q47. How to check if a process is running?**

```
ps aux
```

---

# 📌 **Q48. How to terminate a running process?**

```
kill PID
```

---

# 📌 **Q49. Difference between kill and kill -9?**

`kill -9` forcefully terminates process.

---

# 📌 **Q50. How to check if a server/IP is reachable?**

```
ping server
```

Or test port:

```
telnet IP port
```

---

# 📌 **Q51. Command to get port information?**

```
netstat
```

---

# 📌 **Q52. How to check open ports?**

```
netstat -putan | grep <port>
```

---

# 📌 **Q53. How to check network interfaces?**

```
ifconfig
ip addr
```

---

# 📌 **Q54. Difference between Telnet and SSH?**

SSH is secure; Telnet is not.

---

# 📌 **Q55. Which service must run for remote login?**

`sshd`

---

# 📌 **Q56. What is SSH?**

Secure protocol for connecting to remote servers.

---

# 📌 **Q57. Why is it called Secure Shell?**

Because communication is encrypted.

---

# 📌 **Q58. Default port for SSH?**

```
22
```

---

# 📌 **
