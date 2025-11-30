# Linux Hard Links & Soft Links – Complete README

Links in Linux allow multiple filenames to point to the same file or data. They are essential concepts for DevOps, file management, backups, and understanding Unix internals.

This README explains **hard links**, **soft (symbolic) links**, differences, commands, and practical use cases.

---

# 📌 1. What Are Links in Linux?

Links are pointers or references to files.
Two types:

* **Hard Link** → Points to the *same inode* (actual data)
* **Soft Link (Symbolic Link)** → Points to *another filename*

---

# 📌 2. What Is a Hard Link?

A **hard link** is an exact copy of a file reference. Both filenames point to the same inode.

### ✔ Create a Hard Link

```
ln original.txt hardlink.txt
```

### ✔ Verify inode numbers (same inode = hard link)

```
ls -li
```

### ✔ Properties of Hard Links

* Same inode as original file
* Both files share the same data
* Deleting the original file does NOT delete the hard link
* Cannot link directories
* Cannot link across different file systems

---

# 📌 3. What Is a Soft Link (Symbolic Link)?

A **soft link / symlink / symbolic link** is like a shortcut pointing to the original file.

### ✔ Create a Soft Link

```
ln -s original.txt symlink.txt
```

### ✔ Verify (symlink shows →)

```
ls -l
```

Example output:

```
symlink.txt -> original.txt
```

### ✔ Properties of Soft Links

* Different inode than original file
* Points to filename, not the data
* If original file is deleted, symlink becomes broken
* Can link directories
* Can link across file systems

---

# 📌 4. Hard Link vs Soft Link (Summary Table)

| Feature                    | Hard Link        | Soft Link |
| -------------------------- | ---------------- | --------- |
| Inode                      | Same as original | Different |
| Points to                  | File data        | Filename  |
| Breaks if original removed | ❌ No             | ✔ Yes     |
| Can link directories       | ❌ No             | ✔ Yes     |
| Cross filesystem support   | ❌ No             | ✔ Yes     |
| Shows arrow (`->`)         | ❌ No             | ✔ Yes     |

---

# 📌 5. Commands for Working With Links

### ✔ Check inode numbers

```
ls -li
```

### ✔ Create hard link

```
ln file1 file2
```

### ✔ Create soft link

```
ln -s file1 symlink
```

### ✔ Remove a link

```
rm linkname
```

### ✔ Find all symlinks

```
find . -type l
```

### ✔ Show where a symlink points

```
readlink symlinkname
```

---

# 📌 6. Practical Use Cases

### ✔ 1. Multiple names for the same file (hard links)

Useful in log rotation or backups:

```
ln logfile.log current.log
```

### ✔ 2. Shortcut to long paths (symlinks)

```
ln -s /var/www/html/ /webroot
```

### ✔ 3. Kubernetes, Docker config linking

```
ln -s /etc/myapp/config.yaml config.yaml
```

### ✔ 4. Version switching (symlinks)

```
ln -s /opt/java/jdk17 java
```

Change version:

```
ln -sf /opt/java/jdk21 java
```

### ✔ 5. Backups (hard links keep data safe)

```
ln important.txt backup_copy.txt
```

Even if original is deleted, data stays.

---

# 📌 7. Identify Broken Symlinks

```
find . -xtype l
```


