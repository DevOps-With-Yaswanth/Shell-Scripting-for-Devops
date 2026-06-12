# 🚀 Shell Scripting  - Conditions, Operators and Positional Arguments

Welcome to **Day 3 of Shell Scripting**.

In this session, we will learn how shell scripts make decisions and how values can be passed while executing a script.

These concepts are heavily used in:

* Monitoring Scripts
* Deployment Scripts
* Backup Scripts
* CI/CD Pipelines
* DevOps Automation

---

# 🎯 Learning Objectives

By the end of this session, you will be able to:

✅ Understand Conditions

✅ Use Numeric Operators

✅ Use String Operators

✅ Write `if`, `if-else`, and `if-elif-else` statements

✅ Pass values using Positional Arguments

✅ Build simple DevOps automation scripts

---

# 🤔 Why Do We Need Conditions?

Conditions help a script make decisions.

### Example

Suppose a server has:

```text
Disk Usage = 85%
```

Question:

```text
Is Disk Usage > 80 ?
```

Result:

```text
YES
```

Action:

```text
Display Alert
```

Without conditions, a script cannot decide what action should be performed.

---

# ✅ Understanding TRUE and FALSE

Every condition produces one of two results:

```text
TRUE
```

or

```text
FALSE
```

### Examples

```text
10 > 5
TRUE
```

```text
5 > 10
FALSE
```

```text
80 >= 80
TRUE
```

---

# 🔢 Numeric Operators

Numeric operators are used to compare numbers.

| Operator | Meaning               |
| -------- | --------------------- |
| `-eq`    | Equal                 |
| `-ne`    | Not Equal             |
| `-gt`    | Greater Than          |
| `-lt`    | Less Than             |
| `-ge`    | Greater Than or Equal |
| `-le`    | Less Than or Equal    |

### Examples

```text
10 -eq 10
TRUE
```

```text
20 -gt 10
TRUE
```

```text
5 -lt 10
TRUE
```

---

# 🔹 if Statement

Used when an action should execute only when a condition is TRUE.

### Example

```bash
#!/bin/bash

disk_usage=85

if [ $disk_usage -gt 80 ]
then
    echo "Disk Usage Alert"
fi
```

### Output

```text
Disk Usage Alert
```

---

# 🔹 if else Statement

Used when there are two possible outcomes.

### Example

```bash
#!/bin/bash

disk_usage=60

if [ $disk_usage -gt 80 ]
then
    echo "Disk Usage Alert"
else
    echo "Disk Usage Normal"
fi
```

### Output

```text
Disk Usage Normal
```

---

# 🔹 if elif else Statement

Used when multiple conditions need to be checked.

### Example

```bash
#!/bin/bash

cpu_usage=75

if [ $cpu_usage -ge 90 ]
then
    echo "Critical"
elif [ $cpu_usage -ge 70 ]
then
    echo "Warning"
else
    echo "Healthy"
fi
```

### Output

```text
Warning
```

---

# 🔤 String Operators

String operators are used to compare text values.

| Operator | Meaning          |
| -------- | ---------------- |
| `=`      | Equal            |
| `!=`     | Not Equal        |
| `-z`     | Empty String     |
| `-n`     | Not Empty String |

### Example

```bash
#!/bin/bash

environment="prod"

if [ "$environment" = "prod" ]
then
    echo "Deploying to Production"
fi
```

### Output

```text
Deploying to Production
```

---

# 📥 What Are Positional Arguments?

Positional arguments allow values to be passed while executing a script.

### Example

```bash
./deploy.sh prod ecommerce-app
```

Explanation:

```text
$1 = prod
$2 = ecommerce-app
```

---

# 📝 Positional Argument Example

```bash
#!/bin/bash

echo "Environment : $1"
echo "Application : $2"
```

### Run

```bash
./deploy.sh prod ecommerce-app
```

### Output

```text
Environment : prod
Application : ecommerce-app
```

---

# 📌 Special Variables

| Variable | Description               |
| -------- | ------------------------- |
| `$1`     | First Argument            |
| `$2`     | Second Argument           |
| `$#`     | Total Number of Arguments |
| `$@`     | All Arguments             |
| `$?`     | Previous Command Status   |

### Example

```bash
echo $#
```

---

# 💽 Real-Time Example - Check Disk Usage

View current disk usage:

```bash
df -h
```

### Example Output

```text
Filesystem      Size  Used Avail Use%
/dev/sda1       100G   60G   40G   60%
```

---

# 📊 Get Current Disk Usage Percentage

```bash
disk_usage=$(df -h / | awk 'NR==2 {print $5}' | tr -d '%')

echo $disk_usage
```

### Example Output

```text
60
```

This value can be used in monitoring and alerting scripts.

---

# 🚨 Real-Time DevOps Example

```bash
#!/bin/bash

disk_usage=$(df -h / | awk 'NR==2 {print $5}' | tr -d '%')

if [ $disk_usage -gt 80 ]
then
    echo "Disk Usage Alert"
else
    echo "Disk Usage Normal"
fi
```

### Purpose

✔ Get actual disk usage from Linux

✔ Compare usage percentage

✔ Generate alert when usage exceeds 80%

---

# 🧪 Practice Tasks

## Task 1

Create a script that checks whether disk usage is above 80%.

---

## Task 2

Create a script that accepts an environment name using positional arguments.

### Example

```bash
./deploy.sh prod
```

### Expected Output

```text
Deploying to Production
```

---

## Task 3

Create a script that checks CPU usage and displays:

```text
Critical
Warning
Healthy
```

based on the value provided.

---

# 📚 Summary

In this session, we learned:

* Conditions
* Numeric Operators
* String Operators
* if Statement
* if else Statement
* if elif else Statement
* Positional Arguments
* Special Variables
* Real-Time Disk Usage Monitoring

These concepts form the foundation of DevOps automation and are commonly used in monitoring, deployment, backup, and CI/CD workflows.

---

