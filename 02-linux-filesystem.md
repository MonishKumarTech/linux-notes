# 02 - Linux Filesystem

## What is the Linux Filesystem?

The Linux filesystem is the directory structure used to organize files, folders, programs, system settings, logs, devices, and user data.

In Linux, everything starts from the root directory:

```bash
/
```

Simple recall:

`/` is the starting point of the Linux filesystem.

---

## Root Directory

The root directory is the top-level directory in Linux.

Every file and folder exists under `/`.

Example:

```bash
/
├── home
├── etc
├── var
├── usr
├── bin
├── sbin
├── tmp
├── dev
├── proc
```

Simple recall:

Root `/` is the parent of all directories.

---

## Important Linux Directories

| Directory | Purpose                            |
| --------- | ---------------------------------- |
| `/`       | Root directory                     |
| `/home`   | User personal directories          |
| `/root`   | Home directory of root user        |
| `/etc`    | Configuration files                |
| `/var`    | Variable data like logs            |
| `/usr`    | User programs and system resources |
| `/bin`    | Essential user commands            |
| `/sbin`   | System administration commands     |
| `/tmp`    | Temporary files                    |
| `/dev`    | Device files                       |
| `/proc`   | Process and kernel information     |
| `/opt`    | Optional third-party software      |
| `/mnt`    | Temporary mount point              |
| `/media`  | External devices like USB drives   |

---

## /home

The `/home` directory contains normal user files.

Example:

```bash
/home/demo
```

If the username is `demo`, the user's home directory is:

```bash
/home/demo
```

Simple recall:

`/home` stores user data.

---

## /root

The `/root` directory is the home directory of the root user.

It is different from `/`.

Important:

* `/` means root directory
* `/root` means root user's home directory

Simple recall:

`/` = top of filesystem
`/root` = root user's personal folder

---

## /etc

The `/etc` directory stores system configuration files.

Examples:

```bash
/etc/passwd
/etc/hostname
/etc/fstab
```

Simple recall:

`/etc` contains settings.

---

## /var

The `/var` directory stores changing data.

It commonly contains:

* Logs
* Cache
* Mail
* Spool files

Example:

```bash
/var/log
```

Simple recall:

`/var` contains variable data.

---

## /usr

The `/usr` directory stores user programs, libraries, documentation, and shared system resources.

Example:

```bash
/usr/bin
/usr/lib
/usr/share
```

Simple recall:

`/usr` contains many installed programs and resources.

---

## /bin

The `/bin` directory contains essential commands used by normal users.

Examples:

```bash
/bin/ls
/bin/cp
/bin/mv
```

Simple recall:

`/bin` contains basic commands.

---

## /sbin

The `/sbin` directory contains system administration commands.

Examples:

```bash
/sbin/reboot
/sbin/shutdown
```

Simple recall:

`sbin` means system binaries.

---

## /tmp

The `/tmp` directory stores temporary files.

Files in `/tmp` may be deleted automatically.

Simple recall:

`/tmp` is for temporary storage.

---

## /dev

The `/dev` directory contains device files.

Examples:

```bash
/dev/sda
/dev/null
/dev/tty
```

Simple recall:

Linux treats devices like files.

---

## /proc

The `/proc` directory contains information about running processes and the kernel.

Example:

```bash
/proc/cpuinfo
/proc/meminfo
```

Simple recall:

`/proc` gives live system information.

---

## /opt

The `/opt` directory is used for optional third-party software.

Simple recall:

`/opt` means optional software.

---

## /mnt and /media

`/mnt` is used for temporarily mounted filesystems.

`/media` is commonly used for removable devices like USB drives.

Simple recall:

* `/mnt` = manual mount location
* `/media` = removable device location

---

## Absolute Path

An absolute path starts from `/`.

Example:

```bash
/home/demo/Documents/file.txt
```

Simple recall:

Absolute path starts from root.

---

## Relative Path

A relative path starts from the current directory.

Example:

```bash
Documents/file.txt
```

Simple recall:

Relative path depends on where you are now.

---

## Home Symbol ~

The `~` symbol represents the current user's home directory.

Example:

```bash
cd ~
```

If the user is `demo`, then `~` means:

```bash
/home/demo
```

Simple recall:

`~` means my home directory.

---

## Current and Parent Directory

| Symbol | Meaning           |
| ------ | ----------------- |
| `.`    | Current directory |
| `..`   | Parent directory  |

Example:

```bash
cd .
cd ..
```

Simple recall:

`.` = here
`..` = one level back

---

## Useful Commands for Filesystem Practice

## pwd

Shows current location.

```bash
pwd
```

## ls /

Lists root directory.

```bash
ls /
```

## ls /home

Lists home directories.

```bash
ls /home
```

## cd /

Moves to root directory.

```bash
cd /
```

## cd ~

Moves to current user's home directory.

```bash
cd ~
```

## cd ..

Moves one directory back.

```bash
cd ..
```

---

## Example Practice

Create a practice directory:

```bash
mkdir LinuxPractice
```

Enter the directory:

```bash
cd LinuxPractice
```

Create folders:

```bash
mkdir Docs Images Backup
```

Check the folders:

```bash
ls
```

Expected output:

```bash
Backup  Docs  Images
```

Check current location:

```bash
pwd
```

Example output:

```bash
/home/demo/LinuxPractice
```

---

## Quick Recall Notes

* `/` is the root directory.
* `/home` stores normal user files.
* `/root` is the root user's home folder.
* `/etc` stores configuration files.
* `/var` stores logs and changing data.
* `/bin` stores essential user commands.
* `/sbin` stores system administration commands.
* `/tmp` stores temporary files.
* `/dev` stores device files.
* `/proc` stores live system and process information.
* Absolute path starts from `/`.
* Relative path starts from the current directory.
* `~` means current user's home directory.
* `.` means current directory.
* `..` means parent directory.

---

## Interview Questions

## 1. What is the root directory in Linux?

The root directory `/` is the top-level directory in Linux. All files and folders exist under it.

## 2. What is the difference between `/` and `/root`?

`/` is the root directory of the whole filesystem.
`/root` is the home directory of the root user.

## 3. What is stored in `/home`?

The `/home` directory stores normal users' personal files and folders.

## 4. What is stored in `/etc`?

The `/etc` directory stores system configuration files.

## 5. What is stored in `/var/log`?

The `/var/log` directory stores system and application log files.

## 6. What is an absolute path?

An absolute path starts from the root directory `/`.

Example:

```bash
/home/demo/Documents/file.txt
```

## 7. What is a relative path?

A relative path starts from the current working directory.

Example:

```bash
Documents/file.txt
```

## 8. What does `~` mean in Linux?

`~` represents the current user's home directory.

## 9. What does `..` mean?

`..` means the parent directory.

## 10. Why should IT support learners understand the Linux filesystem?

Because troubleshooting Linux systems requires knowing where user files, configuration files, logs, commands, and system information are stored.
