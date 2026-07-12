# Linux Search Commands

## Why Searching is Important

Linux servers can contain thousands or millions of files. Searching helps administrators and Cloud Engineers quickly locate files and troubleshoot issues.

---

## find

Used to search for files and directories by name.

### Syntax

```bash
find <starting-location> -name "<file-name>"
```

### Example

```bash
find . -name "app.conf"
```

---

## grep

Used to search for text inside a file.

### Syntax

```bash
grep "text" filename
```

### Example

```bash
grep "ERROR" server.log
```

---

## Difference

### find

- Searches for files and directories.
- Returns file or directory paths.

### grep

- Searches inside a file.
- Returns matching lines.

---

## Real-World Uses

### find

- Locate configuration files.
- Find log files.
- Search for deployment scripts.

### grep

- Search logs for ERROR or WARNING.
- Find configuration values.
- Troubleshoot application issues.
