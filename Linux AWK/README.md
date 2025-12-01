# Linux AWK – Complete README

`awk` is one of the most powerful text-processing tools in Linux. It is used for **searching, filtering, formatting, and data extraction**. 
---

# 📌 1. What Is AWK?

`awk` is a scripting language used for:

* Processing text files
* Extracting specific columns
* Filtering rows by patterns
* Performing calculations
* Generating formatted reports

AWK reads input **line-by-line** and splits each line into **fields**.

Default field separator = **space/tab**.

---

# 📌 2. Basic Syntax

```
awk 'pattern { action }' file
```

Example:

```
awk '{print}' file.txt
```

Prints every line.

---

# 📌 3. Print Specific Columns

### ✔ Print 1st column

```
awk '{print $1}' data.txt
```

### ✔ Print 2nd and 4th column

```
awk '{print $2, $4}' file
```

### ✔ Print last column

```
awk '{print $NF}' file
```

### ✔ Print second last column

```
awk '{print $(NF-1)}' file
```

---

# 📌 4. Using Field Separator

### ✔ Change separator to colon (`:`)

```
awk -F ':' '{print $1, $3}' /etc/passwd
```

### ✔ Separator as comma

```
awk -F ',' '{print $2}' file.csv
```

---

# 📌 5. Conditions / Filtering

### ✔ Print lines containing 'error'

```
awk '/error/' logfile.log
```

### ✔ Print lines where 3rd column > 50

```
awk '$3 > 50 {print}' file
```

### ✔ Print only if column 2 equals "active"

```
awk '$2 == "active"' users.txt
```

---

# 📌 6. BEGIN and END Blocks

### ✔ BEGIN runs before processing file

```
awk 'BEGIN {print "Start"} {print} END {print "Done"}' file
```

---

# 📌 7. Built‑in Variables

| Variable  | Description                 |
| --------- | --------------------------- |
| `$0`      | Entire line                 |
| `$1..$NF` | Column fields               |
| `NF`      | Number of fields            |
| `NR`      | Line number (record number) |
| `FS`      | Field separator             |
| `OFS`     | Output field separator      |

### ✔ Add line numbers

```
awk '{print NR, $0}' file
```

### ✔ Print number of columns

```
awk '{print NF}' file
```

---

# 📌 8. Arithmetic Operations in AWK

```
awk '{sum = $1 + $2; print sum}' file
```

### ✔ Sum of column 3

```
awk '{total += $3} END {print total}' file
```

---

# 📌 9. String Operations

### ✔ Convert to uppercase

```
awk '{print toupper($0)}' file
```

### ✔ Convert to lowercase

```
awk '{print tolower($1)}' file
```

---

# 📌 10. Format Output

```
awk '{printf "Name: %-10s Age: %s\n", $1, $2}' file
```

---

# 📌 11. AWK Scripts

Create a script:

```
vim script.awk
```

Add:

```
{ print $1, $3 }
```

Run:

```
awk -f script.awk file.txt
```

---

# 📌 12. Practical DevOps Use Cases

### ✔ Extract IP addresses from logs

```
awk '{print $1}' access.log
```

### ✔ Find memory usage from `free -m`

```
free -m | awk 'NR==2{print $3}'
```

### ✔ Check disk usage (`df -h`) for `/`

```
df -h | awk '$6 == "/" {print $5}'
```

### ✔ Parse Kubernetes logs in pipelines

```
kubectl logs pod | awk '/ERROR/ {print NR, $0}'
```

### ✔ Analyze Nginx access logs

```
awk '{print $9}' access.log | sort | uniq -c
```

---

# 📌 13. Summary

You learned:

* AWK basics: syntax, columns, patterns
* Using BEGIN/END
* Built-in variables
* Field separators
* Math/string operations
* Real DevOps use cases

