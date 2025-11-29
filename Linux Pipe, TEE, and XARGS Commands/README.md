# Linux Pipe, TEE, and XARGS Commands – README

This README explains how to use **Pipes (`|`)**, the **`tee` command**, and the **`xargs` command** in Linux with simple examples. These commands are very important for **DevOps, shell scripting, automation, and command chaining**.

---

# 📌 1. What is a Pipe (`|`) in Linux?

A **pipe** (`|`) takes the output of one command and sends it as input to another command.

### ✔ Syntax

```
command1 | command2
```

### ✔ Example: Show only lines containing "error"

```
cat logfile.txt | grep "error"
```

### ✔ Example: Count number of files

```
ls | wc -l
```

### ✔ Example: Sort and remove duplicates

```
cat names.txt | sort | uniq
```

Pipes help you **combine multiple commands efficiently**.

---

# 📌 2. The `tee` Command

`tee` reads input from standard input and writes output to **both screen and file**.

### ✔ Syntax

```
command | tee filename
```

### ✔ Example: Save output to a file *and* show on screen

```
ls | tee output.txt
```

### ✔ Append output instead of overwriting

```
ls | tee -a log.txt
```

### ✔ Send output through multiple pipes

```
cat file.txt | tee backup.txt | grep "hello"
```

### ✔ Use tee with sudo

```
echo "export PATH=/usr/local/bin:$PATH" | sudo tee -a /etc/profile
```

`sudo` normally doesn’t work with `>>`, so `tee` helps.

---

# 📌 3. The `xargs` Command

`xargs` converts **input into arguments** for another command.
Useful when commands do not accept piped input directly.

### ✔ Basic Syntax

```
command1 | xargs command2
```

---

## 📌 `xargs` Examples

### ✔ Example 1: Delete files listed in a file

```
cat files.txt | xargs rm
```

### ✔ Example 2: Search for a word in multiple files

```
ls *.log | xargs grep "error"
```

### ✔ Example 3: Create multiple directories

```
echo "dev test prod" | xargs mkdir
```

### ✔ Example 4: Download multiple URLs

```
cat urls.txt | xargs wget
```

### ✔ Example 5: Limit number of parallel jobs

```
cat files.txt | xargs -n 1 -P 4 rm
```

* `-n 1` → one argument per command
* `-P 4` → four parallel processes

---

# 📌 When to Use What?

| Feature | Pipe (`|`) | `tee` | `xargs` |
|---------|-----------|-------|----------|
| Combine commands | ✔ | ❌ | ✔ |
| Show & save output at same time | ❌ | ✔ | ❌ |
| Convert input to arguments | ❌ | ❌ | ✔ |
| Needed when command cannot read from pipe | ❌ | ❌ | ✔ |

---

# 📌 Summary

* **Pipe (`|`)** connects commands together.
* **`tee`** displays output while saving it to file.
* **`xargs`** builds and executes commands using input.

These commands are used in:

* Automation scripts
* DevOps pipelines
* Kubernetes/YAML processing
* Log processing
* System administration

inations
* Real DevOps use cases (Docker, Kubernetes, logs, CI/CD)
