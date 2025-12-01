# Linux Job Scheduling – Complete README

Job scheduling in Linux allows you to **automate tasks**, run commands at specific times, repeat jobs, and manage background processes. 
---

# 📌 1. What Is Job Scheduling?

Job scheduling lets you run commands automatically:

* Daily
* Weekly
* Monthly
* At system boot
* Every X minutes
* One-time future execution

Linux provides 4 main tools:

* **cron** – recurring jobs
* **crontab** – user-specific cron jobs
* **at** – one-time jobs
* **anacron** – run scheduled jobs even if the system was down
* **systemd timers** – modern alternative to cron

---

# 📌 2. Cron & Crontab

`cron` is the most used scheduler for recurring tasks.

### ✔ Edit crontab

```
crontab -e
```

### ✔ List cron jobs

```
crontab -l
```

### ✔ Remove cron jobs

```
crontab -r
```

---

# 📌 3. Cron Syntax (VERY IMPORTANT)

```
* * * * * command
| | | | |
| | | | └── Day of week (0–6)
| | | └──── Month (1–12)
| | └────── Day of month (1–31)
| └──────── Hour (0–23)
└────────── Minute (0–59)
```

### ✔ Examples

Run a script at **2:30 AM daily**:

```
30 2 * * * /home/user/backup.sh
```

Run every **5 minutes**:

```
*/5 * * * * /home/user/task.sh
```

Run every **Sunday at 8 PM**:

```
0 20 * * 0 /scripts/report.sh
```

Run twice every day (at 10 AM & 6 PM):

```
0 10,18 * * * /home/user/cleanup.sh
```

---

# 📌 4. Cron Special Keywords

| Keyword    | Meaning        |
| ---------- | -------------- |
| `@reboot`  | Run at startup |
| `@yearly`  | Once per year  |
| `@monthly` | Once per month |
| `@weekly`  | Once per week  |
| `@daily`   | Once per day   |
| `@hourly`  | Once per hour  |

### ✔ Example

Run script on boot:

```
@reboot /usr/bin/python3 /home/user/app.py
```

---

# 📌 5. Cron Logs (DEBUGGING)

Check cron logs:

```
tail -f /var/log/syslog
```

OR

```
grep CRON /var/log/syslog
```

---

# 📌 6. at Command – One-Time Scheduling

`at` is used for running a command **one time in the future**.

### ✔ Install (if not available)

```
sudo apt install at
```

### ✔ Schedule a task

```
at 5pm
```

Then type commands → press `Ctrl + D`.

### ✔ Schedule for tomorrow

```
at 10am tomorrow
```

### ✔ List at jobs

```
atq
```

### ✔ Remove an at job

```
at -d <jobid>
```

---

# 📌 7. anacron – Run Cron Jobs Even If System Was Off

Used mainly on laptops or systems not running 24/7.

### ✔ anacron jobs file

```
/etc/anacrontab
```

### ✔ Example: Run daily task with delay

```
1 5 backup.daily /home/user/backup.sh
```

Meaning:

* Every 1 day
* Wait 5 minutes after boot

---

# 📌 8. systemd Timers (Modern Alternative)

Timers are more reliable than cron.

### ✔ Create a systemd service `/etc/systemd/system/backup.service`

```
[Unit]
Description=Daily Backup

[Service]
ExecStart=/home/user/backup.sh
```

### ✔ Create a timer `/etc/systemd/system/backup.timer`

```
[Unit]
Description=Runs backup daily

[Timer]
OnCalendar=daily
Persistent=true

[Install]
WantedBy=timers.target
```

### ✔ Start timer

```
systemctl start backup.timer
systemctl enable backup.timer
```

### ✔ Check timers

```
systemctl list-timers
```

---

# 📌 9. Practical DevOps Use Cases

### ✔ Automatic log cleanup every night

```
0 1 * * * find /var/log -name "*.log" -mtime +7 -delete
```

### ✔ Restart Docker if crashed

```
*/10 * * * * systemctl restart docker
```

### ✔ Backup database weekly

```
0 2 * * 0 /scripts/db_backup.sh
```

### ✔ Pull latest code every hour

```
0 * * * * cd /app && git pull
```

### ✔ Delete temp files every 6 hours

```
0 */6 * * * rm -rf /tmp/*
```

### ✔ Kubernetes node log rotation (with cronjob)

Used in clusters to clean logs.

---

# 📌 10. Common Cron Issues & Fixes

### ❌ Cron not working → Script missing shebang

Add at top:

```
#!/bin/bash
```

### ❌ Script needs full paths

Cron does not use user PATH. Use full paths:

```
/usr/bin/python3 /home/user/app.py
```

### ❌ Permissions issue

```
chmod +x script.sh
```

---

# 📌 Summary

You learned:

* Cron, at, anacron, timers
* Crontab syntax
* Special keywords
* Debugging cron jobs
* Real DevOps automation tasks

🔥 A cron + systemd comparison chart
