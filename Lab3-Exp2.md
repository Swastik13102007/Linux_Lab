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
touch data.txt
```

---

### `cp` – Copy Files or Directories

```bash
cp course.txt file.
```

* Copy folder:

```bash
cp -r projects folder10
```

---

### `mv` – Move or Rename Files

```bash
mv data.txt source.txt

```bash
mv data.txt ~/Worksheet/     # Move file
```

---

### `rm` – Remove Files

```bash
rm data.txt
rm -r projects
```

⚠️ **Be careful!** There is no undo.

---
## ✅ 3. **File Viewing & Editing**

### `cat` – View File Contents

Displays content in terminal.

```bash
cat data.txt
```bash
cat  data.txt
g;ertn
ret
nrn;rntn
n
enr
Ne
eltn


ebnetknetnetl

```

---
### `nano` – Edit Files in Terminal

A basic terminal-based text editor.

```bash
nano data.txt
---

### `clear` – Clears the Terminal

```bash
clear
```
---

## ✅ 4. **System Commands**

### `echo` – Print Text

Useful for debugging or scripting.

```bash
echo  "Hello, World!"
Hello world!
```

---

### `whoami` – Show Current User

```bash
whoami

SWASTIK SUHANE
```

---

### `man` – Manual for Any Command

```bash
man ls
```
---

## ✅ 5. **Searching and Finding**

### `find` – Locate Files

```bash
find . -name "*.txt"
```
---

### `grep` – Search Inside Files

```bash
grep "Hii" data.txt

hello my name is none of your thing i dont care
```

---

## ✅ 6. **Helpful Shortcuts**

| Shortcut   | Action                      |
| ---------- | --------------------------- |
| `Tab`      | Auto-complete files/folders |
| `↑ / ↓`    | Browse command history      |
| `CTRL + C` | Stop a running command      |
| `CTRL + L` | Clear screen                |

---

## ✅ 7. **Bonus: Chaining Commands**

* **Run multiple commands**:

```bash
mkdir test && cd test && touch hii.txt

hii.txt
```









