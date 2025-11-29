# Linux Basic Commands – README

This README contains the most important **Linux basic commands** with simple explanations and examples. Perfect for beginners and DevOps learners.

---

## 📌 1. pwd (Print Working Directory)

Shows the directory you are currently in.

```bash
pwd
```

Output example:

```
/home/user
```

---

## 📌 2. ls (List Files)

Displays files and folders in the current directory.

```bash
ls
ls -l   # long listing
ls -a   # show hidden files
```

---

## 📌 3. cd (Change Directory)

Used to move between directories.

```bash
cd /home
cd ..      # go back
cd ~       # go to home directory
```

---

## 📌 4. mkdir (Create Directory)

Creates a new folder.

```bash
mkdir projects
```

---

## 📌 5. rmdir / rm (Remove Files or Directories)

Remove files or directories.

```bash
rm file.txt
rm -rf foldername
```

⚠️ `rm -rf` is dangerous — deletes without confirmation.

---

## 📌 6. touch (Create Empty File)

```bash
touch file.txt log.txt
```

---

## 📌 7. cat (View File Content)

```bash
cat file.txt
```

---

## 📌 8. nano / vim (Edit Files)

```bash
nano notes.txt
vim config.ini
```

---

## 📌 9. mv (Move or Rename Files)

```bash
mv file.txt backup/
mv oldname.txt newname.txt
```

---

## 📌 10. cp (Copy Files)

```bash
cp file.txt backup/
cp -r folder1 folder2
```

---

## 📌 11. echo (Print Text)

```bash
echo "Hello World"
```

Write text into a file:

```bash
echo "Linux notes" > notes.txt
```

---

## 📌 12. head & tail (View First/Last Lines)

```bash
head file.txt
tail file.txt
```

---

## 📌 13. grep (Search in Files)

```bash
grep "error" logfile.log
grep -i "warning" *.txt
```

---

## 📌 14. chmod (Change Permissions)

```bash
chmod 755 script.sh
chmod 600 secrets.txt
```

---

## 📌 15. chown (Change File Owner)

```bash
sudo chown user:user file.txt
```

---

## 📌 16. whoami (Show Current User)

```bash
whoami
```

---

## 📌 17. uname (System Information)

```bash
uname -a
```

---

## 📌 18. top (Process Monitoring)

```bash
top
```

---

## 📌 19. ps (Show Running Processes)

```bash
ps aux
```

---

## 📌 20. df & du (Disk Usage)

```bash
df -h    # disk space
du -sh * # folder sizes
```

---

## 📌 21. history (Show Previous Commands)

```bash
history
```

---

## 📌 22. clear (Clear Screen)

```bash
clear
```

---

## ✔ Summary

These are the most commonly used Linux commands for beginners and DevOps engineers. Practice them daily to become comfortable using Linux.
