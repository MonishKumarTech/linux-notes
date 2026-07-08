# 03 - Navigation Commands

## Purpose

Navigation commands are used to move around the Linux filesystem and check the current location.

These commands are basic but important for IT Support, System Administration, and troubleshooting.

---

## Commands Covered

* `pwd`
* `ls`
* `cd`
* `mkdir`
* `rmdir`
* `clear`

---

## pwd

## Meaning

`pwd` means **print working directory**.

It shows the current location in the Linux filesystem.

## Syntax

```bash
pwd
```

## Example

```bash
pwd
```

Example output:

```bash
/home/demo/LinuxPractice
```

## Recall

`pwd` answers:

```text
Where am I now?
```

---

## ls

## Meaning

`ls` means **list**.

It shows files and directories in the current location.

## Syntax

```bash
ls
```

## Example

```bash
ls
```

Example output:

```bash
Docs  Images  Backup
```

## Useful Options

| Command    | Purpose                            |
| ---------- | ---------------------------------- |
| `ls`       | List files and folders             |
| `ls -l`    | Long listing format                |
| `ls -a`    | Show hidden files                  |
| `ls -la`   | Long format including hidden files |
| `ls /`     | List root directory                |
| `ls /home` | List home directory                |

## Examples

```bash
ls -l
```

```bash
ls -a
```

```bash
ls -la
```

```bash
ls /home
```

## Recall

`ls` answers:

```text
What is inside this directory?
```

---

## cd

## Meaning

`cd` means **change directory**.

It is used to move from one directory to another.

## Syntax

```bash
cd directory_name
```

## Examples

Move into a directory:

```bash
cd Documents
```

Move to home directory:

```bash
cd ~
```

Move to root directory:

```bash
cd /
```

Move one level back:

```bash
cd ..
```

Move to previous directory:

```bash
cd -
```

## Recall

`cd` answers:

```text
Where do I want to go?
```

---

## mkdir

## Meaning

`mkdir` means **make directory**.

It is used to create a new directory.

## Syntax

```bash
mkdir directory_name
```

## Example

```bash
mkdir Projects
```

Create multiple directories:

```bash
mkdir Docs Images Backup
```

Create parent and child directories together:

```bash
mkdir -p LinuxPractice/Docs/Notes
```

## Recall

`mkdir` means:

```text
Make a new folder.
```

---

## rmdir

## Meaning

`rmdir` means **remove directory**.

It removes an empty directory.

## Syntax

```bash
rmdir directory_name
```

## Example

```bash
rmdir OldFolder
```

## Important Note

`rmdir` works only if the directory is empty.

If the directory has files inside, it will show an error.

Example:

```text
rmdir: failed to remove 'OldFolder': Directory not empty
```

## Recall

`rmdir` means:

```text
Remove an empty folder.
```

---

## clear

## Meaning

`clear` clears the terminal screen.

## Syntax

```bash
clear
```

## Recall

`clear` does not delete files.
It only cleans the terminal view.

---

## Absolute Path vs Relative Path

## Absolute Path

An absolute path starts from `/`.

Example:

```bash
cd /home/demo/Documents
```

Recall:

```text
Absolute path starts from root.
```

---

## Relative Path

A relative path starts from the current directory.

Example:

```bash
cd Documents
```

Recall:

```text
Relative path depends on where I am now.
```

---

## Special Path Symbols

| Symbol | Meaning                       |
| ------ | ----------------------------- |
| `/`    | Root directory                |
| `~`    | Current user's home directory |
| `.`    | Current directory             |
| `..`   | Parent directory              |
| `-`    | Previous directory            |

---

## Practice Example

Create a practice folder:

```bash
mkdir LinuxPractice
```

Enter the folder:

```bash
cd LinuxPractice
```

Check current location:

```bash
pwd
```

Create subfolders:

```bash
mkdir Docs Images Backup
```

List folders:

```bash
ls
```

Expected output:

```bash
Backup  Docs  Images
```

Move into Docs:

```bash
cd Docs
```

Check location:

```bash
pwd
```

Move back one level:

```bash
cd ..
```

Remove empty Backup folder:

```bash
rmdir Backup
```

Check result:

```bash
ls
```

---

## Common Mistakes

## Mistake 1

Trying to enter a directory that does not exist.

```bash
cd Downloads
```

Possible error:

```text
bash: cd: Downloads: No such file or directory
```

Fix:

```bash
ls
```

Check the exact folder name before using `cd`.

---

## Mistake 2

Using `rmdir` on a folder that contains files.

```bash
rmdir Docs
```

Possible error:

```text
Directory not empty
```

Fix:

Use `ls Docs` to check what is inside.

---

## Mistake 3

Confusing `/` and `~`.

| Symbol | Meaning             |
| ------ | ------------------- |
| `/`    | Root directory      |
| `~`    | User home directory |

Example:

```bash
cd /
```

Moves to root directory.

```bash
cd ~
```

Moves to home directory.

---

## Quick Recall Notes

* `pwd` shows current location.
* `ls` lists files and folders.
* `cd` changes directory.
* `mkdir` creates directories.
* `rmdir` removes empty directories.
* `clear` clears the terminal screen.
* `/` means root directory.
* `~` means home directory.
* `.` means current directory.
* `..` means parent directory.
* Absolute path starts from `/`.
* Relative path starts from current location.

---

## Interview Questions

## 1. What does `pwd` do?

`pwd` prints the current working directory.

## 2. What does `ls` do?

`ls` lists files and directories.

## 3. What is the difference between `ls` and `ls -a`?

`ls` shows normal files and directories.
`ls -a` also shows hidden files.

## 4. What does `cd ..` do?

`cd ..` moves one level back to the parent directory.

## 5. What is the difference between absolute path and relative path?

An absolute path starts from `/`.
A relative path starts from the current directory.

## 6. What does `mkdir` do?

`mkdir` creates a new directory.

## 7. What does `rmdir` do?

`rmdir` removes an empty directory.

## 8. Why does `rmdir` sometimes fail?

`rmdir` fails when the directory is not empty.

## 9. What does `~` represent?

`~` represents the current user's home directory.

## 10. Why are navigation commands important?

Navigation commands help users move through the filesystem, find files, check directories, and perform troubleshooting tasks.
