# 06 - Users and Groups

## Purpose

Linux uses users and groups to control access to files, directories, commands, and system resources.

Users and groups are important for IT Support and System Administration because they help manage permissions, security, and access control.

---

## Commands Covered

* `whoami`
* `id`
* `users`
* `groups`
* `adduser`
* `useradd`
* `passwd`
* `usermod`
* `deluser`
* `userdel`
* `groupadd`
* `groupdel`
* `su`
* `sudo`

---

## What is a User?

A user is an account that can log in and use the Linux system.

Each user has:

* Username
* User ID
* Home directory
* Default shell
* Permissions
* Group membership

Example username:

```bash
demo
```

Example home directory:

```bash
/home/demo
```

Simple recall:

```text
A user is a system account.
```

---

## What is a Group?

A group is a collection of users.

Groups are used to give shared access to files, folders, and system resources.

Simple recall:

```text
A group is a collection of users with shared permissions.
```

---

## Why Groups are Used

Groups are useful because they allow administrators to manage permissions for many users at once.

Example:

If three users need access to the same project folder, create a group and give that group access.

Bad method:

```text
Give permission separately to each user.
```

Better method:

```text
Add users to one group and give permission to the group.
```

---

## whoami

## Meaning

`whoami` shows the current logged-in username.

## Syntax

```bash
whoami
```

## Example

```bash
whoami
```

Example output:

```bash
demo
```

## Recall

`whoami` answers:

```text
Which user am I using now?
```

---

## id

## Meaning

`id` shows user ID, group ID, and group membership.

## Syntax

```bash
id
```

## Example

```bash
id
```

Example output:

```bash
uid=1000(demo) gid=1000(demo) groups=1000(demo),27(sudo)
```

## Breakdown

| Part     | Meaning                    |
| -------- | -------------------------- |
| `uid`    | User ID                    |
| `gid`    | Primary Group ID           |
| `groups` | Groups the user belongs to |

## Recall

`id` shows identity and group details.

---

## users

## Meaning

`users` shows currently logged-in users.

## Syntax

```bash
users
```

## Example

```bash
users
```

Example output:

```bash
demo
```

---

## groups

## Meaning

`groups` shows which groups a user belongs to.

## Syntax

```bash
groups
```

## Example

```bash
groups
```

Example output:

```bash
demo sudo
```

Check groups of another user:

```bash
groups username
```

## Recall

`groups` answers:

```text
Which groups does this user belong to?
```

---

## Root User

The root user is the main administrator account in Linux.

Root has full control over the system.

Root can:

* Install software
* Remove software
* Create users
* Delete users
* Change system files
* Modify permissions
* Start and stop services

Simple recall:

```text
Root is the super administrator.
```

---

## sudo

## Meaning

`sudo` means **superuser do**.

It allows a permitted user to run commands with administrator privileges.

## Example

```bash
sudo apt update
```

## Recall

`sudo` runs a command with admin permission.

---

## su

## Meaning

`su` means **switch user**.

It is used to switch from one user account to another.

## Syntax

```bash
su username
```

Switch to root:

```bash
su -
```

## Difference Between su and sudo

| Command | Purpose                              |
| ------- | ------------------------------------ |
| `su`    | Switch to another user               |
| `sudo`  | Run one command with admin privilege |

Simple recall:

```text
su = become another user
sudo = run one command as admin
```

---

## User Information Files

Linux stores user and group information in system files.

| File           | Purpose                        |
| -------------- | ------------------------------ |
| `/etc/passwd`  | User account information       |
| `/etc/shadow`  | Encrypted password information |
| `/etc/group`   | Group information              |
| `/etc/sudoers` | Sudo permission configuration  |

---

## /etc/passwd

The `/etc/passwd` file contains user account information.

View it:

```bash
cat /etc/passwd
```

Example line:

```text
demo:x:1000:1000:Demo User:/home/demo:/bin/bash
```

Breakdown:

| Part         | Meaning                          |
| ------------ | -------------------------------- |
| `demo`       | Username                         |
| `x`          | Password stored in `/etc/shadow` |
| `1000`       | User ID                          |
| `1000`       | Group ID                         |
| `Demo User`  | User info                        |
| `/home/demo` | Home directory                   |
| `/bin/bash`  | Default shell                    |

---

## /etc/group

The `/etc/group` file contains group information.

View it:

```bash
cat /etc/group
```

Example line:

```text
sudo:x:27:demo
```

Breakdown:

| Part   | Meaning                 |
| ------ | ----------------------- |
| `sudo` | Group name              |
| `x`    | Password placeholder    |
| `27`   | Group ID                |
| `demo` | User belonging to group |

---

## adduser

## Meaning

`adduser` creates a new user account.

It is beginner-friendly and interactive.

## Syntax

```bash
sudo adduser username
```

## Example

```bash
sudo adduser testuser
```

It usually asks for:

* Password
* Full name
* Room number
* Phone details
* Confirmation

Most optional fields can be skipped by pressing Enter.

## Recall

`adduser` creates a user in an easier interactive way.

---

## useradd

## Meaning

`useradd` also creates a user account.

It is lower-level and less beginner-friendly than `adduser`.

## Example

```bash
sudo useradd testuser
```

To create a user with home directory:

```bash
sudo useradd -m testuser
```

Set password:

```bash
sudo passwd testuser
```

## adduser vs useradd

| Command   | Meaning                           |
| --------- | --------------------------------- |
| `adduser` | Easier interactive user creation  |
| `useradd` | Lower-level user creation command |

Simple recall:

