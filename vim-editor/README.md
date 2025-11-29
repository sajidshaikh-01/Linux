# Vim Editor – Complete README

Vim is a powerful, fast, and keyboard-focused text editor widely used in **Linux, DevOps, Cloud, and System Administration**. This README explains how to use Vim along with all important shortcut commands.

---

# 📌 What is Vim?

Vim (Vi IMproved) is an upgraded version of the classic `vi` editor. It is:

* Lightweight
* Available on all Linux servers
* Extremely fast
* Great for editing config files, scripts, YAML, etc.

DevOps engineers use Vim every day.

---

# 📌 Vim Modes

Vim has **3 main modes**:

### **1️⃣ Normal Mode (default)**

Used for navigation & shortcuts.

### **2️⃣ Insert Mode**

Used for typing text.

### **3️⃣ Command Mode**

Used for saving, quitting, searching.

---

# 📌 How to Open Vim

```bash
vim filename.txt
```

If file doesn't exist, Vim creates it.

---

# 📌 Switch Between Modes

| Action                   | Key   |
| ------------------------ | ----- |
| Enter Insert Mode        | `i`   |
| Enter Append Mode        | `a`   |
| Enter Insert at new line | `o`   |
| Back to Normal Mode      | `Esc` |
| Enter Command Mode       | `:`   |

---

# 📌 Save & Exit Commands

| Action              | Command          |
| ------------------- | ---------------- |
| Save file           | `:w`             |
| Quit Vim            | `:q`             |
| Save & quit         | `:wq` or `:x`    |
| Quit without saving | `:q!`            |
| Save as new file    | `:w newname.txt` |

---

# 📌 Insert Mode Shortcuts

| Action                | Key |
| --------------------- | --- |
| Insert at cursor      | `i` |
| Insert at line start  | `I` |
| Append after cursor   | `a` |
| Append at end of line | `A` |
| New line below        | `o` |
| New line above        | `O` |

---

# 📌 Navigation Shortcuts (Normal Mode)

| Action                | Key   |
| --------------------- | ----- |
| Move up               | `k`   |
| Move down             | `j`   |
| Move left             | `h`   |
| Move right            | `l`   |
| Jump to start of line | `0`   |
| Jump to end of line   | `$`   |
| Jump to top of file   | `gg`  |
| Jump to bottom        | `G`   |
| Go to line number     | `:15` |

---

# 📌 Delete Commands

| Action                  | Key   |
| ----------------------- | ----- |
| Delete character        | `x`   |
| Delete word             | `dw`  |
| Delete line             | `dd`  |
| Delete 3 lines          | `3dd` |
| Delete till end of line | `D`   |

---

# 📌 Copy & Paste in Vim

| Action              | Key   |
| ------------------- | ----- |
| Copy (yank) a line  | `yy`  |
| Copy 3 lines        | `3yy` |
| Paste               | `p`   |
| Paste before cursor | `P`   |

---

# 📌 Undo & Redo

| Action | Key        |
| ------ | ---------- |
| Undo   | `u`        |
| Redo   | `Ctrl + r` |

---

# 📌 Search & Replace

### **Search**

```vim
/searchtext
```

Move to next match:

```
n
```

Previous match:

```
N
```

### **Search and Replace**

Replace only first match in a line:

```vim
:s/old/new
```

Replace all matches in entire file:

```vim
:%s/old/new/g
```

---

# 📌 Visual Mode (Select Text)

| Action            | Key         |
| ----------------- | ----------- |
| Enter visual mode | `v`         |
| Select block mode | `Ctrl + v`  |
| Select line mode  | `Shift + v` |
| Copy selection    | `y`         |
| Delete selection  | `d`         |

---

# 📌 Window Splits

| Action               | Command            |
| -------------------- | ------------------ |
| Split horizontally   | `:split filename`  |
| Split vertically     | `:vsplit filename` |
| Move between windows | `Ctrl + w + arrow` |

---

# 📌 Tabs

| Action       | Command            |
| ------------ | ------------------ |
| New tab      | `:tabnew filename` |
| Next tab     | `gt`               |
| Previous tab | `gT`               |

---

# 📌 Summary

This README covers:

* Vim modes
* Navigation
* Editing
* Saving & quitting
* Copy, paste, undo, redo
* Searching
* Splits & tabs
