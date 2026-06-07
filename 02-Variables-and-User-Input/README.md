# 🐚 Shell Scripting - Variables and User Input

## 📌 Introduction

Variables are used to store data in shell scripting.

User Input allows users to enter data while running the script.

These are very important basics in Shell Scripting.

---

# 📚 Topics Covered

- What is a Variable
- Creating Variables
- Using Variables
- System Variables
- User Input using `read`
- Hidden Password Input
- Real-Time Examples

---

# 🧠 What is a Variable?

A variable stores data.

## Example

```bash
name="Linux"
```

Here:
- `name` → Variable Name
- `Linux` → Stored Value

---

# 📌 Accessing Variable Value

Use `$` symbol to access the variable value.

## Example

```bash
#!/bin/bash

name="Linux"

echo $name
```

## Output

```text
Linux
```

---

# 📌 Rules for Variables

## ✅ Correct

```bash
name="John"
age=25
city="Kadapa"
```

## ❌ Wrong

```bash
name = "John"
my-name="John"
1name="John"
```

---

# 📌 Multiple Variables Example

```bash
#!/bin/bash

name="Yaswanth"
age=25
city="Kadapa"

echo "Name: $name"
echo "Age: $age"
echo "City: $city"
```

---

# 📌 System Variables

Linux already provides some system variables.

| Variable | Meaning |
|----------|----------|
| `$HOME` | Home Directory |
| `$USER` | Current User |
| `$PWD` | Present Working Directory |
| `$SHELL` | Current Shell |

## Example

```bash
#!/bin/bash

echo $HOME
echo $USER
echo $PWD
```

---

# 📌 What is User Input?

User input allows users to enter data while running the script.

We use:

```bash
read
```

---

# 📌 Basic User Input Example

```bash
#!/bin/bash

echo "Enter your name:"
read name

echo "Your name is $name"
```

---

# 📌 User Input with Prompt

```bash
#!/bin/bash

read -p "Enter your age: " age

echo "Your age is $age"
```

---

# 📌 Multiple Inputs

```bash
#!/bin/bash

read -p "Enter name and city: " name city

echo "Name: $name"
echo "City: $city"
```

---

# 📌 Hidden Password Input

Used for passwords.

```bash
#!/bin/bash

read -s -p "Enter Password: " password

echo
echo "Password received"
```

---

# 📌 Real-Time Example

## Student Registration Script

```bash
#!/bin/bash

echo "===== Student Registration ====="

read -p "Enter Name: " name
read -p "Enter Age: " age
read -p "Enter Course: " course

echo
echo "===== Student Details ====="

echo "Name   : $name"
echo "Age    : $age"
echo "Course : $course"
```

---

# 📌 Common Mistakes

## ❌ Giving Space Around `=`

Wrong:

```bash
name = "Linux"
```

Correct:

```bash
name="Linux"
```

---

## ❌ Forgetting `$`

Wrong:

```bash
echo name
```

Correct:

```bash
echo $name
```

---

# 🧪 Practice Tasks

## Task 1

Create variables:
- name
- age
- city

Print all values.

---

## Task 2

Take user input:
- username
- password

Display the values.

---

## Task 3

Store current date in a variable.

Hint:

```bash
date
```

---

# 🎯 Summary

| Concept | Example |
|----------|----------|
| Variable | `name="Linux"` |
| Access Variable | `$name` |
| User Input | `read name` |
| Prompt Input | `read -p` |
| Hidden Input | `read -s` |

---

# 🚀 Conclusion

Variables and User Input are the foundation of Shell Scripting.

Understanding these concepts will help in:
- Automation
- DevOps
- Linux Administration
- Real-Time Scripting

Happy Learning 😊
