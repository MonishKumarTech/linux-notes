# 04 - File Operations

## Purpose

File operation commands are used to create, copy, move, rename, view, and delete files in Linux.

These commands are important for IT Support and System Administration because many troubleshooting tasks involve working with files, logs, configuration files, backups, and scripts.

---

## Commands Covered

* `touch`
* `cat`
* `cp`
* `mv`
* `rm`
* `file`
* `less`
* `head`
* `tail`

---

## touch

## Meaning

`touch` is used to create an empty file.

It can also update the timestamp of an existing file.

## Syntax

```bash
touch filename
```

## Example

```bash
touch notes.txt
```

Check the file:

```bash
ls
```

Expected output:

```bash
notes.txt
```

## Create Multiple Files

```bash
touch file1.txt file2.txt file3.txt
```

## Recall

`touch` means:

```text
Create an empty file or update file time.
```

---

## cat

## Meaning

`cat` is used to display the content of a file.

## Syntax

```bash
cat filename
```

## Example

```bash
cat notes.txt
```

## Create Content Using cat

```bash
cat > notes.txt
```

Type the content, then press:

```text
Ctrl + D
```

## Append Content Using cat

```bash
cat >> notes.txt
```

This adds new content at the end of the file.

## Recall

`cat` means:

```text
Show file content.
```

---

## cp

## Meaning

`cp` means **copy**.

It is used to copy files and directories.

## Syntax

```bash
cp source destination
```

## Copy a File

```bash
cp notes.txt backup.txt
```

This copies `notes.txt` as `backup.txt`.

## Copy File to Another Directory

```bash
cp notes.txt Backup/
```

## Copy Directory

```bash
cp -r Docs DocsBackup
```

## Important Option

| Command              | Purpose                    |
| -------------------- | -------------------------- |
| `cp file1 file2`     | Copy file                  |
| `cp file directory/` | Copy file into directory   |
| `cp -r dir1 dir2`    | Copy directory recursively |

## Recall

`cp` means:

```text
Copy source to destination.
```

---

## mv

## Meaning

`mv` means **move**.

It is used to move or rename files and directories.

## Syntax

```bash
mv source destination
```

## Rename a File

```bash
mv notes.txt linux-notes.txt
```

## Move File to Directory

```bash
mv linux-notes.txt Docs/
```

## Rename Directory

```bash
mv OldFolder NewFolder
```

## Recall

`mv` has two uses:

```text
Move file or rename file.
```

---

## rm

## Meaning

`rm` means **remove**.

It is used to delete files and directories.

## Syntax

```bash
rm filename
```

## Delete a File

```bash
rm old.txt
```

## Delete Multiple Files

```bash
rm file1.txt file2.txt
```

## Delete Directory

```bash
rm -r OldFolder
```

## Force Delete

```bash
rm -f old.txt
```

## Dangerous Command

```bash
rm -rf foldername
```

This forcefully removes a folder and everything inside it.

Use carefully.

## Recall

`rm` means:

```text
Delete files or directories.
```

---

## file

## Meaning

`file` is used to identify the file type.

## Syntax

```bash
file filename
```

## Example

```bash
file notes.txt
```

Example output:

```bash
notes.txt: ASCII text
```

## Recall

`file` answers:

```text
What type of file is this?
```

---

## less

## Meaning

`less` is used to view long files page by page.

It is useful for reading logs and large text files.

## Syntax

```bash
less filename
```

## Example

```bash
less notes.txt
```

## Useful Keys Inside less

| Key     | Purpose         |
| ------- | --------------- |
| Space   | Move forward    |
| `b`     | Move backward   |
| `/word` | Search for word |
| `q`     | Quit            |

## Recall

`less` is useful when a file is too long for `cat`.

---

## head

## Meaning

`head` shows the first few lines of a file.

By default, it shows the first 10 lines.

## Syntax

```bash
head filename
```

## Example

```bash
head notes.txt
```

## Show First 5 Lines

