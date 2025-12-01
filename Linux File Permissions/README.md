# Linux File Permissions – Complete README 

Linux file permissions control **who can read, write, or execute** a file or directory. 

---

# 📌 1. What Are File Permissions?

Every Linux file has three permission groups:

* **User (u)** → Owner of the file
* **Group (g)** → Members of the file’s group
* **Others (o)** → Everyone else

Each group can have:

* **r** → Read (4)
* **w** → Write (2)
* **x** → Execute (1)

---

# 📌 2. Viewing File Permissions

Run:

```
ls -l
```

Example output:

```
-rwxr-xr-- 1 user dev 120 script.sh
```

Meaning:

* `-` → regular file
* `rwx` → user: read, write, execute
* `r-x` → group: read, execute
* `r--` → others: read only

---

# 📌 3. Permission Values (Octal Method)

Read = 4
Write = 2
Execute = 1

Examples:

* `chmod 777 file`  → rwx rwx rwx
* `chmod 755 file`  → rwx r-x r-x
* `chmod 644 file`  → rw- r-- r--
* `chmod 600 file`  → rw- --- ---

---

# 📌 4. Changing Permissions – chmod

### ✔ Numeric mode

```
chmod 755 script.sh
```

### ✔ Symbolic mode

```
chmod u+x script.sh
chmod g-w file.txt
chmod o+r notes.txt
chmod a=r file
```

---

# 📌 5. Changing Ownership – chown / chgrp

### ✔ Change owner

```
sudo chown sajid file.txt
```

### ✔ Change owner and group

```
sudo chown sajid:devops file.txt
```

### ✔ Change only group

```
chgrp devops file.txt
```

---

# 📌 6. Directory Permissions

Directories behave differently:

* **r** → list files
* **w** → create/delete files
* **x** → enter the directory

Example:

```
chmod 755 /var/www
```

---

# 📌 7. Special Permissions

## **1️⃣ SUID (4xxx)** – Run with file owner's permission

```
chmod 4755 /usr/bin/passwd
```

Shows as `rws`.

## **2️⃣ SGID (2xxx)** – New files inherit group

```
chmod 2755 /shared
```

## **3️⃣ Sticky Bit (1xxx)** – Only owner can delete

Used in `/tmp`.

```
chmod 1777 /shared
```

Shows as: `drwxrwxrwt`

---

# 📌 8. ACL Permissions (Advanced)

### ✔ Set ACL

```
setfacl -m u:sajid:rwx file.txt
```

### ✔ View ACL

```
getfacl file.txt
```

---

# 📌 9. Practical DevOps Use Cases

### ✔ Secure SSH keys

```
chmod 600 ~/.ssh/id_rsa
```

### ✔ Fix permissions for web apps

```
sudo chown -R www-data:www-data /var/www
chmod -R 755 /var/www
```

### ✔ Shared team folder

```
chgrp devops /team
chmod 770 /team
```

---

# 📌 10. Common Permission Issues

### ❌ "Permission denied"

Check:

```
ls -ld folder
```

Fix:

```
chmod +x script.sh
```

### ❌ Wrong owner

```
sudo chown user:group file
```

---

# 📌 Summary

You learned:

* User/group/other permissions
* Octal & symbolic chmod
* chown & chgrp
* Special permissions (SUID, SGID, Sticky Bit)
* ACLs
* Real DevOps use cases


