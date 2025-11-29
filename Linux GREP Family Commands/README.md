# Linux GREP Family Commands – README

This README covers **grep**, **egrep**, **fgrep**, **zgrep**, **pgrep**, and **pdfgrep** commands with explanations and examples. These commands are essential for text searching, log analysis, automation, and DevOps work.

---

# 📌 1. What is `grep`?

`grep` (Global Regular Expression Print) is used to **search text patterns** inside files.

### ✔ Basic Syntax

```
grep [options] "pattern" filename
```

### ✔ Example: Search "error" in a file

```
grep "error" logfile.txt
```

### ✔ Case-insensitive search

```
grep -i "error" logfile.txt
```

### ✔ Search recursively in directories

```
grep -r "error" /var/log
```

### ✔ Show line numbers

```
grep -n "error" logfile.txt
```

---

# 📌 2. What is `egrep`?

`egrep` = **Extended GREP**.

It supports extended regular expressions (ERE) like:

* `|` (OR)
* `+`
* `?`
* `{n}` repetitions

### ✔ Example: OR search

```
egrep "error|warning" logfile.txt
```

### ✔ Example: Search numbers

```
egrep "[0-9]+" file.txt
```

💡 Note: Modern Linux uses `grep -E` instead of `egrep`.

```
grep -E "error|warning" logfile.txt
```

---

# 📌 3. What is `fgrep`?

`fgrep` = **Fixed GREP**.
It searches **fixed text** (no regex), meaning special characters are ignored.

### ✔ Example

```
fgrep "a.b*c" myfile.txt
```

Searches for exact string `a.b*c`.

💡 Modern alternative:

```
grep -F "a.b*c" myfile.txt
```

---

# 📌 4. What is `zgrep`?

`zgrep` is used to search inside **compressed .gz files** without unzipping.

### ✔ Example: Search inside compressed logs

```
zgrep "error" app.log.gz
```

### ✔ Recursive for compressed files

```
zgrep -r "timeout" /var/log
```

---

# 📌 5. What is `pgrep`?

`pgrep` searches for **process names** instead of file content.

### ✔ Example: Find all nginx processes

```
pgrep nginx
```

### ✔ Show full details

```
pgrep -l nginx
```

### ✔ Kill a process using `pkill`

```
pkill nginx
```

---

# 📌 6. What is `pdfgrep`?

`pdfgrep` searches text inside **PDF files**.

### ✔ Example: Search keyword in a PDF

```
pdfgrep "error" report.pdf
```

### ✔ Case-insensitive search

```
pdfgrep -i "linux" ebook.pdf
```

### ✔ Search page number

```
pdfgrep -n "chapter" book.pdf
```

🔹 Install pdfgrep:

```
sudo apt install pdfgrep
```

---

# 📌 7. GREP Family Comparison Table

| Command             | Purpose               | Supports Regex | Use Case               |
| ------------------- | --------------------- | -------------- | ---------------------- |
| **grep**            | Search text in files  | Yes            | Logs, config files     |
| **egrep / grep -E** | Extended regex search | Yes (ERE)      | Complex patterns       |
| **fgrep / grep -F** | Fixed text search     | No             | Exact string match     |
| **zgrep**           | Search in .gz files   | Yes            | Compressed logs        |
| **pgrep**           | Search processes      | No             | Find running processes |
| **pdfgrep**         | Search inside PDFs    | Yes            | Books, PDFs            |

---

# 📌 8. Useful GREP Options

| Option | Description               |
| ------ | ------------------------- |
| `-i`   | Ignore case               |
| `-n`   | Show line numbers         |
| `-r`   | Recursive search          |
| `-v`   | Invert match              |
| `-c`   | Count matches             |
| `-w`   | Match whole word          |
| `-H`   | Show filename             |
| `-A 3` | Show 3 lines after match  |
| `-B 3` | Show 3 lines before match |
| `-C 3` | Show 3 lines around match |

---

# 📌 9. Practical DevOps Use Cases

### ✔ Check failures in CI/CD pipeline logs

```
grep -i "fail" /var/log/jenkins/jenkins.log
```

### ✔ Search Kubernetes pod logs

```
kubectl logs podname | grep "error"
```

### ✔ Search Docker container logs

```
docker logs myapp | grep -i "timeout"
```

### ✔ Find all YAML files containing `image:`

```
grep -r "image:" .
```

---

# 📌 Summary

This README explained the full GREP command family:

* **grep** – Basic search
* **egrep / grep -E** – Extended regex
* **fgrep / grep -F** – Fixed string
* **zgrep** – Search in .gz files
* **pgrep** – Search processes
* **pdfgrep** – Search inside PDFs

* Advanced regex examples
* A GREP cheat sheet PDF
