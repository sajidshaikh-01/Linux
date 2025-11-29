# Linux Redirects – Complete README

Linux **input/output redirection** allows you to control where command output goes and where input comes from. Redirects are used heavily in **DevOps, scripting, automation, logging, and pipelines**.

This README explains all redirects with examples.

---

# 📌 1. What Are Redirects?

Redirects allow you to:

* Send output to a file
* Read input from a file
* Append data
* Redirect errors
* Combine output and errors

Redirects use special symbols:

```
>   >>   <   2>   2>&1   &>   <<<
```

---

# 📌 2. Output Redirection `>`

Sends output **to a file**, overwriting existing content.

### ✔ Example

```
echo "Hello" > output.txt
```

### ✔ Overwrite file with command output

```
ls > files.txt
```

---

# 📌 3. Append Using `>>`

Appends to a file **without overwriting**.

### ✔ Example

```
echo "New line" >> output.txt
```

---

# 📌 4. Input Redirection `<`

Takes input **from a file** instead of keyboard.

### ✔ Example

```
sort < names.txt
```

---

# 📌 5. Redirect Errors Using `2>`

`2>` redirects **stderr (error output)**.

### ✔ Example

```
ls /wrong/path 2> error.log
```

---

# 📌 6. Redirect Only Standard Output `1>`

`1>` redirects normal output.

```
command 1> output.txt
```

Equivalent to:

```
command > output.txt
```

---

# 📌 7. Redirect Both Output + Errors

## **Method 1: `&>`**

```
command &> all.log
```

## **Method 2: `> file 2>&1`**

```
command > all.log 2>&1
```

## **Method 3: Append both**

```
command >> all.log 2>&1
```

---

# 📌 8. Here String `<<<`

Sends simple text as input.

### ✔ Example

```
grep "hello" <<< "hello world"
```

---

# 📌 9. Here Document `<<`

Used to pass multiline input.

### ✔ Example

```
cat << EOF > message.txt
This is line 1
This is line 2
EOF
```

---

# 📌 10. Practical DevOps Use Cases

### ✔ 1. Save logs while running commands

```
kubectl get pods > pods.log
```

### ✔ 2. Store errors separately

```
docker build . 2> build_errors.log
```

### ✔ 3. Combine output + errors in CI/CD

```
terraform apply > output.log 2>&1
```

### ✔ 4. Append timestamps to log files

```
date >> deploy.log
```

### ✔ 5. Provide input automatically for scripts

```
./install.sh < answers.txt
```

### ✔ 6. Generate configuration files using here-doc

```
cat << EOF > config.yaml
version: 1
name: example
EOF
```

### ✔ 7. Process parameters in automation

```
bash script.sh <<< "username"
```

---

# 📌 11. Summary

| Redirect | Meaning                        |
| -------- | ------------------------------ |
| `>`      | Redirect output (overwrite)    |
| `>>`     | Append output                  |
| `<`      | Redirect input                 |
| `2>`     | Redirect errors                |
| `&>`     | Redirect both output and error |
| `2>&1`   | Merge stderr → stdout          |
| `<<`     | Here Document                  |
| `<<<`    | Here String                    |

---

