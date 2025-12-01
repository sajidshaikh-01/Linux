# Linux Process Management – Complete README

Process management is one of the most important skills in Linux. Every program running on a Linux system is a **process**.
---

# 📌 1. What Is a Process?

A process is a running instance of a program.

Each process has:

* **PID (Process ID)**
* **PPID (Parent Process ID)**
* **USER (Owner)**
* **STATE (Running, Sleeping, Stopped)**
* **CPU/Memory usage**

---

# 📌 2. View Running Processes

### ✔ `ps` – Current processes

```
ps
```

### ✔ Detailed list

```
ps aux
```

### ✔ Filter by process name

```
ps aux | grep nginx
```

### ✔ Tree view of processes

```
ps -ef --forest
```

---

# 📌 3. Real-Time Monitoring

### ✔ `top` – Interactive monitoring

```
top
```

### ✔ `htop` – Enhanced top (recommended)

Install:

```
sudo apt install htop
```

Run:

```
htop
```

---

# 📌 4. Find Process IDs (PID)

### ✔ Using pgrep

```
pgrep nginx
```

### ✔ Show process name + PID

```
pgrep -l ssh
```

---

# 📌 5. Kill Processes

### ✔ Kill by PID

```
kill 1234
```

### ✔ Force kill

```
kill -9 1234
```

### ✔ Kill by name

```
pkill nginx
```

---

# 📌 6. Start, Stop, Restart Services (systemd)

### ✔ Check service status

```
systemctl status nginx
```

### ✔ Start service

```
systemctl start nginx
```

### ✔ Stop service

```
systemctl stop nginx
```

### ✔ Restart service

```
systemctl restart nginx
```

### ✔ Enable auto-start on boot

```
systemctl enable nginx
```

---

# 📌 7. Background & Foreground Processes

### ✔ Run a program in background

```
command &
```

### ✔ Bring process to foreground

```
fg
```

### ✔ List background jobs

```
jobs
```

### ✔ Move foreground job to background

```
Ctrl + Z
bg
```

---

# 📌 8. Process Priority (nice & renice)

### ✔ Start a process with low priority

```
nice -n 10 script.sh
```

### ✔ Change priority of running process

```
renice 5 -p 1234
```

Priority range:

* -20 = highest
* 19 = lowest

---

# 📌 9. Check System Resource Usage

### ✔ CPU usage

```
uptime
```

### ✔ Memory usage

```
free -h
```

### ✔ Disk I/O

```
iostat
```

---

# 📌 10. Debugging Stuck or Hungry Processes

### ✔ Check top CPU processes

```
top -o %CPU
```

### ✔ Check top memory processes

```
top -o %MEM
```

### ✔ View logs

```
journalctl -xe
```

### ✔ Trace a running process

```
strace -p 1234
```

---

# 📌 11. Practical DevOps Use Cases

### ✔ Restart crashed services

```
systemctl restart docker
```

### ✔ Check podman/docker processes

```
ps aux | grep containerd
```

### ✔ Troubleshoot high CPU usage

```
top
iostat
journalctl -xe
```

### ✔ Run long tasks in background via nohup

```
nohup backup.sh &
```

### ✔ Monitor Jenkins / Kubernetes processes

```
ps aux | grep jenkins
ps aux | grep kubelet
```

---

# 📌 Summary

You learned:

* How to view processes
* Real-time monitoring tools
* Killing and controlling processes
* Systemd services
* Priorities (nice/renice)
* DevOps practical commands

