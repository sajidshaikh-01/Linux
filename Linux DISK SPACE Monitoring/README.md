# Linux Disk Space Monitoring – Complete README

Monitoring disk space is essential for Linux administrators, DevOps engineers, SREs, and cloud engineers. Disk full issues can break applications, CI/CD pipelines, Docker, Kubernetes nodes, logging, and system services.
---

# 📌 1. Check Overall Disk Usage – `df`

`df` shows mounted filesystems and disk usage.

### ✔ Human‑readable output

```
df -h
```

### ✔ Show file system type also

```
df -Th
```

### ✔ Show specific directory usage

```
df -h /var/log
```

---

# 📌 2. Check Directory/File Size – `du`

`du` shows how much space directories are using.

### ✔ Show size of all items in current directory

```
du -sh *
```

### ✔ Check size of a specific folder

```
du -sh /var/log
```

### ✔ Show detailed size of all subdirectories

```
du -h --max-depth=1 /home
```

---

# 📌 3. Find Largest Files on System

### ✔ Find files larger than 100MB

```
find / -type f -size +100M
```

### ✔ Show top 20 largest files

```
find / -type f -exec du -Sh {} + | sort -rh | head -n 20
```

---

# 📌 4. Clean Log Files Safely

### ✔ Clear large log files (don’t delete file)

```
> /var/log/syslog
> /var/log/auth.log
```

### ✔ Delete old logs (older than 7 days)

```
find /var/log -name "*.log" -mtime +7 -delete
```

---

# 📌 5. Monitor Disk I/O – `iostat`

Install first:

```
sudo apt install sysstat
```

Run:

```
iostat -xz 1
```

Shows:

* Disk utilization
* Read/write speed
* I/O wait

---

# 📌 6. Monitor Disks in Real Time – `watch`

```
watch df -h
```

Or monitor a directory:

```
watch du -sh /var/log
```

---

# 📌 7. Check Inodes (Important for Kubernetes / Docker)

Running out of **inodes** breaks clusters even if disk is empty.

```
df -i
```

Identify inode-heavy directories:

```
find / -xdev -type d -print0 | xargs -0 du -s | sort -n
```

---

# 📌 8. Disk Usage with Interactive Tools

### ✔ ncdu (Best disk analyzer)

```
sudo apt install ncdu
ncdu /
```

### ✔ baobab (GUI Disk Usage Analyzer)

For desktops only.

---

# 📌 9. LVM Disk Space Monitoring

### ✔ Show LVM volumes

```
lvs
```

### ✔ Show volume groups

```
vgs
```

### ✔ Show physical volumes

```
pvs
```

---

# 📌 10. Disk Health Check – SMART Monitoring

Install:

```
sudo apt install smartmontools
```

Run SMART test:

```
sudo smartctl -a /dev/sda
```

---

# 📌 11. Real DevOps Use Cases

### ✔ Docker consuming disk:

```
du -sh /var/lib/docker/
```

Cleanup:

```
docker system prune -a
```

### ✔ Kubernetes node disk pressure

```
df -h
journalctl -u kubelet
```

### ✔ Jenkins builds filling disk

```
du -sh /var/lib/jenkins/workspace
```

### ✔ Log rotation (automatic cleanup)

Check config:

```
/etc/logrotate.conf
/etc/logrotate.d/
```

---

# 📌 12. Alerts & Automation

### ✔ Cron job to monitor disk & send mail

```
*/10 * * * * df -h | mail -s "Disk Report" admin@example.com
```

### ✔ Alert if disk > 90%

```
[ $(df / | grep / | awk '{print $5}' | sed 's/%//') -gt 90 ] && echo "Disk almost full!"
```

---

# 📌 Summary

You learned how to:

* Monitor disk space (`df`, `du`)
* Find large files
* Clean logs
* Check inodes
* Analyze disk usage (`ncdu`)
* Monitor disk I/O (`iostat`)
* Handle DevOps scenarios

