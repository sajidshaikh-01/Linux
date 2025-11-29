# Linux Tips & Tricks – Improve Your Productivity 🚀

This README contains powerful **Linux tips, shortcuts, tools, and time‑saving tricks** used by DevOps engineers, system admins, cloud engineers, and power users.

Mastering these will **significantly boost your speed** on any Linux machine.

---

# 📌 1. Use `!!` to Repeat Last Command

Run your last command again:

```
!!
```

Run last command with sudo:

```
sudo !!
```

Huge time-saver!

---

# 📌 2. Use Arrow Keys to Search Command History

Search previous commands using:

```
Ctrl + r
```

Type a few letters and Linux will autocomplete matching commands.

---

# 📌 3. Quickly Go to Home Directory

```
cd ~
```

or simply:

```
cd
```

---

# 📌 4. Create Multiple Files or Folders at Once

```
touch file{1..5}.txt
mkdir project_{dev,test,prod}
```

---

# 📌 5. Check How Long Your System Has Been Running

```
uptime
```

---

# 📌 6. Find Running Processes Easily

```
ps aux | grep nginx
pgrep nginx
```

---

# 📌 7. Use `watch` to Monitor Commands in Real Time

```
watch df -h
watch kubectl get pods
```

---

# 📌 8. Use `htop` Instead of `top`

```
sudo apt install htop
htop
```

More readable, color-coded process viewer.

---

# 📌 9. Use `ncdu` to Find Disk Usage Quickly

Install:

```
sudo apt install ncdu
```

Run:

```
ncdu /
```

Perfect for analyzing disk issues.

---

# 📌 10. Use Aliases for Long Commands

Add to `~/.bashrc`:

```
alias k='kubectl'
alias ll="ls -la"
alias gs="git status"
```

Reload:

```
source ~/.bashrc
```

---

# 📌 11. Jump Between Directories Quickly

Go back to previous directory:

```
cd -
```

---

# 📌 12. Check Which Commands You Use the Most

```
history | awk '{print $2}' | sort | uniq -c | sort -nr | head
```

---

# 📌 13. Use `tar` to Compress/Extract Like a Pro

Compress:

```
tar -czvf backup.tar.gz folder/
```

Extract:

```
tar -xzvf backup.tar.gz
```

---

# 📌 14. Check Open Ports

```
ss -tulnp
```

---

# 📌 15. Use `CTRL` Shortcuts

| Shortcut   | Action                    |
| ---------- | ------------------------- |
| `Ctrl + c` | Stop command              |
| `Ctrl + z` | Pause command             |
| `Ctrl + d` | Logout / end input        |
| `Ctrl + a` | Go to beginning of line   |
| `Ctrl + e` | Go to end of line         |
| `Ctrl + k` | Delete until end of line  |
| `Ctrl + u` | Delete from start of line |
| `Ctrl + r` | Reverse search history    |

---

# 📌 16. Use `df -h` and `du -sh` Together

Disk free:

```
df -h
```

Folder usage:

```
du -sh *
```

---

# 📌 17. Use `xargs` for Bulk Operations

Delete files listed in file:

```
cat files.txt | xargs rm
```

---

# 📌 18. Use `tee` to View + Save Output

```
ls -l | tee output.txt
```

---

# 📌 19. Use Wildcards Smartly

Remove all `.log` files:

```
rm *.log
```

Copy all `.yaml` files:

```
cp *.yaml /backup
```

---

# 📌 20. Create Strong Passwords

```
openssl rand -base64 16
```

---

# 📌 21. to see the commands what you wrote in past
```
control+r
```

---

# 📌 22. for calculater
```
bc -l
```

---

# 📌 Summary – You Will Work Faster If You Use:

* `!!` and `Ctrl + r` for command history
* Aliases for shortcuts
* `htop`, `ncdu`, `watch` for better monitoring
* Wildcards + xargs + tee
* Keyboard shortcuts to fly through the terminal

ctivity hacks
🔥 A professional Linux cheat sheet PDF
