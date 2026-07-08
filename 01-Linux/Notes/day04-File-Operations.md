# Linux File Operations

File operations are basic tasks performed by Linux administrators and Cloud Engineers to manage files and directories.

## Common File Operation Commands

- `cp` → Copy files and directories
- `mv` → Move or rename files and directories
- `rm` → Delete files and directories
- `cat` → Display the contents of a file
- `less` → View large files page by page
- `head` → Display the first few lines of a file
- `tail` → Display the last few lines of a file
- `echo` → Print text or write text into a file

---

## Why are File Operations Important?

Cloud Engineers use file operations to:

- Create backups before editing configuration files.
- Move log files to archive folders.
- Delete temporary or unnecessary files.
- Read configuration and log files.
- Troubleshoot applications using logs.

---

## Real-World Examples

### Backup Configuration Files

Before editing a configuration file, create a backup copy so it can be restored if something goes wrong.

### Log Files

Large log files are usually checked using the latest entries instead of reading the entire file.

### Temporary Files

Temporary files stored in `/tmp` can be removed when they are no longer needed.

---

# Searching in Linux

Searching is an essential Linux skill because Linux servers can contain thousands or even millions of files.

There are two types of searching.

## 1. Searching for Files

Used when you know the file name but not its location.

Examples:
- `nginx.conf`
- `docker-compose.yml`
- `app.log`

Linux command:
- `find`

---

## 2. Searching Inside Files

Used when you know the text you want to locate inside a file.

Examples:
- `ERROR`
- `WARNING`
- `Connection refused`

Linux command:
- `grep`

---

## Difference

Searching for files:
- Finds the location of a file.

Searching inside files:
- Finds specific text within a file.

---

## Why is Searching Important?

Cloud Engineers use searching to:

- Locate configuration files.
- Find application log files.
- Troubleshoot server issues.
- Search for error messages.
- Quickly work with large Linux systems.
