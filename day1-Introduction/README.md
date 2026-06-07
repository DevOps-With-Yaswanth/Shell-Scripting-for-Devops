# Day 1 - Introduction to Shell Scripting

Welcome to Day 1 of Shell Scripting.

In this session, we will learn the basics of shell scripting and understand how automation works in Linux.

---

# What is Shell Scripting?

Shell scripting is a way to automate Linux commands using a script file.

Instead of typing commands one by one manually, we can write all commands inside a file and execute them together.

---

# Why Do We Use Shell Scripting?

Shell scripting helps us to:

* Automate repetitive tasks
* Save time
* Reduce manual work
* Manage servers easily
* Perform DevOps automation

---

# Shell Architecture

```text id="42j36d"
+------------+
|   USER     |
+------------+
       |
       v
+------------+
|   SHELL    |
|  (bash)    |
+------------+
       |
       v
+------------+
|   KERNEL   |
+------------+
       |
       v
+------------+
|  HARDWARE  |
+------------+
```

## Explanation

* User gives commands
* Shell interprets commands
* Kernel processes requests
* Hardware performs operations

---

# Commands Practiced

## Create a File

```bash id="jlwm8h"
touch file.txt
```

---

## List Files and Folders

```bash id="m5n7wx"
ls
```

```bash id="l6w7mf"
ls -l
```

---

## Manual Command Help

```bash id="04x38y"
man ls
```

---

# Create and Edit Files Using vim

## Create File

```bash id="kvs62v"
vim test.sh
```

## Insert Mode

Press:

```text id="yc0wdf"
i
```

to enter insert mode.

---

## Save and Exit

Press:

```text id="5awgvz"
ESC
```

Then type:

```text id="sx2p4d"
:wq
```

---

# Difference Between touch and vim

| touch              | vim                    |
| ------------------ | ---------------------- |
| Creates empty file | Creates and edits file |
| No editing         | Supports editing       |

---

# Copy File Content

```bash id="d4b1vg"
cp file1.txt file2.txt
```

---

# What is #!/bin/bash ?

```bash id="vwwob5"
#!/bin/bash
```

This is called:

* Shebang
* Interpreter Path

It tells Linux to execute the script using Bash shell.

---

# Different Types of Shells

| Shell | Description           |
| ----- | --------------------- |
| bash  | Bourne Again Shell    |
| sh    | Bourne Shell          |
| ksh   | Korn Shell            |
| dash  | Debian Almquist Shell |

Bash is commonly used in DevOps.

---

# echo Command

Used to print output on the screen.

Example:

```bash id="1k64bo"
echo "Welcome to Shell Scripting"
```

---

# First Shell Script

```bash id="mh9m71"
#!/bin/bash

echo "Welcome to Shell Scripting"

date
pwd
whoami
```

---

# Execute Shell Script

## Give Execute Permission

```bash id="r3hjpm"
chmod +x test.sh
```

---

## Run Script

```bash id="mrjucy"
./test.sh
```

---

# Linux Permissions

Permissions control who can:

* Read
* Write
* Execute

---

# chmod Command

Used to change file permissions.

Example:

```bash id="9e3zmk"
chmod +x test.sh
```

This gives execute permission to the script.

---

# Important Commands Used Today

| Command | Purpose            |
| ------- | ------------------ |
| touch   | Create file        |
| ls      | List files         |
| man     | Command manual     |
| vim     | Edit file          |
| echo    | Print output       |
| chmod   | Change permissions |
| cp      | Copy files         |

---

# Summary

In this session we learned:

* Basics of Shell Scripting
* Linux file handling
* vim editor
* Bash shell
* Script execution
* Linux permissions

---

# Practice Tasks

1. Create a shell script file
2. Print your name using echo
3. Display current date
4. Execute the script
5. Give execute permission using chmod
