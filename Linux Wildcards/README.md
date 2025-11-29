# Linux Wildcards – Complete README

Linux **wildcards** are special characters that help match **file names, patterns, and text** without typing full names. They are extremely useful in automation, scripting, DevOps, and daily Linux usage.

This README covers all wildcard types with examples.

---

# 📌 1. What Are Wildcards?

Wildcards are symbols used in Linux shell to **match multiple files or patterns**. They are used with commands like:

* `ls`
* `cp`
* `mv`
* `rm`
* `find`
* `grep`
* `tar`

---

# 📌 2. Types of Wildcards

## **1️⃣ Asterisk (*) – Match Zero or More Characters**

The most common wildcard.

### ✔ Examples

Match all files:

```
ls *
```

Match all `.txt` files:

```
ls *.txt
```

Match all files starting with "log":

```
ls log*
```

Match everything in current folder:

```
rm -rf *
```

⚠️ Dangerous – use carefully!

---

## **2️⃣ Question Mark (?) – Match Exactly One Character**

### ✔ Examples

Match files like `a1.txt`, `a2.txt`, but not `a10.txt`:

```
ls a?.txt
```

Match files with exactly 3 letters:

```
ls ???
```

---

## **3️⃣ Square Brackets ([]) – Match a Range or Set**

### ✔ Match specific characters

```
ls file[123].txt
```

Matches:

* file1.txt
* file2.txt
* file3.txt

### ✔ Match a range of letters

```
ls file[a-d].txt
```

### ✔ Match digits 0–9

```
ls file[0-9].txt
```

---

## **4️⃣ Negated Brackets ([!]) – Exclude Characters**

```
ls file[!1-3].txt
```

Matches all files except file1.txt, file2.txt, file3.txt.

---

## **5️⃣ Curly Braces ({}) – Brace Expansion (Not Exactly Wildcards)**

Used to generate multiple strings.

### ✔ Create multiple files

```
touch file{1..5}.txt
```

### ✔ Create multiple directories

```
mkdir env_{dev,stage,prod}
```

### ✔ Combine patterns

```
cp *.txt{,.bak}
```

Copies: file.txt → file.txt.bak

---

# 📌 3. Practical Wildcard Use Cases

### ✔ 1. Remove all log files

```
rm *.log
```

### ✔ 2. Copy all configuration files

```
cp /etc/*.conf /backup/
```

### ✔ 3. Move all PNG + JPG files

```
mv *.{png,jpg} images/
```

### ✔ 4. Find all YAML or JSON files

```
ls *.{yaml,yml,json}
```

### ✔ 5. Delete files starting with temp

```
rm temp*
```

### ✔ 6. List files with exactly 4 characters

```
ls ????
```

---

# 📌 4. Wildcards With GREP

Search for all `.log` files containing "error":

```
grep "error" *.log
```

Search all `.txt` files starting with letter `a`:

```
grep "hello" a*.txt
```

---

# 📌 5. Wildcards With FIND

Find all `.sh` files:

```
find . -name "*.sh"
```

Find files ending with number:

```
find . -name "*.[0-9]"
```

---

# 📌 6. Wildcards With TAR

Compress only `.txt` and `.log` files:

```
tar -czf backup.tar.gz *.{txt,log}
```

---

# 📌 7. Important Notes

* Wildcards are expanded **by the shell**, not by Linux commands.
* `{}` (brace expansion) is NOT a wildcard.
* Wildcards DO NOT work inside single quotes `' '`.

---

# 📌 Summary

Linux wildcards help you:

* Work faster
* Manage files efficiently
* Automate repeating tasks
* Combine patterns in DevOps

