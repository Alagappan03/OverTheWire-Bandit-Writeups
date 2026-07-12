# 🏴 Bandit Level 1 → Level 2

## 🎯 Objective

The goal of this level is to find the password for **Bandit Level 2**. The password is stored in a file named `-` located in the home directory.

---

## 🧠 Challenge Overview

Unlike the previous level, the file name is simply `-` (a single dash). In Linux, a dash is commonly treated as a special argument by many commands instead of a normal filename. Because of this, we need to specify that it is a file in the current directory.

---

## 🛠 Commands Used

### 1. Connect to the Bandit Server

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

**Explanation**

* `ssh` establishes a secure connection to the remote Linux server.
* `bandit1` is the username for this level.
* `-p 2220` specifies the SSH port.

---

### 2. List the Files

```bash
ls
```

**Output**

```text
-
```

**Explanation**

The `ls` command lists the files in the current directory. Here, it shows that there is a file named `-`.

---

### 3. Read the File

```bash
cat ./-
```

**Explanation**

* `cat` displays the contents of a file.
* `./` refers to the current directory.
* `./-` tells Linux to treat `-` as a filename instead of a special command argument.

The output contains the password for the next Bandit level.

> **Password intentionally omitted** to respect the OverTheWire challenge.

---

## 💡 Why Doesn't `cat -` Work?

Many Linux commands interpret `-` as a special argument (often meaning **standard input**). As a result, `cat -` waits for input from the keyboard instead of reading the file.

By using:

```bash
cat ./-
```

we explicitly tell Linux to read the file named `-` from the current directory.

---

## 📚 Concepts Learned

* Special filenames in Linux.
* The meaning of `./` (current directory).
* How command-line programs may interpret `-` as a special option.
* How to access files with unusual names.

---

## 📖 Commands Learned

| Command | Purpose                             |
| ------- | ----------------------------------- |
| `ssh`   | Connect to a remote Linux server    |
| `ls`    | List files in the current directory |
| `cat`   | Display the contents of a file      |
| `./`    | Refer to the current directory      |

---

## 📸 Suggested Screenshots

* SSH login to Bandit Level 1
* Output of the `ls` command
* Running `cat ./-`

> ⚠️ Remember to blur or crop out the password before uploading screenshots.

---

## ✅ Key Takeaways

* File names can contain special characters.
* `-` is often interpreted as a special argument by Linux commands.
* Using `./` allows Linux to recognize `-` as a filename in the current directory.
* Understanding how the shell interprets filenames is an important Linux skill.
