# Linux Boot Process – Complete README

The Linux boot process describes the sequence of steps a Linux system follows from powering on to loading the operating system and giving you a login prompt.
---

# 📌 1. Overview of Linux Boot Process

The Linux boot process happens in **6 major stages**:

1️⃣ **BIOS / UEFI**
2️⃣ **MBR / GPT (Bootloader Stage 1)**
3️⃣ **GRUB (Bootloader Stage 2)**
4️⃣ **Kernel Loading**
5️⃣ **Init / systemd**
6️⃣ **Login Prompt (TTY / GUI)**

---

# 📌 2. Stage 1: BIOS / UEFI Initialization

### ✔ What happens here:

* Hardware initialization (CPU, RAM, keyboard, disks)
* Checks boot devices
* Loads the first bootloader from disk

### ✔ BIOS or UEFI?

* **BIOS** → old firmware
* **UEFI** → modern, faster, secure boot, larger disks

To check:

```
dmesg | grep -i uefi
```

---

# 📌 3. Stage 2: MBR / GPT (Bootloader Stage 1)

### ✔ MBR (Master Boot Record)

* First 512 bytes of disk
* Contains bootloader + partition table

### ✔ GPT (GUID Partition Table)

* Modern replacement for MBR
* Supports >2TB disks
* Used with UEFI

Check disk type:

```
lsblk -f
```

---

# 📌 4. Stage 3: GRUB – Bootloader Stage 2

**GRUB (GRand Unified Bootloader)** loads the Linux kernel.

### ✔ GRUB tasks:

* Displays boot menu
* Loads kernel and initramfs
* Allows kernel parameters

GRUB config file:

```
/etc/default/grub
```

Update GRUB:

```
sudo update-grub
```

---

# 📌 5. Stage 4: Linux Kernel Loading

### ✔ Kernel responsibilities:

* Detect hardware
* Load drivers
* Mount root filesystem (`/`)
* Start `init` process

Kernel image is stored in:

```
/boot/vmlinuz-<version>
```

Initial RAM filesystem:

```
/boot/initrd.img-<version>
```

---

# 📌 6. Stage 5: Init / systemd

After the kernel loads, it starts the **init process**, typically **systemd**.

Check init system:

```
ps -p 1 -o comm=
```

Expected output:

```
systemd
```

### ✔ systemd responsibilities:

* Starts services
* Manages targets (runlevels)
* Controls boot order

Systemd unit files:

```
/lib/systemd/system
/etc/systemd/system
```

Check boot services:

```
systemctl --type=service
```

Boot targets:

```
systemctl get-default
```

Common targets:

* `graphical.target` → GUI
* `multi-user.target` → CLI server mode

---

# 📌 7. Stage 6: Login Prompt (TTY / GUI)

Final stage provides:

* Console login (`tty1–tty6`)
* GUI login (GDM, LightDM, SDDM)

Switch between terminal TTYs:

```
Ctrl + Alt + F2   (TTY2)
Ctrl + Alt + F1   (Back to GUI)
```

---

# 📌 Linux Boot Process Diagram (Text Version)

```
Power On
   ↓
BIOS / UEFI
   ↓
MBR / GPT
   ↓
GRUB Bootloader
   ↓
Linux Kernel + initramfs
   ↓
systemd (PID 1)
   ↓
Services + Targets
   ↓
Login Prompt (CLI or GUI)
```

---

# 📌 Key Files in the Boot Process

| File                  | Purpose                |
| --------------------- | ---------------------- |
| `/boot/vmlinuz`       | Linux kernel           |
| `/boot/initrd.img`    | Initial RAM disk       |
| `/etc/default/grub`   | GRUB config            |
| `/etc/fstab`          | Filesystem mount rules |
| `/lib/systemd/system` | System services        |

---

# 📌 Commands Useful for Boot Troubleshooting

### ✔ View boot logs

```
journalctl -b
```

### ✔ View kernel messages

```
dmesg
```

### ✔ List failed systemd services

```
systemctl --failed
```

### ✔ Boot into emergency mode

```
systemctl emergency
```

### ✔ Boot into rescue mode

```
systemctl rescue
```

---

# 📌 Practical DevOps Use Cases

### ✔ GRUB edits for kernel parameters during troubleshooting

```
GRUB_CMDLINE_LINUX="systemd.log_level=debug"
```

### ✔ Resize disks and update fstab

```
/etc/fstab
```

### ✔ Debug boot failures on EC2, GCP, Azure

* Wrong fstab mounts
* Kernel panics
* Missing root filesystem

### ✔ Systemd service creation for apps

```
/etc/systemd/system/myapp.service
```

---

# 📌 Summary

You learned the complete Linux boot sequence:

* BIOS/UEFI
* MBR/GPT
* GRUB
* Kernel
* systemd
* Login prompt

