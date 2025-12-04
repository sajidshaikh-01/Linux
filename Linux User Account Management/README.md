# Linux User Account Management – Complete README

Linux user account management is essential for system administration, DevOps, security, and automation. 

---

# 📌 1. Where User & Group Information Is Stored

### ✔ User details

```
/etc/passwd
```

### ✔ Password hashes

```
/etc/shadow
```

### ✔ Group information

```
/etc/group
```

---

# 📌 2. Creating Users

### ✔ Create a simple user

```
sudo useradd sajid
```

### ✔ Create user with home directory

```
sudo useradd -m sajid
```

### ✔ Create user with custom shell

```
sudo useradd -m -s /bin/bash sajid
```

### ✔ Create user with full name

```
sudo useradd -m -c "Sajid Shaikh" sajid
```

---

# 📌 3. Setting & Changing Passwords

```
sudo passwd sajid
```

Password policies can be modified in:

```
/etc/login.defs
/etc/pam.d/common-password
```

---

# 📌 4. Deleting Users

### ✔ Remove user (keep home directory)

```
sudo userdel sajid
```

### ✔ Remove user + home directory

```
sudo userdel -r sajid
```

---

# 📌 5. Modifying Existing Users

### ✔ Change username

```
sudo usermod -l newname oldname
```

### ✔ Change home directory

```
sudo usermod -d /new/home user
```

### ✔ Lock user account

```
sudo usermod -L sajid
```

### ✔ Unlock account

```
sudo usermod -U sajid
```

### ✔ Add user to group

```
sudo usermod -aG docker sajid
```

---

# 📌 6. Group Management

### ✔ Create group

```
sudo groupadd devops
```

### ✔ Remove group

```
sudo groupdel devops
```

### ✔ Add user to group

```
sudo usermod -aG devops sajid
```

### ✔ See groups of a user

```
groups sajid
```

### ✔ Change group ownership of file

```
sudo chgrp devops file.txt
```

---

# 📌 7. Sudo (Admin Privileges)

### ✔ Add user to sudo group

```
sudo usermod -aG sudo sajid
```

### ✔ Edit sudoers file

```
sudo visudo
```

Example rule:

```
sajid ALL=(ALL) NOPASSWD: ALL
```

---

# 📌 8. Checking Logged-In Users

### ✔ Who is logged in?

```
who
```

### ✔ More detail

```
w
```

### ✔ Login history

```
last
```

---

# 📌 9. Default User Template Files

Files in:

```
/etc/skel/
```

are copied to every new user’s home directory.

---

# 📌 10. Shell Management

### ✔ View available shells

```
cat /etc/shells
```

### ✔ Change user shell

```
sudo chsh -s /bin/bash sajid
```

---

# 📌 11. System Users vs Normal Users

### ✔ System users (UID < 1000)

Used by services like nginx, mysql, www-data.

### ✔ Normal users (UID ≥ 1000)

For human login users.

Check UID:

```
id sajid
```

---

# 📌 12. Password & Account Expiration

### ✔ Set expiry date

```
sudo chage -E 2025-12-31 sajid
```

### ✔ Check aging details

```
chage -l sajid
```

---

# 📌 13. Real DevOps Use Cases

### ✔ Create a deploy user

```
sudo useradd -m -s /bin/bash deploy
sudo usermod -aG docker deploy
```

### ✔ Jenkins agent user

```
sudo useradd -m jenkins
```

### ✔ Secure SSH access

```
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

### ✔ Create service user with no login

```
sudo useradd -r -s /usr/sbin/nologin myapp
```

