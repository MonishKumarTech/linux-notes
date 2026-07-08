# 05 - Linux Permissions

## Purpose

Linux permissions control who can read, write, and execute files or directories.

Permissions are important for IT Support and System Administration because they protect files, control access, and prevent unauthorized changes.

---

## Commands Covered

* `ls -l`
* `chmod`
* `chown`
* `chgrp`

---

## Permission Types

Linux has three basic permission types:

| Symbol | Permission | Meaning                         |
| ------ | ---------- | ------------------------------- |
| `r`    | Read       | View file content               |
| `w`    | Write      | Modify or delete file           |
| `x`    | Execute    | Run file as a program or script |

---

## Permission Groups

Linux permissions are applied to three groups:

| Group  | Meaning                             |
| ------ | ----------------------------------- |
| User   | File owner                          |
| Group  | Users belonging to the file's group |
| Others | Everyone else                       |

Simple recall:

```text
User - Group - Others
```

---

## Viewing Permissions

Use:

```bash
ls -l
```

Example output:

```bash
-rw-r--r-- 1 demo demo 120 Jul 8 10:30 notes.txt
```

Breakdown:

```text
-rw-r--r--
```

| Part  | Meaning            |
| ----- | ------------------ |
| `-`   | File type          |
| `rw-` | User permissions   |
| `r--` | Group permissions  |
| `r--` | Others permissions |

---

## File Type Symbol

The first character shows the file type.

| Symbol | Meaning      |
| ------ | ------------ |
| `-`    | Regular file |
| `d`    | Directory    |
| `l`    | Link         |

Example:

```bash
-rw-r--r-- notes.txt
drwxr-xr-x Documents
```

Recall:

```text
- means file
d means directory
l means link
```

---

## Permission Example

```bash
-rw-r--r--
```

This means:

| User Type | Permission | Meaning            |
| --------- | ---------- | ------------------ |
| Owner     | `rw-`      | Can read and write |
| Group     | `r--`      | Can only read      |
| Others    | `r--`      | Can only read      |

---

## Another Permission Example

```bash
-rwxr-xr--
```

This means:

| User Type | Permission | Meaning                      |
| --------- | ---------- | ---------------------------- |
| Owner     | `rwx`      | Can read, write, and execute |
| Group     | `r-x`      | Can read and execute         |
| Others    | `r--`      | Can only read                |

---

## Permission Values

Linux permissions also have number values.

| Permission | Value |
| ---------- | ----- |
| Read       | 4     |
| Write      | 2     |
| Execute    | 1     |

To calculate permission numbers, add the values.

| Permission | Calculation | Number |
| ---------- | ----------- | ------ |
| `r--`      | 4           | 4      |
| `rw-`      | 4 + 2       | 6      |
| `r-x`      | 4 + 1       | 5      |
| `rwx`      | 4 + 2 + 1   | 7      |
| `---`      | 0           | 0      |

---

## Common Numeric Permissions

| Permission | Meaning                                    |
| ---------- | ------------------------------------------ |
| `777`      | Everyone can read, write, and execute      |
| `755`      | Owner full access, others read and execute |
| `644`      | Owner read/write, others read only         |
| `600`      | Owner read/write only                      |
| `700`      | Owner full access only                     |

---

## chmod

## Meaning

`chmod` means **change mode**.

It is used to change file or directory permissions.

## Syntax

```bash
chmod permission filename
```

---

## chmod with Numbers

Give full permission to everyone:

```bash
chmod 777 script.sh
```

Give owner full access and others read/execute:

```bash
chmod 755 script.sh
```

Give owner read/write and others read only:

```bash
chmod 644 notes.txt
```

Give owner only access:

```bash
chmod 600 private.txt
```

---

## chmod with Symbols

Symbolic method uses:

| Symbol | Meaning              |
| ------ | -------------------- |
| `u`    | User / owner         |
| `g`    | Group                |
| `o`    | Others               |
| `a`    | All                  |
| `+`    | Add permission       |
| `-`    | Remove permission    |
| `=`    | Set exact permission |

---

## Add Execute Permission

```bash
chmod +x script.sh
```

This adds execute permission.

---

## Remove Write Permission from Others

```bash
chmod o-w notes.txt
```

---

## Give User Read, Write, Execute

```bash
chmod u+rwx script.sh
```

---

## Set Exact Permission for User

```bash
chmod u=rw notes.txt
```

---

## Directory Permissions

Directory permissions behave slightly differently.

