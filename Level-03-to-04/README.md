# Bandit Level 3 → Level 4

## Objective

The goal of this level is to retrieve the password for **Bandit Level 4**. The password is stored in a **hidden file** inside the `inhere` directory.

---

## Challenge Overview

In Linux, files and directories whose names begin with a dot (`.`) are considered **hidden**. The standard `ls` command does not display hidden files, so we need to use the appropriate option to reveal them.

This level introduces the concept of navigating directories and working with hidden files.

---

## Commands Used

### 1. Connect to the Server

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

**Explanation**

* `ssh` establishes a secure connection to the remote Linux server.
* `bandit3` is the username for this level.
* `-p 2220` specifies the SSH port.

---

### 2. List the Files

```bash
ls
```

**Output**

```text
inhere
```

**Explanation**

The `ls` command lists the files and directories in the current location. Here, it shows that there is a directory named `inhere`.

---

### 3. Change Directory

```bash
cd inhere
```

**Explanation**

The `cd` (change directory) command is used to move into the `inhere` directory.

---

### 4. Display Hidden Files

```bash
ls -a
```

**Explanation**

The `-a` option stands for **all**. It displays every file, including hidden files whose names begin with a dot (`.`).

The output includes a hidden file that contains the password for the next level.

---

### 5. Read the Hidden File

```bash
cat <hidden-file-name>
```

**Example**

```bash
cat ...Hiding-From-You
```

**Explanation**

The `cat` command displays the contents of the hidden file, revealing the password for the next level.

> **Password intentionally omitted** to respect the OverTheWire challenge.

---

## Concepts Learned

* How to navigate directories using `cd`.
* Hidden files in Linux begin with a dot (`.`).
* The `ls` command does not display hidden files by default.
* The `ls -a` command displays all files, including hidden ones.
* The `cat` command reads the contents of a file.

---

## Commands Learned

| Command | Purpose                                   |
| ------- | ----------------------------------------- |
| `ssh`   | Connect to a remote Linux server          |
| `ls`    | List files and directories                |
| `cd`    | Change the current directory              |
| `ls -a` | Display all files, including hidden files |
| `cat`   | Display the contents of a file            |

---

## Suggested Screenshots

<img width="2876" height="1152" alt="l3_bandit-1" src="https://github.com/user-attachments/assets/8fcad232-6c47-420d-997e-e509cbe8d6c0" />

<img width="2876" height="268" alt="l3_bandit-2" src="https://github.com/user-attachments/assets/92184dd9-daa6-4b2f-97da-080f417708cb" />

<img width="2880" height="104" alt="l3_bandit-3" src="https://github.com/user-attachments/assets/1696b6b0-8902-4b4b-a0a6-1695453cabc5" />


## Key Takeaways

* Hidden files are identified by a leading dot (`.`).
* `ls -a` is required to view hidden files.
* Directory navigation using `cd` is a fundamental Linux skill.
* Reading and understanding the challenge objective helps determine which commands to use.
