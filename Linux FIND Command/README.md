# Linux FIND Command – Complete README

The **`find`** command is one of the most powerful Linux utilities used to **search files and directories** based on name, size, permissions, type, time, and more. This README includes explanations + practical DevOps use cases.

---

# 📌 1. Basic Syntax of `find`

```
find [path] [options] [expression]
```

Example:

```
find /home -name "file.txt"
```

---

# 📌 2. Search by Filename

### ✔ Search by exact name

```
find . -name "file.txt"
```

### ✔ Case-insensitive search

```
find . -iname "file.txt"
```

### ✔ Search multiple extensions

```
find . -name "*.log" -o -name "*.txt"
```

---

# 📌 3. Search by File Type

### ✔ Only files

```
find . -type f
```

### ✔ Only directories

```
find . -type d
```

---

# 📌 4. Search by Size

### ✔ Files greater than 10MB

```
find . -size +10M
```

### ✔ Files less than 1KB

```
find . -size -1k
```

### ✔ Between 1MB and 10MB

```
find . -size +1M -size -10M
```

---

# 📌 5. Search by Time

### ✔ Modified in last 1 day

```
find . -mtime -1
```

### ✔ Modified more than 7 days ago

```
find . -mtime +7
```

### ✔ Accessed in last 5 days

```
find . -atime -5
```

### ✔ Changed permissions in last 2 days

```
find . -ctime -2
```

---

# 📌 6. Search by Permissions

### ✔ Files with 777 permission

```
find . -perm 777
```

### ✔ Files writable by others

```
find /var/www -perm -o=w
```

### ✔ Files with permission 644

```
find . -perm 644
```

---

# 📌 7. Search & Execute Commands Using `-exec`

### ✔ Delete files

```
find . -name "*.tmp" -exec rm -f {} \;
```

### ✔ Change file permissions

```
find . -type f -name "*.sh" -exec chmod +x {} \;
```

### ✔ Copy all `.conf` files

```
find /etc -name "*.conf" -exec cp {} /backup \;
```

---

# 📌 8. Search & Replace Using `-exec` + `sed`

```
find . -type f -name "*.yaml" -exec sed -i 's/old/new/g' {} \;
```

Useful for Kubernetes YAML automation.

---

# 📌 9. Search With `-delete` (Safe Delete)

### ✔ Delete all `.log` files

```
find . -name "*.log" -delete
```

### ✔ Delete empty directories

```
find . -type d -empty -delete
```

⚠️ Be very careful when using `-delete`.

---

# 📌 10. Practical DevOps Use Cases

### ✔ 1. Find large files consuming disk space

```
find / -type f -size +100M
```

Useful in fixing "disk full" issues.

### ✔ 2. Find Docker/Kubernetes logs bigger than 50MB

```
find /var/lib/docker -size +50M
```

### ✔ 3. Find all YAML files in a project

```
find . -name "*.yaml" -o -name "*.yml"
```

### ✔ 4. Delete old log files (older than 7 days)

```
find /var/log -name "*.log" -mtime +7 -delete
```

### ✔ 5. Fix permissions on `.sh` scripts

```
find . -name "*.sh" -exec chmod +x {} \;
```

### ✔ 6. Search for configuration files across Linux

```
find / -type f -name "*.conf"
```

### ✔ 7. Find processes logs modified recently

```
find /var/log -name "*.log" -mtime -1
```

### ✔ 8. Backup all `.conf` files

```
find /etc -name "*.conf" -exec cp {} /backup/conf \;
```

---

# 📌 11. Combining FIND with GREP (Powerful)

### ✔ Search inside all `.log` files for "error"

```
find . -name "*.log" -exec grep -i "error" {} \;
```

---

# 📌 Summary

The `find` command helps locate files by:

* Name
* Size
* Type
* Permissions
* Time
* Content (with grep)

It is heavily used in DevOps for logs, automation, YAML management, cleanup tasks, and debugging.

