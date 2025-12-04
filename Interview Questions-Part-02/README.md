# Linux Additional Interview Questions – Complete README (Arranged & Answered)

---

# 📌 Q1. What is the kernel?

The Linux kernel is the **core component** of the operating system. It manages:

* Hardware communication
* Memory
* CPU scheduling
* Device drivers
* System processes

---

# 📌 Q2. What is swap space?

Swap space is used when **RAM is full**. Inactive memory pages are moved to swap to free RAM.

---

# 📌 Q3. Search and replace a word in a file?

```
sed 's/old/new/g' file_name
```

---

# 📌 Q4. What is the use of SCP command?

SCP copies files between local ↔ remote systems using SSH.

```
scp file user@server:/path
```

---

# 📌 Q5. What is FTP used for?

FTP transfers files between client and server.

---

# 📌 Q6. What is alias and how to set it?

Alias = shortcut for long commands.

```
alias d="ls -ltr"
```

---

# 📌 Q7. Difference between update and upgrade?

* **Update** → Updates package list & latest versions
* **Upgrade** → Installs latest versions + removes obsolete packages

---

# 📌 Q8. Default ports (important)

* DNS → 53
* SMTP → 25
* FTP → 21
* SSH → 22
* DHCP → 67, 68
* Squid → 3128
* HTTP → 80
* HTTPS → 443

---

# 📌 Q9. Check if a package is installed?

```
rpm -qa | grep package
```

---

# 📌 Q10. Which command sends 3 ping packets?

```
ping -c 3 google.com
```

---

# 📌 Q11. Which file contains group names and GIDs?

```
/etc/group
```

---

# 📌 Q12. Which variable stores exit status of last command?

```
$?
```

---

# 📌 Q13. Command to display CPU info?

```
cat /proc/cpuinfo
lscpu
```

---

# 📌 Q14. Valid exit status values?

```
0–255
```

---

# 📌 Q15. Directory for log files (FHS)?

```
/var/log
```

---

# 📌 Q16. What port must be open for ping?

Ping **does not use ports**.

---

# 📌 Q17. How to transfer files between Linux and Windows?

Tools:

* SSH/SCP
* SFTP
* WinSCP
* FileZilla

---

# 📌 Q18. Can you split a file? How?

```
split -l 3 file
```

---

# 📌 Q19. Get unique values from a list?

```
sort file | uniq
```

---

# 📌 Q20. How to edit and save a file using VI?

```
vi file
i → insert
ESC
:wq
```

---

# 📌 Q21. Difference between find and locate?

* `find` → searches filesystem in real-time
* `locate` → searches from a cached DB → must update with `updatedb`

---

# 📌 Q22. Count number of files/folders in a directory?

```
ls -1 | wc -l
```

---

# 📌 Q23. Read only lines 26 to 30?

```
head -30 file | tail -5
```

---

# 📌 Q24. Use of tar command?

Tar creates compressed archives.

---

# 📌 Q25. Redirect both output and error?

```
command > file 2>&1
```

---

# 📌 Q26. DNS resolution tools?

```
ping
nslookup
dig
host
```

---

# 📌 Q27. Use of at command?

Schedules a **one-time job**.

---

# 📌 Q28. Which service does at depend on?

```
atd
```

---

# 📌 Q29. What is ACL? Advantage?

ACL = Access Control List
Commands:

```
setfacl
getfacl
```

Advantage: Set permission for **specific user/group**.

---

# 📌 Q30. Difference between hard and soft links?

### Hard Link:

* Same inode
* Cannot link directories
* If original deleted → hard link still works

### Soft Link:

* Different inode
* Shortcut (pointer)
* Breaks if original is deleted

---

# 📌 Q31. Show environment variables?

```
env
printenv
```

---

# 📌 Q32. How to set environment variables?

Temporary:

```
export VAR=value
```

Permanent:

* `~/.bashrc`
* `/etc/profile`

---

# 📌 Q33. Command to show all PIDs of nginx?

```
pidof nginx
```

---

# 📌 Q34. What is nice value?

Nice value decides process priority.
Range: **-20 (high priority) to +19 (low priority)**

---

# 📌 Q35. How to check nice value?

```
ps -l -p PID
```

---

# 📌 Q36. Increase priority of PID 8675?

```
renice -20 -p 8675
```

---

# 📌 Q37. Check %CPU and %MEM of a process?

```
top
```

---

# 📌 Q38. Run task even after terminal closes?

```
nohup command &
```

---

# 📌 Q39. See all active jobs?

```
jobs
```

---

# 📌 Q40. Resume a stopped job?

Background:

```
bg
```

Foreground:

```
fg
```

---

# 📌 Q41. Show kernel & hardware messages?

```
dmesg
```

---

# 📌 Q42. Show only XML files in a directory?

```
ls *.xml
```

---

# 📌 Q43. Create 100 files?

```
touch file{1..100}
```

---

# 📌 Q44. Show files starting with c or m?

```
ls [cm]*
```

---

# 📌 Q45. Show all lines except those starting with #?

```
grep -v ^# file
```

---

# 📌 Q46. List files except those starting with "e"?

```
ls -1 | grep -v ^e
```

---

# 📌 Q47. How to test Linux on a Windows machine?

Use VM:

* VMware
* VirtualBox
* Hyper-V

---

# 📌 Q48. Command to display memory + swap usage?

```
free -h
```

---

# 📌 Q49. SSH connection timed out – which port to check?

```
22
```

---

# 📌 Q50. How to check Linux filesystem?

```
lsblk -f
```


