# Linux Environment Variables – Complete README

Environment variables are key-value pairs used by the Linux shell and applications to store configuration values. They are heavily used in **DevOps, scripting, CI/CD pipelines, Docker, Kubernetes, and application configuration**.

---

# 📌 1. What Are Environment Variables?

Environment variables store information that can be used by:

* Shell sessions
* Programs and scripts
* System services
* DevOps tools (Docker, Ansible, Terraform, Jenkins, etc.)

Example values include:

* Username
* Shell type
* System paths
* API keys
* Configuration settings

---

# 📌 2. View Environment Variables

### ✔ View all env variables

```
env
```

OR

```
printenv
```

### ✔ View a single variable

```
echo $HOME
echo $USER
echo $PATH
```

---

# 📌 3. Common Environment Variables

| Variable    | Description                                   |
| ----------- | --------------------------------------------- |
| `$HOME`     | User home directory                           |
| `$USER`     | Logged-in username                            |
| `$PATH`     | Directories where Linux searches for commands |
| `$SHELL`    | Shell type (bash, zsh)                        |
| `$PWD`      | Current directory                             |
| `$LANG`     | System language                               |
| `$EDITOR`   | Default text editor                           |
| `$HOSTNAME` | System hostname                               |
| `$LOGNAME`  | User login name                               |

---

# 📌 4. Create Environment Variables (Temporary)

Temporary variables last **only for the session**.

### ✔ Create a variable

```
MYVAR="hello"
```

### ✔ Access it

```
echo $MYVAR
```

### ✔ Delete it

```
unset MYVAR
```

---

# 📌 5. Export Variables

To make a variable available to **child processes**, export it.

```
export MYVAR="hello world"
```

Now every script or command in this session can access it.

---

# 📌 6. Permanent Environment Variables

### 1️⃣ Add to `.bashrc` (for the user)

```
vim ~/.bashrc
```

Add:

```
export MYVAR="permanent-value"
```

Apply:

```
source ~/.bashrc
```

### 2️⃣ Add to `/etc/environment` (system-wide)

```
sudo vim /etc/environment
```

Add:

```
MYVAR="systemwide-value"
```

---

# 📌 7. Remove an Environment Variable

```
unset MYVAR
```

To remove permanently → delete it from `.bashrc` or `/etc/environment`.

---

# 📌 8. Special Variables in Shell Scripts

| Variable      | Meaning                     |
| ------------- | --------------------------- |
| `$0`          | Script name                 |
| `$1, $2, ...` | Arguments                   |
| `$#`          | Number of arguments         |
| `$@`          | All arguments               |
| `$$`          | Process ID of shell         |
| `$?`          | Exit status of last command |

Example:

```
echo "First argument: $1"
```


# 📌 10. PATH Variable

`$PATH` is one of the most important variables. It controls where Linux looks for commands.

### ✔ View PATH

```
echo $PATH
```

### ✔ Add a directory to PATH

```
export PATH=$PATH:/usr/local/bin
```

Permanent:
Add to `.bashrc`:

```
export PATH="$PATH:/usr/local/bin"
```

---

# 📌 11. Load Variables From a File

### ✔ Example `.env` file

```
USERNAME=admin
PASSWORD=Secret123
```

### ✔ Load the file

```
source .env
```

---

# 📌 12. Check Exit Status Using `$?`

Shows if last command succeeded.

```
command
echo $?
```

* `0` → success
* Non‑zero → error

---

# 📌 Summary

Environment variables help manage configuration, automate scripts, and control system behavior.