```text
adduser is easier.
useradd is more manual.
```

---

## passwd

## Meaning

`passwd` changes or sets a user's password.

## Change Current User Password

```bash
passwd
```

## Change Another User Password

```bash
sudo passwd username
```

Example:

```bash
sudo passwd testuser
```

---

## usermod

## Meaning

`usermod` modifies an existing user account.

## Add User to a Group

```bash
sudo usermod -aG groupname username
```

Example:

```bash
sudo usermod -aG sudo testuser
```

Important:

Use `-aG`, not just `-G`.

| Option | Meaning             |
| ------ | ------------------- |
| `-a`   | Append              |
| `-G`   | Supplementary group |

Without `-a`, existing group memberships may be replaced. Beautiful disaster, very avoidable.

---

## groupadd

## Meaning

`groupadd` creates a new group.

## Syntax

```bash
sudo groupadd groupname
```

## Example

```bash
sudo groupadd supportteam
```

---

## groupdel

## Meaning

`groupdel` deletes a group.

## Syntax

```bash
sudo groupdel groupname
```

## Example

```bash
sudo groupdel supportteam
```

---

## deluser

## Meaning

`deluser` deletes a user account.

## Syntax

```bash
sudo deluser username
```

## Example

```bash
sudo deluser testuser
```

Delete user with home directory:

```bash
sudo deluser --remove-home testuser
```

---

## userdel

## Meaning

`userdel` also deletes a user account.

## Syntax

```bash
sudo userdel username
```

Delete user with home directory:

```bash
sudo userdel -r username
```

## deluser vs userdel

| Command   | Meaning                           |
| --------- | --------------------------------- |
| `deluser` | Easier user deletion command      |
| `userdel` | Lower-level user deletion command |

---

## Practice Example

Check current user:

```bash
whoami
```

Check user ID and group details:

```bash
id
```

Check current user's groups:

```bash
groups
```

Create a new group:

```bash
sudo groupadd supportteam
```

Create a new user:

```bash
sudo adduser testuser
```

Add user to group:

```bash
sudo usermod -aG supportteam testuser
```

Check user groups:

```bash
groups testuser
```

Create a folder:

```bash
mkdir shared-folder
```

Change group ownership:

```bash
sudo chgrp supportteam shared-folder
```

Give group access:

```bash
chmod 770 shared-folder
```

Check permissions:

```bash
ls -ld shared-folder
```

Delete test user:

```bash
sudo deluser --remove-home testuser
```

Delete test group:

```bash
sudo groupdel supportteam
```

---

## Common Mistakes

## Mistake 1

Using root account for normal work.

Bad habit:

```text
Always working as root.
```

Why it is bad:

Root has full control. One wrong command can damage the system.

Better:

```text
Use normal user account and sudo only when needed.
```

---

## Mistake 2

Forgetting `sudo`.

Example:

```bash
adduser testuser
```

Possible error:

```text
Permission denied
```

Fix:

```bash
sudo adduser testuser
```

---

## Mistake 3

Using `usermod -G` instead of `usermod -aG`.

Risk:

Existing groups may be removed.

Better:

```bash
sudo usermod -aG groupname username
```

---

## Mistake 4

Deleting a user without checking files.

Before deleting a user, check whether the user owns important files.

Useful command:

```bash
find / -user username 2>/dev/null
```

---

## Quick Recall Notes

* A user is a system account.
* A group is a collection of users.
* Groups help manage shared permissions.
* `whoami` shows current username.
* `id` shows UID, GID, and groups.
* `groups` shows group membership.
* Root is the super administrator.
* `sudo` runs a command with admin privileges.
* `su` switches user.
* `/etc/passwd` stores user account information.
* `/etc/shadow` stores encrypted password information.
* `/etc/group` stores group information.
* `adduser` creates a user interactively.
* `useradd` creates a user manually.
* `passwd` changes password.
* `usermod -aG` adds a user to a group.
* `groupadd` creates a group.
* `groupdel` deletes a group.
* `deluser` deletes a user.
* Use root carefully.

---

## Interview Questions

## 1. What is a user in Linux?

A user is an account that can log in and use the Linux system.

## 2. What is a group in Linux?

A group is a collection of users used to manage shared permissions.

## 3. Why are groups used?

Groups are used to give shared access to files, folders, and resources without assigning permissions separately to each user.

## 4. What does `whoami` do?

`whoami` shows the current logged-in username.

## 5. What does `id` show?

`id` shows user ID, group ID, and group membership.

## 6. What does `groups` show?

`groups` shows which groups a user belongs to.

## 7. What is the root user?

The root user is the main administrator account with full control over the Linux system.

## 8. What does `sudo` do?

`sudo` allows a permitted user to run commands with administrator privileges.

## 9. What is the difference between `su` and `sudo`?

`su` switches to another user.
`sudo` runs a single command with administrator privileges.

## 10. What is stored in `/etc/passwd`?

`/etc/passwd` stores user account information such as username, UID, GID, home directory, and shell.

## 11. What is stored in `/etc/group`?

`/etc/group` stores group information and group membership details.

## 12. What is the difference between `adduser` and `useradd`?

`adduser` is easier and interactive.
`useradd` is lower-level and more manual.

## 13. How do you add a user to a group?

Use:

```bash
sudo usermod -aG groupname username
```

## 14. Why is `usermod -aG` safer than only `usermod -G`?

`-aG` appends the user to a group without removing existing group memberships.

## 15. How do you delete a user with their home directory?

Use:

```bash
sudo deluser --remove-home username
```

or:

```bash
sudo userdel -r username
```
