# What is a shell script?
* A **shell script** is a text file containing a series of commands written for the shell to execute.
* It automates tasks that you would normally run in the terminal.
* Example: Running multiple commands, looping through files, making backups, etc.

---

## 2. Creating Your First Shell Script

1. Open a terminal and create a file:

   ```bash
     nano qwerty.txt
   ```
![Image](./abc.png)
   ---

2. Add the following content:

   ```bash
   #!/bin/bash
   # This is a simple shell script

   echo "Hii, World!"
   ```
   ![Image](./xyz.png)

   ---

   3. Save and exit (`CTRL+O`, `CTRL+X` in nano).

4. Make it executable:

   ```bash
   chmod +x qwerty.txt
   ```
![Image](./asd.png)
   --- 

   5. Run it:

   ```bash
   ./qwerty.txt
   ```

✅ Output should be:

```
Hii, World!
```
![Image](./98.png)
---

## 3. Variables in Shell

You can store data in variables:

```bash
#!/bin/bash

name="Swastik"
age=17

echo "My name is $name"
echo "I am $age years old"

echo "My name is Swastik"
echo "I am 17 years old"
```

⚠️ Note: **No spaces** around `=` when assigning values.

![Image](./13.png)

---

## 4. Taking User Input

```bash
#!/bin/bash

echo "Enter your name:"
read username - swastik

echo "Hii, swastik! Welcome to shell scripting."
```

* `read` → takes input from the user.
* `$username` → retrieves the value.

![Image](./789.png)

![Image](./1qa.png)
---

## 5. Conditional Statements (if-else)

```bash
#!/bin/bash

echo "Enter a number:"
read num

if [ $num -gt 10 ]
then
    echo "The number is greater than 10"
else
    echo "The number is 10 or smaller"
fi
```

* `-gt` → greater than.
* Other operators: `-lt` (less than), `-eq` (equal).



---

