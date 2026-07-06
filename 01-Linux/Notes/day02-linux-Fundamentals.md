# Day 02 - Linux Fundamentals

## 1. Operating System (OS)

An Operating System acts as a bridge between the user, applications, and the computer hardware.

Responsibilities:
- Manages CPU
- Manages Memory (RAM)
- Manages Storage
- Runs Applications
- Controls Hardware

Examples:
- Windows
- Linux
- macOS

---

## 2. What is Linux?

Linux is an open-source operating system widely used in servers and cloud computing.

Advantages:
- Fast
- Stable
- Secure
- Free
- Open Source
- Highly Customizable

---

## 3. Why Linux is used in Cloud?

Most cloud providers use Linux because it:
- Handles heavy workloads
- Is reliable
- Supports automation
- Has excellent performance
- Has no licensing cost
- Is secure

Examples:
- AWS EC2
- Docker Containers
- Kubernetes Nodes

---

## 4. Linux Distributions

A Linux distribution is a version of Linux packaged with software and tools.

Examples:
- Ubuntu
- Debian
- Fedora
- Rocky Linux
- Amazon Linux

---

## 5. Kernel

The Kernel is the core of the operating system.

Responsibilities:
- Manages CPU
- Manages Memory
- Manages Storage
- Communicates with Hardware

---

## 6. Shell

The Shell is a command interpreter.

Responsibilities:
- Accepts user commands
- Sends requests to the Kernel
- Displays output

Example:
- Bash

---

## 7. Terminal

The Terminal is the application/window used to interact with the Shell.

Flow:

User
↓
Terminal
↓
Shell
↓
Kernel
↓
Hardware
↓
Output

---

## 8. Linux File System

Everything starts from the Root Directory (/).

Important Directories:

/              Root Directory
/home          User files
/etc           Configuration files
/var           Variable data and logs
/var/log       System and application logs
/tmp           Temporary files
/usr           User Installed programs
/bin           Essential commands(pwd, ls)
/boot          Boot files( Files needed to start an OS)

---

## 9. Temporary Files

Temporary files are created only while a task is being performed.

Examples:
- Software installation
- File downloads
- Image editing
- Application cache

Usually stored in:
/tmp

---

## 10. Absolute Path

Starts from the Root (/).

Example:

/home/sathwiks/cloud-journey/01-Linux

Works from anywhere.

---

## 11. Relative Path

Starts from the current directory.

Example:

01-Linux

Depends on the current working directory.

---

## Key Takeaways

- Linux is the operating system used by most cloud servers.
- The Kernel manages hardware.
- The Shell communicates with the Kernel.
- The Terminal is where users type commands.
- Everything in Linux starts from the Root (/).
- Use Absolute paths for reliability.
- Use Relative paths for convenience.
