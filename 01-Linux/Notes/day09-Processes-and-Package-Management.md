# Day 09 - Processes, Package Management & Users

## Processes

### What is a Process?

A process is a program that is currently running in the system.

Examples:

* Google Chrome
* Microsoft Teams
* File Explorer
* Outlook
* Bash Terminal

Each process is identified by a unique **Process ID (PID)**.

---

## Process Commands

### `ps`

Displays the processes running in the current terminal session.

### `ps -ef`

Displays all running processes in the Linux system with detailed information.

### `top`

Displays a live view of running processes along with CPU and memory usage.

Useful information shown by `top`:

* PID
* CPU Usage
* Memory Usage
* Running and Sleeping Processes

Press **q** to exit `top`.

### `kill`

Terminates a process using its Process ID (PID).

---

## Package Management

### What is a Package?

A package contains everything required for a software application to run, such as:

* Application files
* Required libraries
* Configuration files
* Documentation

### What is a Package Manager?

A package manager is a tool used to:

* Download software
* Install software
* Update software
* Remove software
* Manage software dependencies

Ubuntu uses **APT (Advanced Package Tool)** as its package manager.

### Common APT Commands

Update the package list:

```bash
sudo apt update
```

Install software:

```bash
sudo apt install <package-name>
```

Remove software:

```bash
sudo apt remove <package-name>
```

**Note:** `apt update` refreshes the package list from the repositories. It does **not** update the installed software.

---

## Users and Groups

### User

A user is an individual account used to log in to a Linux system.

### Group

A group is a collection of users that share the same permissions.

Using groups makes permission management easier because permissions can be assigned to the group instead of individual users.

---

## Important Commands

### `whoami`

Displays the currently logged-in user.

### `groups`

Displays all the groups the current user belongs to.

### `id`

Displays:

* User ID (UID)
* Group ID (GID)
* Groups the user belongs to

### `sudo`

Executes a command with administrator (root) privileges.

It is used when performing administrative tasks such as installing software or changing system settings.

---

## Key Learnings

* Every running application is a process.
* Every process has a unique PID.
* `ps` shows processes in the current terminal.
* `ps -ef` shows all system processes.
* `top` provides a live view of system resource usage.
* A package manager simplifies software installation and maintenance.
* Ubuntu uses APT for package management.
* Users provide individual identities on a Linux system.
* Groups simplify permission management.
* `sudo` allows temporary administrator access when required.
