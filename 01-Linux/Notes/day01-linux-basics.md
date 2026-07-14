# Linux - Day 1

## Commands Learned

# Day 1 - Linux Basics

## Commands Learned

### Navigation
```bash
pwd        # Print current working directory
ls         # List files and folders
cd folder  # Move into a folder
cd ..      # Move back one level
```

### Creating Files & Folders
```bash
mkdir folder_name   # Create a directory
mkdir -p directory/foldername/foldername #Create all the directories if they don't exist then fine ignore
touch file.txt      # Create an empty file
```

### Moving Files
```bash
mv file.txt folder/     # Move a file
mv old.txt new.txt      # Rename a file
```

### Reading & Writing Files
```bash
cat file.txt                    # Display file contents
echo "Hello Linux" > file.txt   # Overwrite file
echo "New line" >> file.txt     # Append to file
```

### Deleting
```bash
rm file.txt     # Delete a file
rmdir foldername # Delete a folder
```

## Key Learnings

- `pwd` tells me where I am.
- `ls` shows what is in the current directory.
- Linux uses a tree-like file system.
- `>` overwrites a file, while `>>` appends to it.
- `rm` permanently deletes a file.
