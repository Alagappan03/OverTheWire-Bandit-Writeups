# Bandit Level 2 → Level 3

## Objective

The goal of this level is to retrieve the password for **Bandit Level 3**. The password is stored in a file named `--spaces in this filename--` located in the home directory.

---

## Challenge Overview

This level introduces two important Linux concepts:

* File names can contain **spaces**.
* File names that begin with `-` or `--` may be interpreted as command-line options instead of regular files.

To access the file correctly, we must tell the shell and the command that it is a filename rather than an option.

---

## Commands Used

### 1. Connect to the Server

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

**Explanation**

* `ssh` establishes a secure connection to the Bandit server.
* `bandit2` is the username.
* `-p 2220` specifies the SSH port.

---

### 2. List the Files

```bash
ls
```

**Output**

```text
--spaces in this filename--
```

**Explanation**

The `ls` command displays the files in the current directory.

---

### 3. Read the File

```bash
cat "./--spaces in this filename--"
```

**Alternative Solution**

```bash
cat -- "--spaces in this filename--"
```

**Explanation**

* The filename contains spaces, so it is enclosed in quotes.
* The filename starts with `--`, which could be interpreted as a command option.
* Prefixing it with `./` tells Linux that it is a file in the current directory.
* Alternatively, `--` tells the command to stop processing options and treat everything after it as a filename.

The output contains the password for the next level.

> **Password intentionally omitted** to respect the OverTheWire challenge.

---

## Concepts Learned

* Handling filenames that contain spaces.
* Understanding why commands interpret filenames beginning with `-` or `--` as options.
* Using `./` to reference files in the current directory.
* Using `--` to stop option parsing.

---

## Commands Learned

| Command | Purpose                                                        |
| ------- | -------------------------------------------------------------- |
| `ssh`   | Connect to a remote Linux server                               |
| `ls`    | List files in the current directory                            |
| `cat`   | Display the contents of a file                                 |
| `./`    | Reference a file in the current directory                      |
| `--`    | Stop option parsing and treat following arguments as filenames |

---

## Screenshots

<img width="2880" height="1432" alt="l3-bandit -1" src="https://github.com/user-attachments/assets/d16f8c62-f5f8-4d3a-abd9-df2d0d5935c0" />
---
<img width="2864" height="1236" alt="l3-bandit -2" src="https://github.com/user-attachments/assets/d9db3d42-4185-409d-95b0-9f4d52ee7d43" />
---
<img width="2880" height="130" alt="l3-bandit -3" src="https://github.com/user-attachments/assets/88441ba9-3855-42c0-b36f-4e1f35c4b185" />

Key Takeaways

* Spaces in filenames require quotes or escaped spaces.
* Filenames beginning with `-` or `--` can be mistaken for command options.
* `./` and `--` are useful techniques for safely accessing such files.
* Understanding shell argument parsing helps solve many Linux command-line problems.
