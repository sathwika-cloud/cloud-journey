# Day 03 - Hidden Files & Linux Permissions

# Hidden Files

## What are Hidden Files?

Hidden files are files or directories whose names start with a dot (`.`).

Examples:
- `.bashrc`
- `.git`
- `.ssh`
- `.profile`
- `.config`

Linux hides these files from normal view to keep the file system clean.

---

## Why are Hidden Files Used?

Most hidden files are **configuration files**.

Configuration files store the settings and information that applications need to remember.

Examples:
- Bash terminal settings
- Git repository information
- SSH keys and configuration
- Application preferences

---

## Hidden Does NOT Mean Secure

Hidden files are only hidden from normal directory listings.

Anyone with the required permissions can:
- View them
- Edit them
- Delete them

Security is controlled by **Linux Permissions**, not by hiding files.

---

## Viewing Hidden Files

To display hidden files:

```bash
ls -a
```

`-a` means **all**, including hidden files.

---

## Important Hidden Directories

### `.git`

Created when running:

```bash
git init
```

Stores:
- Commit history
- Branch information
- Repository configuration

---

### `.ssh`

Stores:
- SSH keys
- Known hosts
- SSH configuration

Cloud engineers use this directory frequently while connecting to Linux servers.

---

### `.bashrc`

Stores Bash shell configuration such as:
- Aliases
- Environment variables
- Prompt customization

---

# Linux Permissions

Linux uses permissions to control who can access files and directories.

Permissions help protect important files from unauthorized access or accidental modification.

---

## Permission Types

### Read (r)

For Files:
- View file contents

For Directories:
- View directory contents

---

### Write (w)

For Files:
- Edit file contents

For Directories:
- Create files
- Delete files
- Rename files

---

### Execute (x)

Allows a file (usually a script or program) to be executed.

Example:

```bash
./deploy.sh
```

Without execute permission, Linux displays:

```text
Permission denied
```

---

# Permission Categories

Linux divides users into three categories.

## Owner (u)

Usually the user who created the file.

Typically has the highest level of access.

---

## Group (g)

Users who belong to the same group.

Permissions are shared among group members.

---

## Others (o)

Everyone else who is neither the owner nor part of the group.

---

# Example

```
Owner   : rw-
Group   : r--
Others  : ---
```

Meaning:

Owner
- Can read
- Can edit

Group
- Can only read

Others
- No access

---

# Why Permissions are Important

Permissions help:
- Protect sensitive files
- Prevent accidental changes
- Restrict unauthorized access
- Secure Linux servers

In Cloud Computing, permissions protect:
- Configuration files
- Deployment scripts
- SSH keys
- Application files
- Database configuration

---

# Key Takeaways

- Hidden files begin with a dot (`.`).
- Hidden files usually store application configuration.
- Hidden does **not** mean secure.
- Use `ls -a` to view hidden files.
- Linux permissions control who can access files.
- There are three permissions:
  - Read (r)
  - Write (w)
  - Execute (x)
- There are three permission categories:
  - Owner (u)
  - Group (g)
  - Others (o)
