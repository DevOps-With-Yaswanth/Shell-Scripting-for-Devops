# 🚀  Node Health Monitoring, Script Debugging and Useful Linux Commands

Welcome to Day 5 of Shell Scripting.

In this session, we will learn how DevOps Engineers monitor Linux servers, troubleshoot scripts, and use important Linux commands in real-world environments.

This session focuses on practical concepts that are commonly used in server administration, automation, monitoring, and DevOps projects.

---

# 🎯 Learning Objectives

By the end of this session, you will be able to:

✅ Understand Node Health Monitoring

✅ Analyze the health of a Linux server

✅ Create a simple Node Health Script

✅ Improve script readability

✅ Debug scripts using set -x

✅ Understand processes and process IDs

✅ Use grep and pipe commands

✅ Extract information using AWK

✅ Understand set -e and set -o pipefail

✅ Download files using wget

✅ Understand the difference between CURL and WGET

---

# 🖥️ What is Node Health?

A Node is simply a Linux server or machine.

As a DevOps Engineer, one of the common tasks is to check whether a server is healthy.

A healthy server should provide information about:

* Hostname
* Current User
* System Uptime
* Memory Usage
* Disk Usage
* Running Processes

---

# 🔍 Commands Used to Check Node Health

## Hostname

Displays the server name.

```bash
hostname
```

---

## Current User

Displays the current logged-in user.

```bash
whoami
```

---

## System Uptime

Displays how long the system has been running.

```bash
uptime
```

---

## Memory Usage

Displays RAM usage information.

```bash
free -h
```

---

## Disk Usage

Displays disk usage information.

```bash
df -h
```

---

## Running Processes

Displays currently running processes.

```bash
ps -ef
```

---

# 📝 Sample Node Health Script

```bash
#!/bin/bash

echo "================================="
echo "      NODE HEALTH REPORT"
echo "================================="

echo ""
echo "Hostname:"
hostname

echo ""
echo "Current User:"
whoami

echo ""
echo "System Uptime:"
uptime

echo ""
echo "Memory Usage:"
free -h

echo ""
echo "Disk Usage:"
df -h
```

---

# 📊 Checking Actual Disk Usage Percentage

To get the current disk usage percentage:

```bash
disk_usage=$(df -h / | awk 'NR==2 {print $5}' | tr -d '%')

echo $disk_usage
```

Example Output:

```text
60
```

This is commonly used in monitoring and alerting scripts.

---

# ✨ Improving Script Readability

Good scripts should be easy to read and understand.

### Example

```bash
echo "================================="
echo "      NODE HEALTH REPORT"
echo "================================="
```

Use meaningful messages so that anyone reading the output can easily understand it.

---

# ✅ Good Practices for Writing Shell Scripts

### Use Meaningful Variable Names

Good:

```bash
disk_usage=80
```

Bad:

```bash
a=80
```

---

### Add Comments

```bash
# Check disk usage
```

Comments help others understand the script.

---

### Keep Output Clean

Good:

```bash
echo "Current Disk Usage: $disk_usage%"
```

---

### Use Functions

Functions help avoid duplicate code and improve script readability.

---

# 🐞 Debugging Scripts Using set -x

The set -x option displays each command before execution.

### Example

```bash
#!/bin/bash

set -x

name="DevOps"

echo $name
```

### Output

```text
+ name=DevOps
+ echo DevOps
DevOps
```

### Purpose

* Troubleshooting scripts
* Finding errors
* Understanding script execution flow

---

# ⚙️ What are Processes?

A Process is a running program.

Examples:

* Chrome Browser
* VS Code
* Jenkins
* Docker
* Nginx

All of these run as processes.

---

# View Running Processes

```bash
ps -ef
```

---

# Find a Specific Process

Example:

```bash
ps -ef | grep ssh
```

or

```bash
ps -ef | grep sleep
```

---

# What is a Process ID (PID)?

Every process running on Linux has a unique Process ID.

Example:

```text
UID       PID       PPID       CMD
user      1234      1000       sleep 300
```

Here:

```text
PID = 1234
```

---

# 🔍 grep Command

grep is used to search and filter output.

### Example

```bash
ps -ef | grep ssh
```

This displays only SSH related processes.

---

# 🔗 Pipe Command ( | )

The pipe symbol passes the output of one command to another command.

### Example

```bash
ps -ef | grep ssh
```

Flow:

```text
ps -ef
   |
   |
   V
grep ssh
```

---

# 📄 AWK Command

AWK is used to extract specific columns from command output.

### Example

```bash
df -h
```

---

Display First Column:

```bash
df -h | awk '{print $1}'
```

---

Display Second Column:

```bash
df -h | awk '{print $2}'
```

---

Display Disk Usage Percentage:

```bash
df -h / | awk 'NR==2 {print $5}'
```

Example Output:

```text
60%
```

---

# 🛑 set -e

The set -e option stops script execution immediately if a command fails.

### Example

```bash
#!/bin/bash

set -e

pwd

invalidcommand

echo "Hello"
```

### Result

```text
invalidcommand: command not found
```

The script stops immediately.

### Purpose

Prevents scripts from continuing when an error occurs.

---

# 🛑 set -o pipefail

Used together with pipelines.

### Example

```bash
set -o pipefail
```

This ensures the script detects failures inside piped commands.

### Common Usage

```bash
set -e
set -o pipefail
```

These are widely used in production-grade scripts.

---

# 📥 wget Command

wget is used to download files from the internet.

### Example

```bash
wget https://example.com/file.zip
```

After downloading:

```bash
ls
```

You can see the downloaded file.

---

# 🌐 curl Command

curl is used to communicate with web servers and APIs.

### Example

```bash
curl https://google.com
```

---

# CURL vs WGET

| CURL                  | WGET                          |
| --------------------- | ----------------------------- |
| Used for APIs         | Used for Downloads            |
| Returns response      | Downloads file                |
| Common in CI/CD       | Common for packages and files |
| Supports API requests | Best for downloading files    |

---

# Examples

### CURL

```bash
curl ifconfig.me
```

Displays public IP address.

---

### WGET

```bash
wget https://example.com/file.zip
```

Downloads a file.

---

# 📚 Summary

In this session, we learned:

* Node Health Monitoring
* Important Linux Health Check Commands
* Node Health Script
* Script Readability
* Good Scripting Practices
* Debugging with set -x
* Processes and Process IDs
* grep Command
* Pipe Command
* AWK Command
* set -e
* set -o pipefail
* wget Command
* CURL vs WGET

These concepts are widely used in Linux Administration, DevOps, Automation, Monitoring, Troubleshooting, and CI/CD Pipelines.

---

# 🎉 Shell Scripting Course Completed

Congratulations!

You have now learned:

* Introduction to Shell Scripting
* Variables and User Input
* Conditions and Operators
* Positional Arguments
* Loops and Functions
* Node Health Monitoring
* Script Debugging
* Process Management
* Useful Linux Commands

You are now ready to start using Shell Scripting in real DevOps environments and automation tasks.
