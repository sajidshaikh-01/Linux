# Linux SED – Complete README

`sed` (Stream Editor) is a powerful Linux command-line tool used for **searching, modifying, and transforming text**. 
# 📌 1. What Is SED?

`sed` is a **stream editor** that processes text **line-by-line** and performs operations like:

* Search and replace
* Delete lines
* Insert or append text
* Print specific lines
* Modify files automatically

---

# 📌 2. Basic Syntax

```
sed 'command' file
```

Or with multiple commands:

```
sed -e 'command1' -e 'command2' file
```

---

# 📌 3. Print Lines

### ✔ Print entire file

```
sed '' file
```

### ✔ Print specific line (line number)

```
sed -n '5p' file
```

### ✔ Print range of lines

```
sed -n '3,7p' file
```

---

# 📌 4. Search & Replace (MOST IMPORTANT)

### ✔ Replace first occurrence in each line

```
sed 's/old/new/' file
```

### ✔ Replace all occurrences

```
sed 's/old/new/g' file
```

### ✔ Case-insensitive replace

```
sed 's/old/new/gi' file
```

### ✔ Replace text in a specific line only

```
sed '5s/error/fixed/' file
```

### ✔ Replace in range

```
sed '3,6s/test/pass/g' file
```

---

# 📌 5. In-Place Editing (Modify File Directly)

### ✔ Save changes back to file

```
sed -i 's/old/new/g' file
```

### ✔ Create backup automatically

```
sed -i.bak 's/old/new/g' file
```

---

# 📌 6. Delete Lines

### ✔ Delete a specific line

```
sed '3d' file
```

### ✔ Delete a range of lines

```
sed '10,20d' file
```

### ✔ Delete lines containing a pattern

```
sed '/error/d' file
```

---

# 📌 7. Insert & Append Text

### ✔ Insert BEFORE a line

```
sed '3i This is inserted above line 3' file
```

### ✔ Append AFTER a line

```
sed '3a This is added below line 3' file
```

---

# 📌 8. Substitution with Variables (Bash)

Example using variables:

```
sed "s/$old/$new/g" file
```

---

# 📌 9. Using Patterns

### ✔ Replace only lines matching pattern

```
sed '/server/s/off/on/' config.txt
```

### ✔ Replace only if line starts with keyword

```
sed '/^NAME/ s/abc/xyz/' file
```

### ✔ Replace only if line ends with keyword

```
sed '/end$/ s/done/ok/' file
```

---

# 📌 10. Extracting Data with sed

### ✔ Extract numbers

```
echo "user123" | sed 's/[^0-9]//g'
```

### ✔ Extract specific text

```
echo "ID=456" | sed 's/.*=//'
```

---

# 📌 11. Useful sed Flags

| Flag | Meaning             |
| ---- | ------------------- |
| `g`  | global replace      |
| `i`  | case-insensitive    |
| `p`  | print matched lines |
| `d`  | delete              |
| `n`  | skip to next line   |
| `-i` | edit file in-place  |

---

# 📌 12. Practical DevOps Examples

### ✔ Replace image tag in Kubernetes YAML file

```
sed -i 's/tag: .*/tag: v2/' deployment.yaml
```

### ✔ Update Nginx config values

```
sed -i 's/listen 80/listen 8080/' /etc/nginx/sites-enabled/default
```

### ✔ Remove empty lines in logs

```
sed '/^$/d' logfile.log
```

### ✔ Mask sensitive info in logs

```
sed 's/password=.*/password=*****/' app.log
```

### ✔ Update environment variable values

```
sed -i 's/ENV=.*/ENV=prod/' .env
```


* In-place editing
* Real
