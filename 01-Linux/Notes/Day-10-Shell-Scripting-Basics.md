# Day 10 - Shell Scripting Basics

## What is Shell Scripting?

A shell script is a text file containing a sequence of Linux commands that are executed automatically in order.

### Why use Shell Scripting?

* Automates repetitive tasks.
* Saves time and manual effort.
* Reduces human errors.
* Makes scripts reusable.
* Improves productivity.

---

## Shebang

```bash
#!/bin/bash
```

### What is a Shebang?

The shebang is the first line of a shell script. It tells Linux which interpreter should execute the script.

Example:

```bash
#!/bin/bash
```

This instructs Linux to execute the script using the Bash shell.

**Note:** The `.sh` extension is only a naming convention. Linux can execute a script even without the `.sh` extension.

---

## Variables

A variable is used to store data that can be reused throughout a script.

### Why use Variables?

* Avoid repeating values.
* Change a value in one place instead of multiple places.
* Make scripts reusable and easier to maintain.

### Creating a Variable

```bash
NAME="Sathwika"
```

**Rules:**

* No spaces around `=`.
* Variable names are commonly written in uppercase (convention).

### Accessing a Variable

```bash
echo $NAME
```

Output:

```text
Sathwika
```

Without `$`, Bash treats it as plain text.

```bash
echo NAME
```

Output:

```text
NAME
```

---

## User Input

The `read` command accepts input from the user and stores it in a variable.

### Method 1

```bash
echo "Enter your name:"
read NAME
```

### Method 2

```bash
read -p "Enter your name: " NAME
```

Example:

```bash
read -p "Enter your city: " CITY
echo "You live in $CITY"
```

---

## Conditional Statements

Conditional statements allow a script to make decisions.

Example logic:

```
If a condition is true
    Perform one action
Else
    Perform another action
```

Basic structure:

```bash
if condition
then
    commands
else
    commands
fi
```

### Why `fi`?

`fi` marks the end of an `if` block.

It is especially important when multiple or nested `if` statements are used, allowing Bash to identify where each `if` statement ends.

---

## Key Learnings

* A shell script automates Linux commands.
* `#!/bin/bash` tells Linux to execute the script using Bash.
* `.sh` is a convention, not a requirement.
* Variables store reusable values.
* Use `$` to access variable values.
* `read` accepts user input.
* `if` statements allow scripts to make decisions.
* `fi` marks the end of an `if` block.