| Permission | Meaning for Directory                      |
| ---------- | ------------------------------------------ |
| `r`        | Can list directory contents                |
| `w`        | Can create, rename, or delete files inside |
| `x`        | Can enter/access the directory             |

Important:

For directories, execute permission means permission to enter the directory.

Example:

```bash
cd Documents
```

This requires execute permission on the directory.

---

## chown

## Meaning

`chown` means **change owner**.

It changes the owner of a file or directory.

## Syntax

```bash
chown user filename
```

## Example

```bash
sudo chown demo notes.txt
```

Change owner and group:

```bash
sudo chown demo:demo notes.txt
```

---

## chgrp

## Meaning

`chgrp` means **change group**.

It changes the group ownership of a file or directory.

## Syntax

```bash
chgrp groupname filename
```

## Example

```bash
sudo chgrp staff notes.txt
```

---

## Recursive Permission Change

To apply permission changes to a directory and everything inside it, use `-R`.

Example:

```bash
chmod -R 755 ProjectFolder
```

Change owner recursively:

```bash
sudo chown -R demo:demo ProjectFolder
```

Important:

Use recursive changes carefully because they affect many files.

---

## Practice Example

Create a file:

```bash
touch permission-test.txt
```

Check permissions:

```bash
ls -l permission-test.txt
```

Give owner read and write only:

```bash
chmod 600 permission-test.txt
```

Check again:

```bash
ls -l permission-test.txt
```

Give everyone read permission:

```bash
chmod 644 permission-test.txt
```

Check again:

```bash
ls -l permission-test.txt
```

Create a script file:

```bash
touch test-script.sh
```

Add execute permission:

```bash
chmod +x test-script.sh
```

Check permission:

```bash
ls -l test-script.sh
```

Expected permission may look like:

```bash
-rwxr-xr-x
```

---

## Common Mistakes

## Mistake 1

Using `chmod 777` everywhere.

Bad:

```bash
chmod 777 file.txt
```

Why it is bad:

It gives everyone read, write, and execute permission.

Better:

```bash
chmod 644 file.txt
```

For scripts:

```bash
chmod 755 script.sh
```

---

## Mistake 2

Forgetting execute permission on scripts.

Problem:

```bash
./script.sh
```

Possible error:

```text
Permission denied
```

Fix:

```bash
chmod +x script.sh
```

---

## Mistake 3

Confusing file execute and directory execute.

For a file, execute means run the file.

For a directory, execute means enter/access the directory.

---

## Mistake 4

Changing permissions recursively without checking.

Dangerous:

```bash
chmod -R 777 Documents
```

This can create security problems.

Always understand what the command will affect before using `-R`.

---

## Quick Recall Notes

* Linux permissions control file and directory access.
* Permission types are read, write, and execute.
* `r` means read.
* `w` means write.
* `x` means execute.
* Permissions apply to user, group, and others.
* `ls -l` shows permissions.
* `chmod` changes permissions.
* `chown` changes file owner.
* `chgrp` changes file group.
* `chmod +x file` adds execute permission.
* `chmod 644 file` is common for normal files.
* `chmod 755 file` is common for scripts and directories.
* `chmod 777` should not be used carelessly.
* Directory execute permission allows entering the directory.

---

## Interview Questions

## 1. What are Linux permissions?

Linux permissions control who can read, write, or execute a file or directory.

## 2. What are the three permission types in Linux?

The three permission types are read, write, and execute.

## 3. What does `rwx` mean?

`rwx` means read, write, and execute permission.

## 4. What does `ls -l` show?

`ls -l` shows detailed file information, including permissions, owner, group, size, date, and filename.

## 5. What does `chmod` do?

`chmod` changes file or directory permissions.

## 6. What does `chmod +x script.sh` do?

It adds execute permission to `script.sh`.

## 7. What does `chmod 755 script.sh` mean?

Owner can read, write, and execute.
Group and others can read and execute.

## 8. What does `chmod 644 notes.txt` mean?

Owner can read and write.
Group and others can only read.

## 9. Why is `chmod 777` risky?

It gives everyone full permission to read, write, and execute the file or directory. This can create security problems.

## 10. What does `chown` do?

`chown` changes the owner of a file or directory.

## 11. What does `chgrp` do?

`chgrp` changes the group of a file or directory.

## 12. What does execute permission mean for a directory?

For a directory, execute permission means the user can enter or access the directory.

## 13. What is the difference between `chmod` and `chown`?

`chmod` changes permissions.
`chown` changes ownership.

## 14. What does `-R` mean in permission commands?

`-R` means recursive. It applies the command to a directory and everything inside it.
