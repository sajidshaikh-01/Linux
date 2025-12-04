# Linux Package Management – Complete README

Package management is how Linux installs, updates, removes, and manages software. Every Linux distribution uses a package manager and package repository system.

This README covers **APT, DPKG, YUM, DNF, RPM, Snap, Flatpak**, and real DevOps examples.

---

# 📌 1. What Is a Package Manager?

A package manager:

* Installs software
* Updates software
* Removes software
* Resolves dependencies
* Manages repositories

Examples:

* **Ubuntu/Debian** → `apt`, `dpkg`
* **RHEL/CentOS/Fedora** → `yum`, `dnf`, `rpm`
* **Universal** → `snap`, `flatpak`

---

# 📌 2. APT (Ubuntu / Debian)

## ✔ Update package list

```
sudo apt update
```

## ✔ Upgrade installed packages

```
sudo apt upgrade
```

## ✔ Install a package

```
sudo apt install nginx
```

## ✔ Remove a package

```
sudo apt remove nginx
```

## ✔ Remove including config files

```
sudo apt purge nginx
```

## ✔ Search packages

```
apt search docker
```

## ✔ Show package info

```
appropos nginx
apt show nginx
```

---

# 📌 3. DPKG (Low-Level – Debian/Ubuntu)

Used for `.deb` files.

## ✔ Install `.deb` package

```
sudo dpkg -i package.deb
```

## ✔ Fix broken dependencies

```
sudo apt --fix-broken install
```

## ✔ List installed packages

```
dpkg -l
```

## ✔ Remove package

```
sudo dpkg -r package_name
```

---

# 📌 4. YUM (CentOS / RHEL 7)

## ✔ Install package

```
sudo yum install nginx -y
```

## ✔ Update packages

```
sudo yum update -y
```

## ✔ Remove package

```
sudo yum remove nginx -y
```

## ✔ Search package

```
yum search nginx
```

---

# 📌 5. DNF (Fedora / RHEL 8+)

Successor to YUM.

## ✔ Install package

```
sudo dnf install nginx -y
```

## ✔ Update

```
sudo dnf update -y
```

## ✔ Remove package

```
sudo dnf remove nginx -y
```

---

# 📌 6. RPM (Low-Level – RedHat/Fedora)

Used for `.rpm` files.

## ✔ Install

```
sudo rpm -ivh package.rpm
```

## ✔ Upgrade

```
sudo rpm -Uvh package.rpm
```

## ✔ List installed RPM packages

```
rpm -qa
```

## ✔ Query package info

```
rpm -qi package_name
```

---

# 📌 7. Snap (Cross-Distribution)

## ✔ Install snap package

```
sudo snap install docker
```

## ✔ List snap packages

```
snap list
```

## ✔ Remove package

```
sudo snap remove docker
```

---

# 📌 8. Flatpak (Cross-Distribution)

## ✔ Install package

```
flatpak install flathub org.mozilla.firefox
```

## ✔ Run application

```
flatpak run org.mozilla.firefox
```

## ✔ Remove package

```
flatpak uninstall org.mozilla.firefox
```

---

# 📌 9. Add/Remove Repositories

### ✔ Add APT repo

```
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
```

### ✔ Add YUM repo

```
sudo yum-config-manager --add-repo http://repo.example.com/rhel7.repo
```

---

# 📌 10. Clean Cache

### ✔ APT

```
sudo apt autoremove
sudo apt clean
```

### ✔ YUM/DNF

```
sudo yum clean all
sudo dnf clean all
```

---

# 📌 11. Real DevOps Use Cases

### ✔ Install Docker

```
sudo apt install docker.io -y
```

### ✔ Install Kubernetes tools

```
sudo apt install kubeadm kubectl kubelet
```

### ✔ Install Terraform (via .deb)

```
sudo dpkg -i terraform.deb
```

### ✔ Install Jenkins

```
sudo apt install openjdk-11-jdk
sudo apt install jenkins
```

---

# 📌 12. Summary

You learned:

* APT, DPKG, YUM, DNF, RPM
* Snap & Flatpak
* Package installation, removal, and updates
* Real DevOps examples

