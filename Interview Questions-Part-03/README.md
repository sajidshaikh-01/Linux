# Linux Interview Questions – Set 3 (With Answers)

---

## **Q1: How do you change file permissions in Linux?**

```
chmod 755 file
chmod u+rwx file
```

---

## **Q2: What is a process in Linux?**

A running instance of a program identified by a **PID**.

---

## **Q3: How do you view active processes in Linux?**

```
ps aux
top
htop
```

---

## **Q4: How do you kill a process in Linux?**

```
kill PID
kill -9 PID   # force kill
```

---

## **Q5: What is a daemon in Linux?**

A background service that runs automatically (e.g., sshd, cron, httpd).

---

## **Q6: What is the use of the df command?**

Shows disk usage.

```
df -h
```

---

## **Q7: What does the free command do?**

Displays RAM and swap usage.

```
free -h
```

---

## **Q8: Explain the purpose of the grep command.**

Searches text patterns in files.

```
grep "error" logfile
```

---

## **Q9: How do you compress and extract files in Linux?**

```
tar -cvf file.tar folder/
tar -xvf file.tar
```

---

## **Q10: What is a symbolic link?**

A pointer to another file.

```
ln -s target link
```

---

## **Q11: What are inodes?**

Metadata about files: permissions, timestamps, size.

---

## **Q12: Purpose of crontab?**

Schedules repetitive tasks.

```
crontab -e
```

---

## **Q13: How to find the IP of a Linux server?**

```
ip addr
ifconfig
```

---

## **Q14: Purpose of sshd service?**

Handles incoming SSH connections.

---

## **Q15: How to check the status of a service?**

```
systemctl status service
```

---

## **Q16: Purpose of /etc/passwd?**

Stores basic user account information.

---

## **Q17: Use of vi editor?**

Edit text files.

```
vi file
```

---

## **Q18: How to search for a file?**

```
find / -name filename
locate filename
```

---

## **Q19: Purpose of iptables?**

Firewall for packet filtering.

---

## **Q20: What are environment variables?**

System-wide or user-specific variables like PATH, USER, HOME.

---

## **Q21: How to set environment variables?**

```
export VAR=value
```

Permanent: ~/.bashrc or /etc/profile

---

## **Q22: Purpose of /etc/shadow?**

Stores encrypted passwords.

---

## **Q23: Use of ping?**

Tests network connectivity.

```
ping google.com
```

---

## **Q24: Difference between wget and curl?**

* wget → downloading files
* curl → APIs, requests (GET, POST, PUT)

---

## **Q25: How to check disk usage?**

```
du -sh directory/
```

---

## **Q26: Use of tail command?**

Shows last lines of a file.

```
tail -f logfile
```

---

## **Q27: Purpose of xargs?**

Executes commands from input.

```
find . -name "*.log" | xargs rm -f
```

---

## **Q28: How to schedule a task?**

```
crontab -e
```

---

## **Q29: What is a package manager?**

Tool to install, update, remove software.

---

## **Q30: Common package managers?**

APT, YUM, DNF, RPM, Snap, Flatpak

---

## **Q31: Difference between yum and rpm?**

* yum handles dependencies
* rpm does not

---

## **Q32: List installed packages?**

```
rpm -qa
apt list --installed
```

---

## **Q33: What is a Linux service?**

A background program controlled by systemd.

---

## **Q34: Start/stop/restart a service?**

```
systemctl start service
systemctl stop service
systemctl restart service
```

---

## **Q35: Purpose of /etc/fstab?**

Defines filesystems to mount at boot.

---

## **Q36: What is LVM? Advantages?**

Logical Volume Manager.
Advantages:

* Resize volumes
* Combine disks
* Snapshots

---

## **Q37: Create a simple script?**

```
#!/bin/bash
echo "Hello"
```

Make executable:

```
chmod +x script.sh
```

---

## **Q38: Use of nohup?**

Runs command even after terminal closes.

```
nohup command &
```

---

## **Q39: Purpose of sed?**

Stream editor for text manipulation.

---

## **Q40: Purpose of /var directory?**

Stores logs, cache, spool files.

---

## **Q41: How to monitor system performance?**

```
top
htop
iostat
vmstat
```

---

## **Q42: Purpose of ssh command?**

Connects securely to remote servers.

---

## **Q43: How to secure SSH server?**

* Disable root login
* Change SSH port
* Use key-based login
* Enable firewall rules

---

## **Q44: Purpose of /home directory?**

Stores user files.

---

## **Q45: Use of awk command?**

Advanced text processing.

```
awk '{print $1}' file
```

---

## **Q46: What is swap space?**

Used when RAM is full.

---

## **Q47: How to create swap file?**

```
fallocate -l 1G /swapfile
chmod 600 /swapfile
mkswap /swapfile
swapon /swapfile
```

---

## **Q48: Purpose of /etc/hosts?**

Maps hostnames to IP addresses.

---

## **Q49: How to set a static IP?**

Edit:

```
/etc/netplan/*.yaml
```

Apply:

```
netplan apply
```

---

## **Q50: Purpose of nslookup?**

DNS query tool.

---

## **Q51: Difference between iptables and firewalld?**

* iptables → rule-based
* firewalld → zone-based & dynamic rules

---

## **Q52: What are runlevels?**

System modes:

* 0 halt
* 1 single user
* 3 multi-user
* 5 GUI
* 6 reboot

---

## **Q53: How to change runlevels?**

```
systemctl isolate multi-user.target
```

---

## **Q54: Purpose of /boot?**

Contains kernel, initrd, bootloader files.

---

## **Q55: Purpose of rsync?**

Fast file transfer and sync.

```
rsync -av src dest
```

---

## **Q56: What is a Linux distribution?**

A packaged version of Linux (kernel + tools).

---

## **Q57: Popular distributions?**

Ubuntu, Fedora, RHEL, CentOS, Debian, Arch

---

## **Q58: Change hostname?**

```
hostnamectl set-hostname newname
```

---

## **Q59: What are system logs and where?**

Stored in:

```
/var/log
```

---

## **Q60: Purpose of netstat?**

Shows network connections, ports, routing.

---

## **Q61: Purpose of /etc/sysconfig?**

Stores network and system configuration (RHEL-based systems).

