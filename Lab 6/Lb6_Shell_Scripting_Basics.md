# 🐚✨SHELL SCRIPTING TUTORIAL!! 🚀

Shell scripting allows you to **automate tasks** in Linux/Unix by writing commands inside a file that the shell executes line by line.

---

═════════════════════════════════════════
### 🔹 1. **What is a Shell Script?**
═════════════════════════════════════════

📌 A **shell** is a command-line interpreter (e.g., `bash`, `zsh`, `sh`).
📌 A **shell script** is a text file with a series of commands.
📌 File usually has **`.sh`** extension, though not mandatory.

🎬 Example: `1_script.sh`**

File name = "1_script.sh"

```bash
#!/bin/bash
echo "Hello World!"
```

▶️ Run it:

```bash
chmod +x 1_script.sh   # make it executable
./1_script.sh
```

✅ Output:

```
Hello World!
```
 🖼️  ![Image](./F1.png)

  
 🖼️  ![Image](./F500.png)

---

💡 Tip: Always start your script with #!/bin/bash, so the system knows which interpreter to use.

═════════════════════════════
### 🔹 2. **Variables 🎒**
═════════════════════════════

📦 Variables store data (text, numbers, paths, etc.).

✍️ Defining variables

```bash
name="Swastik"
age=17
```

⚠️ No spaces around `=`.

📤 Accessing variables

```bash
echo "My name is $name and I am $age years old."
```

✅ Output:

```
My name is Swastik and I am 17 years old.
```

🌍 Environment variables

```bash
echo $HOME   # 🏠 Home directory
echo $USER   # 👤 Current user
echo $PWD    # 📍 Present working directory
```
🖼️  ![Image](./F501.png)

🖼️  ![Image](./F502.png)
---

💡 Pro Tip: Use printenv to list all available environment variables.

══════════════════════════════
### 🔹 3. **User Input 🎤**
══════════════════════════════

Read input from user with `read`.

```bash
#!/bin/bash
echo "Enter your favorite language:"
read lang
echo "You chose $lang"
```
🖼️  ![Image](./F503.png)

🖼️  ![Image](./F504.png)
---

✅ Success: Scripts become interactive when you use read.

══════════════════════════════════════════════════
### 🔹 4. **Conditional Statements (if-else) ⚖️**
══════════════════════════════════════════════════

```bash
#!/bin/bash
num=10

if [ $num -gt 5 ]; then
    echo "Number is greater than 5 ✅"
else
    echo "Number is less than or equal to 5 ❌"
fi
```
🔑Operators:

* `-eq` (equal)
* `-ne` (not equal)
* `-gt` (greater than)
* `-lt` (less than)
* `-ge` (greater or equal)
* `-le` (less or equal)

🖼️ ![Image](./F505.png)

🖼️ ![Image](./F506.png)
---

🚨 Warning: Always leave spaces inside [ ] in conditions, otherwise the script fails.

═══════════════════════
### 🔹5.**Loops 🔄** 
═══════════════════════

🔁 For loop

```bash
for i in 1 2 3 4 5
do
    echo "Number: $i"
done
```

👉 range:

```bash
for i in {1..5}
do
    echo "Iteration $i"
done
```

🔁 While loop
```bash
count=1
while [ $count -le 5 ]
do
    echo "Count: $count"
    ((count++))   # increment
done
```

🔁 Until loop

Runs until condition becomes true.

```bash
x=1
until [ $x -gt 5 ]
do
    echo "Value: $x"
    ((x++))
done
```
🖼️ ![Image](./F507.png)

🖼️ ![Image](./F508.png)

🖼️ ![Image](./F509.png)

🖼️ ![Image](./F510.png)


🖼️ ![Image](./F8.png)

🖼️ ![Image](./F9.png)

🖼️ ![Image](./F11.png)

🖼️ ![Image](./F12.png)
---

💡 Pro Tip: Use loops for automation like file processing, backups, or bulk renaming.

═════════════════════════════
### 🔹 6. **Functions 🛠️**
═════════════════════════════

Encapsulate reusable code.

```bash
greet() {
    echo "Hello, $1 👋"
}

greet Swastik 👋
greet World 🌍
```

✅ Output:

```
Hello, Swastik
Hello, World
```
🖼️ ![Image](./F511.png) 

🖼️ ![Image](./F512.png) 
---

⚡ Note: $1, $2 … are function arguments.

═══════════════════════════════════════════
### 🔹 7. **Command Line Arguments 🎯**
═══════════════════════════════════════════

Access arguments passed to script:

```bash
#!/bin/bash
echo "Script name: $0"
echo "First argument: $1"
echo "Second argument: $2"
echo "All arguments: $@"
echo "Number of arguments: $#"
```

▶️ Run:

```bash
./1_script.sh apple banana
```

✅ Output:

```
Script name: ./script.sh
First argument: apple
Second argument: banana
All arguments: apple banana
Number of arguments: 2
```
🖼️ ![Image](./F513.png)

🖼️ ![Image](./F514.png)
---

💡 Pro Tip: $@ expands to all arguments, $# gives argument count.

════════════════════════════
### 🔹 8. **Arrays 📚**
════════════════════════════

```bash
variable=("V" "A" "B")

echo "First variable: ${variable[0]}"

for variable in "${variable[@]}"; do
    echo "variable: $variable"
done
```
🖼️ ![Image](F99.png)

🖼️ ![Image](F98.png)

🖼️ ![Image](F97.png)

🖼️ ![Image](F999.png)

🖼️ ![Image](F1000.png)
---

⚠️ Note: Arrays are zero-indexed → first element = ${array[0]}.

══════════════════════════════════════════════
### 🔹 9. **Useful Commands in Scripts 🧰**
══════════════════════════════════════════════

🕒 date → current date/time
🙋 whoami → current user
📂 ls → list files
📍 pwd → working directory
📖 cat → read file contents

---

💡 Tip: Use man <command> to open the manual of any command.

════════════════════════════════════════
### 🔹 10.**A Practical Example 🪟** 
════════════════════════════════════════

**Backup script (`backup.sh`):**

```bash
#!/bin/bash
# Backup home directory to /tmp

backup_file="/tmp/home_backup_$(date +%Y%m%d%H%M%S).tar.gz"

tar -czf $backup_file $HOME

echo " ✅ Backup saved to $backup_file"
```

▶️ Run:

```bash
./backup.sh
```
⚠️ Warning: Ensure you have enough space in /tmp before running backups.
---


✨ Congratulations! You now know the basics of Shell Scripting 🐚🎉


