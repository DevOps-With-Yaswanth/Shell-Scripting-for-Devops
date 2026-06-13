# 🚀   Shell Scripting - Loops and Functions

Welcome to Day 4 of Shell Scripting.

In this session, we will learn how to automate repetitive tasks using **Loops** and how to avoid duplicate code using **Functions**.

These concepts are widely used in:

* Server Monitoring
* Backup Automation
* Deployment Scripts
* Health Check Scripts
* DevOps Automation
* CI/CD Pipelines

---

# 🎯 Learning Objectives

By the end of this session, you will be able to:

✅ Understand Loops

✅ Use for Loop

✅ Use while Loop

✅ Use break Statement

✅ Use continue Statement

✅ Create Functions

✅ Pass Arguments to Functions

✅ Build Simple DevOps Automation Scripts

---

# 🤔 Why Do We Need Loops?

Imagine you want to display:

```text
Welcome to DevOps
Welcome to DevOps
Welcome to DevOps
Welcome to DevOps
Welcome to DevOps
```

One way is:

```bash
echo "Welcome to DevOps"
echo "Welcome to DevOps"
echo "Welcome to DevOps"
echo "Welcome to DevOps"
echo "Welcome to DevOps"
```

This works, but it is repetitive.

A better solution is to use a Loop.

---

# 🔄 What is a Loop?

A Loop is used to execute the same task multiple times.

### Real-Life Example

```text
Print Numbers from 1 to 5

1
2
3
4
5
```

Instead of writing five separate commands, we can use a loop.

---

# 📌 Types of Loops

There are two commonly used loops in Shell Scripting:

1. for Loop
2. while Loop

---

# 🔹 for Loop

A for loop is used when we know how many times a task should repeat.

### Syntax

```bash
for variable in values
do
    commands
done
```

---

# Example 1 - Print Numbers

```bash
for i in 1 2 3 4 5
do
    echo $i
done
```

### Output

```text
1
2
3
4
5
```

---

# Example 2 - DevOps Example

```bash
for server in dev test prod
do
    echo "Checking $server server"
done
```

### Output

```text
Checking dev server
Checking test server
Checking prod server
```

This approach is commonly used to perform operations on multiple servers.

---

# 🔹 while Loop

A while loop runs until a condition becomes FALSE.

### Syntax

```bash
while [ condition ]
do
    commands
done
```

---

# Example

```bash
count=1

while [ $count -le 5 ]
do
    echo $count
    ((count++))
done
```

### Output

```text
1
2
3
4
5
```

---

# Understanding count++

```bash
((count++))
```

This increases the value of count by 1.

Example:

```text
count=1
count=2
count=3
count=4
count=5
```

---

# DevOps Example Using while Loop

```bash
count=1

while [ $count -le 3 ]
do
    free -h
    ((count++))
done
```

This checks system memory multiple times.

---

# 🔹 break Statement

The break statement is used to stop a loop immediately.

### Example

```bash
for i in 1 2 3 4 5
do
    if [ $i -eq 3 ]
    then
        break
    fi

    echo $i
done
```

### Output

```text
1
2
```

### Explanation

When the value becomes 3, the loop stops.

---

# 🔹 continue Statement

The continue statement is used to skip the current iteration.

### Example

```bash
for i in 1 2 3 4 5
do
    if [ $i -eq 3 ]
    then
        continue
    fi

    echo $i
done
```

### Output

```text
1
2
4
5
```

### Explanation

The value 3 is skipped.

---

# 🧩 What is a Function?

A Function is a reusable block of code.

Instead of writing the same commands multiple times, we can write them once inside a function and call the function whenever needed.

---

# Why Do We Need Functions?

Without Function:

```bash
echo "Server Health Check"
echo "Server Health Check"
echo "Server Health Check"
```

With Function:

```bash
health_check() {
    echo "Server Health Check"
}
```

Now we can reuse the same code multiple times.

---

# 🔹 Function Syntax

```bash
function_name() {
    commands
}
```

---

# Example

```bash
greet() {
    echo "Welcome to DevOps"
}
```

Call Function:

```bash
greet
```

### Output

```text
Welcome to DevOps
```

---

# DevOps Function Example

```bash
server_health() {

    echo "Hostname:"
    hostname

    echo "Memory Information:"
    free -h
}
```

Call Function:

```bash
server_health
```

### Output

Displays:

* Hostname
* Memory Information

This is similar to a real-world health check script.

---

# 📥 Function with Arguments

Functions can also accept arguments.

### Example

```bash
welcome() {
    echo "Welcome $1"
}
```

Call Function:

```bash
welcome DevOps
```

### Output

```text
Welcome DevOps
```

---

# DevOps Example

```bash
deploy() {
    echo "Deploying application to $1 environment"
}
```

Call Function:

```bash
deploy prod
```

### Output

```text
Deploying application to prod environment
```

---

# 🚀 Real-Time DevOps Example

```bash
#!/bin/bash

server_health() {

    echo "Hostname:"
    hostname

    echo ""

    echo "Disk Usage:"
    df -h /

    echo ""

    echo "Memory Information:"
    free -h
}

server_health
```

### Purpose

This script displays:

* Hostname
* Disk Usage
* Memory Information

This is a simple example of a Server Health Check Script.

---

# 🧪 Practice Tasks

## Task 1

Create a for loop that prints numbers from 1 to 10.

---

## Task 2

Create a for loop that displays:

```text
Checking dev server
Checking test server
Checking prod server
```

---

## Task 3

Create a while loop that prints numbers from 1 to 5.

---

## Task 4

Create a function that displays your name.

Example Output:

```text
My Name is Yaswanth
```

---

## Task 5

Create a function that accepts an environment name and displays:

```text
Deploying application to production environment
```

---

# 📚 Summary

In this session, we learned:

* for Loop
* while Loop
* break Statement
* continue Statement
* Functions
* Function Arguments
* Real-Time DevOps Examples

Loops help us automate repetitive tasks.

Functions help us reuse code.

Together, they are commonly used in DevOps automation, monitoring, deployment, backup, and CI/CD workflows.

---

