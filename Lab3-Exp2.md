Here's a **detailed tutorial on basic terminal commands** that work on **Linux, macOS, and Git Bash (Windows)**. These commands are essential for navigating and managing files from the terminal, especially for coding and version control (e.g., Git, VS Code, etc.).

---

## ✅ 1. **Navigation Commands**

### `pwd` – Print Working Directory

Shows the current location in the filesystem.

```bash
pwd
```

📌 Output example:

```
C:\Users\SWASTIK SUHANE\Downloads\Linux lab
```
---

### `ls` – List Directory Contents

Lists files and folders in the current directory.

```bash
ls
```bash

    Directory: C:\Users\SWASTIK SUHANE\Downloads\Linux lab


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        07-08-2025     11:20                Lab1
-a----        12-08-2025     13:26          31080 1.image.png
-a----        07-08-2025     11:33         542740 2.png
-a----        07-08-2025     18:41         281590 4.png
-a----        07-08-2025     10:51         311400 cp.png
-a----        07-08-2025     11:37           2339 First.md
-a----        12-08-2025     13:07           2342 fourth.md
-a----        12-08-2025     13:27            216 Lab3-Exp1.md
-a----        12-08-2025     13:35            618 Lab3-Exp2.md
-a----        07-08-2025     11:20         524656 Screenshot 2025-08-07 112023.png
-a----        07-08-2025     11:39           2401 thrid.md
```
---

### `cd` – Change Directory

Moves into a directory.

```bash
cd projects
PS C:\Users\SWASTIK SUHANE\Downloads\Linux lab\projects> 
```

---

## ✅ 2. **File and Directory Management**

### `mkdir` – Make Directory

Creates a new folder.

```bash
mkdir projects 
```bash
  Directory: C:\Users\SWASTIK SUHANE\Downloads\Linux lab


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        12-08-2025     18:23                projects

```

---

### `touch` – Create File

Creates an empty file.

```bash
touch file.txt
```

---

### `cp` – Copy Files or Directories

```bash
cp source.txt file.
```

* Copy folder:

```bash
cp -r projects folder10
```

---

### `mv` – Move or Rename Files

```bash
mv file.txt source.txt

```bash
mv file.txt ~//     # Move file




