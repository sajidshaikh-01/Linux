# Linux File System – Complete README

The Linux File System defines **how files and directories are organized**, stored, and accessed. 
---

# 📌 1. What Is a File System?

A **file system** controls how data is stored and retrieved on storage devices.

Popular Linux file systems:

* **ext4** (default on Ubuntu)
* **xfs** (default on RHEL/CentOS 7+)
* **btrfs**
* **zfs**

Use:

```
lsblk -f
```

To see which file system is in use.

---

# 📌 2. Linux Directory Structure (FHS – File Hierarchy Standard)

Linux follows a universal directory structure.

```
/
├── bin
├── boot
├── dev
├── etc
├── home
├── lib
├── media
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin
├── srv
├── sys
├── tmp
├── usr
└── var
```

---

# 📌 3. Important Directories Explained

### 📁 `/` (Root)

Top-level directory; everything starts from here.

---

### 📁 `/home`

Contains home directories for normal users.

```
/home/user1
/home/user2
```

---

### 📁 `/root`

Home directory of the **root user**.
Privileged access only.

---

### 📁 `/etc`

Stores system-wide configuration files.
Examples:

* `/etc/passwd`
* `/etc/ssh/sshd_config`
* `/etc/fstab`

---

### 📁 `/bin` and `/sbin`

Essential user commands and system commands.

`/bin` → basic commands (`ls`, `cp`, `mv`, `cat`)

`/sbin` → admin/system commands (`mount`, `ifconfig`, `reboot`)

---

### 📁 `/usr`

User-installed programs, libraries, documentation.

```
/usr/bin
/usr/sbin
/usr/lib
```

---

### 📁 `/var`

Variable data:

* Logs → `/var/log`
* Cache → `/var/cache`
* Spool files

---

### 📁 `/tmp`

Temporary files (deleted on reboot).

---

### 📁 `/dev`

Device files (virtual files representing hardware):

* `/dev/sda` → disk
* `/dev/null`
* `/dev/tty`

---

### 📁 `/proc`

Virtual filesystem showing process info.

```
/proc/cpuinfo
/proc/meminfo
```

---

### 📁 `/sys`

Info about kernel, devices, hardware.

---

### 📁 `/mnt` and `/media`

For mounting external devices.

* `/mnt` → manual mounts
* `/media` → automatic mounts (USB, CD, HDD)

---

### 📁 `/opt`

Optional third‑party software.

---

### 📁 `/boot`

Bootloader files, Linux kernel image.

* `/boot/vmlinuz` → kernel
* `/boot/grub` → GRUB config

---

# 📌 4. Absolute vs Relative Paths

### ✔ Absolute Path

Starts from root `/`:

```
/etc/ssh/sshd_config
```

### ✔ Relative Path

Based on current directory:

```
cd ../logs
```

---

# 📌 5. File Types in Linux

Check file types using:

```
ls -l
```

| Symbol | Type             |
| ------ | ---------------- |
| `-`    | Regular file     |
| `d`    | Directory        |
| `l`    | Symbolic link    |
| `c`    | Character device |
| `b`    | Block device     |
| `s`    | Socket           |
| `p`    | Named pipe       |

---

# 📌 6. What Are Inodes?

Inodes store metadata about files:

* Ownership
* Permissions
* File size
* Timestamps
* Location of data blocks

### ✔ View inode number

```
ls -i filename
```

Hard links share the same inode.

---

# 📌 7. Mounting File Systems

### ✔ Check mounted filesystems

```
mount
```

OR

```
findmnt
```

### ✔ Mount a device

```
sudo mount /dev/sdb1 /mnt
```

### ✔ Unmount

```
sudo umount /mnt
```

---

# 📌 8. Disk Usage & Space Management

### ✔ Check disk space

```
df -h
```

### ✔ Check folder sizes

```
du -sh *
```

### ✔ Find large files

```
find / -type f -size +100M
```

---

# 📌 9. Special System Files

### ✔ `/etc/fstab`

Defines what to mount at boot.

### ✔ `/etc/passwd`

User accounts.

### ✔ `/proc` files

Used for monitoring.

---

# 📌 10. DevOps & Cloud Use Cases

### ✔ Docker uses overlay filesystems

```
/var/lib/docker/overlay2
```

### ✔ Kubernetes volumes stored in

```
/var/lib/kubelet
```

### ✔ System logs stored in

```
/var/log
```

### ✔ Web apps store configs in

```
/etc/<appname>
```

### ✔ CI/CD runners store caches in `/var`

---

# 📌 Summary

You learned:

* Linux directory structure
* Important paths and meanings
* File types
* Inodes and mount points
* Disk usage commands
* DevOps real use cases

sheet
🔥 Diagram-based explanation
