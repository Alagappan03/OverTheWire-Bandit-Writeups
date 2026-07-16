## Bandit Level 4 → Level 5

## Objective

The goal of this level is to retrieve the password for **Bandit Level 5**. The password is stored in the **only human-readable file** inside the `inhere` directory.

---

## Challenge Overview

This level introduces the `file` command, which helps identify the type of a file.

The `inhere` directory contains multiple files. Most of them contain binary or non-readable data, while only one contains plain text that can be read by humans.

Instead of opening every file manually, we can use the `file` command to determine which file is human-readable.

---

## Commands Used

### 1. Connect to the Server

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

**Explanation**

* `ssh` creates a secure connection to the Bandit server.
* `bandit4` is the username.
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

The `ls` command displays the files and directories in the current location.

---

### 3. Change Directory

```bash
cd inhere
```

**Explanation**

The `cd` command changes the current working directory to `inhere`.

---

### 4. Identify File Types

```bash
file ./*
```

**Explanation**

* `file` identifies the type of each file.
* `./*` means "all files in the current directory."

Example output:

```text
./-file00: data
./-file01: data
./-file02: ASCII text
./-file03: data
...
```

The file labeled **ASCII text** is the human-readable file.

---

### 5. Read the Human-Readable File

```bash
cat ./-file02
```

> Replace `-file02` with the actual filename identified by the `file` command.

**Explanation**

The filename begins with `-`, which Linux may interpret as a command option. Prefixing it with `./` tells Linux that it is a file located in the current directory.

The output contains the password for the next Bandit level.

> **Password intentionally omitted** to respect the OverTheWire challenge.

---

## Concepts Learned

* Using the `file` command to determine file types.
* Identifying human-readable files among binary files.
* Using wildcards (`*`) to process multiple files.
* Understanding why filenames beginning with `-` require `./`.

---

## Commands Learned

| Command | Purpose                                   |
| ------- | ----------------------------------------- |
| `ssh`   | Connect to a remote Linux server          |
| `ls`    | List files and directories                |
| `cd`    | Change the current directory              |
| `file`  | Identify the type of a file               |
| `cat`   | Display the contents of a file            |
| `./`    | Reference a file in the current directory |
| `*`     | Match all files in the current directory  |

---

## Suggested Screenshots

<img width="2880" height="1130" alt="l5_bandit-1" src="https://github.com/user-attachments/assets/577f117d-a195-4c44-80db-cddd202d8a0a" />

<img width="2872" height="626" alt="l5_bandit-2" src="https://github.com/user-attachments/assets/16c077a6-a843-4358-971e-8245030db119" />

<img width="2880" height="132" alt="l5_bandit-3" src="https://github.com/user-attachments/assets/0d2ce05e-cde1-44d2-bb4e-c7bc4ad00ad9" />

---

## My Notes

At first, I tried using `cat -file07`, but Linux treated `-f` as an option instead of a filename. I learned that prefixing the filename with `./` tells the shell to treat it as a file in the current directory.

---

## Key Takeaways

* The `file` command helps identify different file types.
* Human-readable files are typically reported as **ASCII text**.
* Wildcards (`*`) make it easy to work with multiple files at once.
* Filenames beginning with `-` should be referenced using `./` to avoid being interpreted as command options.