```bash
head -n 5 notes.txt
```

## Recall

`head` shows the beginning of a file.

---

## tail

## Meaning

`tail` shows the last few lines of a file.

By default, it shows the last 10 lines.

## Syntax

```bash
tail filename
```

## Example

```bash
tail notes.txt
```

## Show Last 5 Lines

```bash
tail -n 5 notes.txt
```

## Follow Live File Updates

```bash
tail -f logfile.txt
```

This is useful for watching log files live.

## Recall

`tail` shows the end of a file.

---

## Practice Example

Create a practice directory:

```bash
mkdir FilePractice
```

Enter it:

```bash
cd FilePractice
```

Create files:

```bash
touch notes.txt tasks.txt backup.txt
```

Check files:

```bash
ls
```

Add content:

```bash
cat > notes.txt
```

Type:

```text
Linux file operation practice
```

Press:

```text
Ctrl + D
```

View content:

```bash
cat notes.txt
```

Copy file:

```bash
cp notes.txt notes-copy.txt
```

Rename file:

```bash
mv notes-copy.txt linux-notes-copy.txt
```

Create folder:

```bash
mkdir Backup
```

Move file into folder:

```bash
mv linux-notes-copy.txt Backup/
```

Check folder content:

```bash
ls Backup
```

Delete file:

```bash
rm tasks.txt
```

Check final files:

```bash
ls
```

---

## Common Mistakes

## Mistake 1

Using `rm` without checking the file name.

Bad habit:

```bash
rm important.txt
```

Before deleting, check:

```bash
ls
```

Better:

```bash
ls important.txt
rm important.txt
```

---

## Mistake 2

Forgetting `-r` while copying a directory.

Wrong:

```bash
cp Docs DocsBackup
```

Possible error:

```text
cp: -r not specified; omitting directory 'Docs'
```

Correct:

```bash
cp -r Docs DocsBackup
```

---

## Mistake 3

Confusing rename and copy.

This renames:

```bash
mv old.txt new.txt
```

This copies:

```bash
cp old.txt new.txt
```

Difference:

* `mv` changes the original file name or location
* `cp` keeps the original and creates another copy

---

## Mistake 4

Using `cat` for very long files.

For short files:

```bash
cat file.txt
```

For long files:

```bash
less file.txt
```

For logs:

```bash
tail -f logfile.txt
```

---

## Quick Recall Notes

* `touch` creates an empty file.
* `cat` displays file content.
* `cp` copies files or folders.
* `mv` moves or renames files and folders.
* `rm` deletes files or folders.
* `file` identifies file type.
* `less` views long files page by page.
* `head` shows the first lines of a file.
* `tail` shows the last lines of a file.
* `tail -f` watches file updates live.
* Use `cp -r` to copy directories.
* Use `rm -r` to delete directories.
* Be careful with `rm -rf`.

---

## Interview Questions

## 1. What does `touch` do?

`touch` creates an empty file or updates the timestamp of an existing file.

## 2. What does `cat` do?

`cat` displays the content of a file.

## 3. What is the difference between `cp` and `mv`?

`cp` copies a file or directory.
`mv` moves or renames a file or directory.

## 4. How do you copy a directory in Linux?

Use:

```bash
cp -r source_directory destination_directory
```

## 5. How do you delete a file?

Use:

```bash
rm filename
```

## 6. How do you delete a directory?

Use:

```bash
rm -r directory_name
```

## 7. Why is `rm -rf` dangerous?

`rm -rf` forcefully deletes files and directories without asking confirmation. If used incorrectly, it can delete important data.

## 8. What command shows the first 10 lines of a file?

```bash
head filename
```

## 9. What command shows the last 10 lines of a file?

```bash
tail filename
```

## 10. Which command is useful for watching log files live?

```bash
tail -f logfile.txt
```

## 11. When should you use `less` instead of `cat`?

Use `less` when the file is long and needs to be viewed page by page.

## 12. What does the `file` command do?

The `file` command identifies the type of a file.
