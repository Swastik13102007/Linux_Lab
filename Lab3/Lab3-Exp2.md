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
/home/mayank13
```
---

### `ls` – List Directory Contents

Lists files and folders in the current directory.

```bash
ls
```bash

Output

    Directory: mayank13@ubuntu/home/mayank13



```
![Image](./F515.png)

---

### `cd` – Change Directory

Moves into a directory.

```bash
cd projects
```

---

## ✅ 2. **File and Directory Management**

### `mkdir` – Make Directory

Creates a new folder.

```bash
mkdir newone 
```bash
  Directory: mayank13@ubuntu


### `touch` – Create File

Creates an empty file.

```bash
touch newone.txt
```

---

### `cp` – Copy Files or Directories

```bash
cp newone.txt newone2
```

* Copy folder:

```bash
cp -r newone newone2
```

---

### `mv` – Move or Rename Files

```bash
mv newone.txt newone2.txt

```bash
mv newone2.txt ~/Worksheet/     # Move file
```

---

### `rm` – Remove Files

```bash
rm newone2.txt
rm -r newone
```
![Image](./F516.png)
---

⚠️ **Be careful!** There is no undo.

---
## ✅ 3. **File Viewing & Editing**

### `cat` – View File Contents

Displays content in terminal.

```bash
cat newone2.txt

Hii how are you

```bash

```
![Image](./F518.png)
---
### `nano` – Edit Files in Terminal

A basic terminal-based text editor.

```bash
nano newone2.txt
---

### `clear` – Clears the Terminal

```bash
clear
```
![Image](./F517.png)
---

## ✅ 4. **System Commands**

### `echo` – Print Text

Useful for debugging or scripting.

```bash
echo  "Hello, World!"
Hello world!
```
![Image](./F519.png)
---

### `whoami` – Show Current User

```bash
whoami

mayank13
```
![Image](./F520.png)
---

### `man` – Manual for Any Command

```bash
man ls
```
![Image](./F521.png)
---

## ✅ 5. **Searching and Finding**

### `find` – Locate Files

```bash
find . -name "*newone2.txt"
```
![Image](./F522.png)
---

### `grep` – Search Inside Files

```bash
grep "Hii" newone2.txt

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
mkdir newone3 && cd newone3 && touch newone3.txt

newone3.txt
```
![Image](./F523.png)
--- 









