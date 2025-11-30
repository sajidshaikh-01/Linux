# Linux Compression Commands – Complete README

Linux provides multiple commands for **compressing and decompressing** files. These are essential for:

* Backups
* Log management
* Archiving
* Packaging applications
* DevOps automation (CI/CD, containers, servers)

This README explains all major Linux compression tools with examples.

---

# 📌 1. `tar` – Archive Multiple Files

`tar` bundles multiple files/directories into a single archive.

### ✔ Create a `.tar` archive

```
tar -cvf archive.tar folder/
```

* `c` → create
* `v` → verbose
* `f` → file

### ✔ Extract `.tar`

```
tar -xvf archive.tar
```

---

# 📌 2. `tar.gz` / `tar.bz2` / `tar.xz` – Compressed Archives

## **Create a `.tar.gz` (gzip)**

```
tar -czvf backup.tar.gz folder/
```

## **Extract `.tar.gz`**

```
tar -xzvf backup.tar.gz
```

## **Create `.tar.bz2` (bzip2)**

```
tar -cjvf backup.tar.bz2 folder/
```

## **Extract `.tar.bz2`**

```
tar -xjvf backup.tar.bz2
```

## **Create `.tar.xz` (xz)**

```
tar -cJvf backup.tar.xz folder/
```

## **Extract `.tar.xz`**

```
tar -xJvf backup.tar.xz
```

---

# 📌 3. `gzip` – Compress Single Files Only

### ✔ Compress a file

```
gzip file.txt
```

Creates: `file.txt.gz`

### ✔ Decompress

```
gunzip file.txt.gz
```

### ✔ Keep original file during compression

```
gzip -k file.txt
```

### ✔ Compression ratio display

```
gzip -v file.txt
```

---

# 📌 4. `bzip2` – Better Compression Than gzip

### ✔ Compress

```
bzip2 file.txt
```

Creates: `file.txt.bz2`

### ✔ Decompress

```
bunzip2 file.txt.bz2
```

### ✔ Keep original file

```
bzip2 -k file.txt
```

---

# 📌 5. `xz` – Best Compression Ratio

### ✔ Compress

```
xz file.txt
```

Creates: `file.txt.xz`

### ✔ Decompress

```
unxz file.txt.xz
```

### ✔ Keep original

```
xz -k file.txt
```

---

# 📌 6. `zip` – Windows-Friendly Compression

### ✔ Install zip

```
sudo apt install zip unzip
```

### ✔ Create zip file

```
zip archive.zip file1 file2 folder/
```

### ✔ Unzip

```
unzip archive.zip
```

### ✔ Password-protected ZIP

```
zip -e secure.zip secret.txt
```

---

# 📌 7. `7z` – High-Ratio Multi-format Compression

Install 7zip:

```
sudo apt install p7zip-full
```

### ✔ Create archive

```
7z a backup.7z folder/
```

### ✔ Extract

```
7z x backup.7z
```

### ✔ Password-protected 7z

```
7z a -pMyPassword secure.7z folder/
```

---

# 📌 8. Comparing Compression Types

| Format    | Tool       | Compression | Speed  | Multi-file support |
| --------- | ---------- | ----------- | ------ | ------------------ |
| `.gz`     | gzip       | Medium      | Fast   | ❌                  |
| `.bz2`    | bzip2      | High        | Medium | ❌                  |
| `.xz`     | xz         | Very High   | Slow   | ❌                  |
| `.zip`    | zip        | Medium      | Fast   | ✔                  |
| `.tar.gz` | tar + gzip | Medium      | Fast   | ✔✔                 |
| `.7z`     | 7zip       | Very High   | Slow   | ✔✔                 |

---

# 📌 9. Practical DevOps Use Cases

### ✔ Compress logs before sending to S3

```
tar -czvf logs.tar.gz /var/log/nginx/
```

### ✔ Backup Kubernetes YAML files

```
tar -czvf k8s_backup.tar.gz *.yaml
```

### ✔ Archive Terraform states

```
zip tfstate_backup.zip terraform.tfstate*
```

### ✔ Extract artifacts in CI/CD pipelines

```
unzip build-artifacts.zip
```

### ✔ Compress Docker volume backup

```
tar -czvf docker_volume.tar.gz /var/lib/docker/
```

---

# 📌 10. Summary

* `tar` is used to **bundle** files
* `gzip`, `bzip2`, `xz` compress **single** files
* Combined formats (`tar.gz`, `tar.bz2`, `tar.xz`) compress **directories**
* `zip` and `7z` support multi-platform compression
