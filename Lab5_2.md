# 🐚✨ Shell Tutorial 
🔐 File Permissions with chmod and chown

════════════════════════════════════════════════
   📂 Learn Linux Permissions the Fun Way 🎭 
════════════════════════════════════════════════

---
════════════════════════════════════════════════════════
## 🔹 1. 🎭 Understanding File Permissions in Linux
════════════════════════════════════════════════════════

Each file/directory in Linux has:

* **👤Owner** → The user who created the file.
* **👥Group** → A group of users who may share access.
* **🌍Others** → Everyone else.

### 🧩 Permission Types


| Symbol | Value | Meaning | Emoji |
| ------ | ----- | ------- | ----- |
| r      | 4     | Read    | 📖    |
| w      | 2     | Write   | ✏️    |
| x      | 1     | Execute | ⚡    |

💡 **Pro Tip**: Always check permissions with `ls -l` before changing them!  

--- 


### 🧩 Permission Layout

Example from `ls -l`:

-rwxr-xr--

```
-rwxr-xr--
```

🔎 Breakdown:

* `-` → Regular file (`d` = directory, `l` = symlink, etc.)
* `rwx` → Owner has **read, write, execute**
* `r-x` → Group has **read, execute** 
* `r--` → Others have **read only**


🖼️ ![Image](./F532.png)

⚠️ **Warning**: Giving **777** permissions means *anyone can do anything* with the file. Avoid unless absolutely necessary! 🚨  

---

═══════════════════════════════════════════════════════
## 🔹 2. 🔧 `chmod` – Change File Permissions
═══════════════════════════════════════════════════════

### 🖊️ Syntax

```bash
chmod [options] mode filename
```

Modes can be set in:
✨ **Numeric (Octal)** or ✨ **Symbolic** form 

---

### (A) 🔢 Numeric (Octal) Method

 Permission → Numbers 🎯  

* Read = 4
* Write = 2
* Execute = 1

Add them up ➕ :

* `7 = rwx`
* `6 = rw-`
* `5 = r-x`
* `4 = r--`
* `0 = ---`

#### 📌 Example:

```bash
chmod 755 abc2.txt
```

👉 Meaning:
 
* 👤 Owner: 7 → `rwx`
* 👥 Group: 5 → `r-x`
* 🌍 others: 5 → `r-x`

🖼️ ![Image](./755.png)


💡 **Pro Tip**: Most common file permission for scripts = `755`  
It means: *Owner can modify & run, everyone else can only run.*  

---

### (B) ✨ Symbolic Method

Use `u` (user/owner), `g` (group), `o` (others), `a` (all).
Operators:

* `+` → Add permission
* `-` → Remove permission
* `=` → Assign exact permission

#### ✅ Examples:

```bash
chmod u+x abc2.txt    # Add execute for owner
chmod g-w abc2.txt    # Remove write from group
chmod o=r abc2.txt    # Set others to read only
chmod a+r abc2.txt    # Everyone gets read access
```
🖼️ ![Image](./qwe.png)
---

### (C) 🔄 Recursive Changes

```bash
chmod -R 755 /lab5
```

* `-R` → applies changes recursively to all files/subdirectories.

🖼️ ![Image](./mnb.png)
---

════════════════════════════════════════════════
## 🔹 3. 👑 `chown` – Change File Ownership
════════════════════════════════════════════════

### 🖊️ Syntax:

```bash
chown [options] new_owner:new_group filename

✅ Example:

```bash
chown swastik:upesvala chown.txt


👉 new_owner - swastik
👉 new_group - upesvala
👉 filename - chown.txt
```
🖼️ ![Image](./chown.png)

🚨 Warning: Only root users can usually run chown.
---

═════════════════════════════════════
## 🔹 4.⚡ Putting It All Together
═════════════════════════════════════
### Example Scenario

```bash

touch chown.txt
ls -l chown.txt
```

Output:


Now:

```bash
chmod 700 chown.txt    # Only owner has rwx
chmod u+x,g-w chown.txt   # Add execute for user, remove write for group
chown root:admin chown.txt # Change owner to root and group to admin
```
🖼️ [Image](./zxc.png)

🖼️ ![Image](./vbn.png)

🖼️ ![Image](./zxc.png)

💡 Pro Tip: Practice on test files before applying to real projects.
---

══════════════════════════════════
## 🔹 5. Quick Reference Table
══════════════════════════════════

| Numeric | Permission | Meaning      |
| ------- | ---------- | ------------ |
| 0       | ---        | No access    |
| 1       | --x        | Execute only |
| 2       | -w-        | Write only   |
| 3       | -wx        | Write + Exec |
| 4       | r--        | Read only    |
| 5       | r-x        | Read + Exec  |
| 6       | rw-        | Read + Write |
| 7       | rwx        | Full access  |

---

✅ **Key Tip**: 
👉 Use numeric (e.g., 755, 644) for fast setup.
👉 Use symbolic (u+x, g-w) for fine-grained control.
---

🎉 CONGRATS! YOU’RE NOW A PERMISSION PRO 🐧🔑