# Bandit Level 0 → Level 1

## Objective

The password for the next level is stored in a file named `readme` in the home directory.

---

## Commands Used

### Connect to the Bandit Server

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

**Explanation**

* `ssh` starts a secure remote connection.
* `bandit0` is the username.
* `bandit.labs.overthewire.org` is the remote server.
* `-p 2220` tells SSH to use port 2220.

---

### List Files

```bash
ls
```

**Explanation**

The `ls` command lists all files and directories in the current directory.

Output:

```text
readme
```

---

### Read the File

```bash
cat readme
```

**Explanation**

The `cat` command displays the contents of a file.

The output contains the password for the next Bandit level.

> Password intentionally omitted.

---

## Concepts Learned

* What SSH is and how to connect to a remote Linux machine.
* Linux hides passwords while typing for security.
* The home directory is represented by `~`.
* `ls` lists files in the current directory.
* `cat` displays the contents of a text file.

---

## Commands Learned

| Command | Purpose                          |
| ------- | -------------------------------- |
| `ssh`   | Connect to a remote Linux server |
| `ls`    | List files and folders           |
| `cat`   | Display the contents of a file   |

---

## Key Takeaways

* Always read the challenge objective carefully before using commands.
* Use SSH to access remote Linux systems securely.
* Learn what each command does instead of memorizing solutions.
* Save passwords locally, but do not publish them.
