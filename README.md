# 🐧 Linux Shell Lab 2 – File Management & Redirection

In this lab, I practiced **Linux shell commands**, including `sudo` usage, directory management, file archiving, compression, searching, and file redirection.

---

## 📋 Lab Overview

**Goal:**

* Practice navigating the Linux filesystem
* Create, move, and compress directories
* Use `find` and `grep` to locate files and strings
* Redirect output to files
* Run Python scripts and capture errors

**Learning Outcomes:**

* Use `sudo` for privileged commands
* Create directories efficiently with `mkdir -p`
* Compress and extract files using `tar` and `gzip`
* Redirect command output and errors using `>` and `2>`
* Use `find` and `grep` for filesystem searches

---

## 🛠 Step-by-Step Journey

### Step 1: Switch to Superuser

```bash
sudo su
```

* Enter the password when prompted
* This allows running multiple commands without repeatedly typing `sudo`

💡 **Tip:** `sudo su` opens a root shell to simplify privilege management.

---

### Step 2: Create a Tarball and Compress It

**Task:** Archive a directory and compress it using gzip.

```bash
tar -cf python.tar /home/user/reptile/snake/Python
gzip python.tar
```

* Result: `/home/user/python.tar.gz`
* Warning about “removing leading `/`” can be ignored

💡 **Tip:** Use `tar -cf` to create archives, `gzip` to compress them.

---

### Step 3: Extract a Compressed File

**Task:** Extract `eaglet.dat.gz` in the same directory.

```bash
gunzip /home/user/birds/eagle/eaglet.dat.gz
```

* This decompresses the file without affecting other directories

💡 **Tip:** `gunzip` is used to uncompress `.gz` files.

---

### Step 4: Locate a File in `/opt`

**Task:** Find a file when the exact location is unknown.

```bash
find /opt -name calistone-code
```

* Output example: `/opt/test/test123/calistone/calistone-code`

💡 **Tip:** `find <directory> -name <filename>` searches recursively.

---

### Step 5: Save Absolute Path of a File

**Task:** Locate `dummy.service` in `/etc` and save its absolute path.

```bash
find /etc -name dummy.service
echo /etc/systemd/system/dummy.service > /home/user/dummy-service
```

* Creates `/home/user/dummy-service` containing the full path

💡 **Tip:** Use `>` to overwrite and `>>` to append output to a file.

---

### Step 6: Search for a String in Files

**Task:** Find a specific IP address in `/etc` and save its absolute path.

```bash
grep -R "172.16.238.197" /etc
echo /etc/path/to/file > /home/user/ip
```

* `grep -R` recursively searches files for a string
* Redirect the absolute path to a file for later reference

---

### Step 7: Create a New File with Content

**Task:** Create `file_with_data.txt` containing a single line.

```bash
echo "A file in my home directory" > /home/user/file_with_data.txt
```

* Creates the file and writes content in one command

💡 **Tip:** `>` creates or overwrites a file; `>>` appends.

---

### Step 8: Redirect Python Script Output and Errors

**Task:** Run a Python script and redirect **standard error** to a file.

```bash
python3 /home/user/my_python_test.py 2> /home/user/py_error.txt
```

* Captures any errors during execution into `py_error.txt`

💡 **Tip:** Use `2>` for redirecting stderr, `>` for stdout, and `&>` for both.

---

### Step 9: Read Compressed Manual Pages and Save Output

**Task:** Read a compressed manual file and save contents to another file.

```bash
zcat /usr/share/man/man1/tail.1.gz > /home/user/pipes
```

* Extracts the compressed manual and redirects output to `/home/user/pipes`

💡 **Tip:** `zcat` reads `.gz` files without uncompressing them permanently.

---

## ✅ Key Commands Summary

| Task                              | Command                                          |
| --------------------------------- | ------------------------------------------------ |
| Open root shell                   | `sudo su`                                        |
| Create directory                  | `mkdir -p /path/to/dir`                          |
| Tarball and compress              | `tar -cf archive.tar <dir>` + `gzip archive.tar` |
| Extract gz file                   | `gunzip file.gz`                                 |
| Find file by name                 | `find /dir -name filename`                       |
| Search string recursively         | `grep -R "string" /dir`                          |
| Save output to file               | `echo <text> > /path/file`                       |
| Redirect Python errors            | `python3 script.py 2> errors.txt`                |
| Read compressed file and redirect | `zcat file.gz > output.txt`                      |

---

## 💡 Notes / Tips

* Always use `sudo` for privileged commands
* Use `mkdir -p` to create nested directories in one command
* `tar` and `gzip` are standard tools for archiving and compression
* Redirect operators `>` and `2>` are essential for capturing output and errors
* `find` and `grep -R` are powerful for locating files and strings

---

## 📌 Lab Summary

| Step                            | Status | Key Takeaways                                |
| ------------------------------- | ------ | -------------------------------------------- |
| Switch to root                  | ✅      | Simplifies privilege management              |
| Tarball and gzip                | ✅      | Archive and compress directories efficiently |
| Extract compressed file         | ✅      | `gunzip` restores compressed files           |
| Locate file in `/opt`           | ✅      | Recursive `find` command                     |
| Save absolute path to file      | ✅      | Use `>` to redirect output                   |
| Search for string in `/etc`     | ✅      | `grep -R` for recursive search               |
| Create a new file with content  | ✅      | `echo` with redirection                      |
| Redirect Python errors          | ✅      | Capture stderr separately                    |
| Read `.gz` file and save output | ✅      | Use `zcat` for compressed files              |

---

## ✅ References

* [Linux `tar` Manual](https://man7.org/linux/man-pages/man1/tar.1.html)
* [Linux `gzip` Manual](https://man7.org/linux/man-pages/man1/gzip.1.html)
* [Linux `find` Command](https://man7.org/linux/man-pages/man1/find.1.html)
* [Linux `grep` Command](https://man7.org/linux/man-pages/man1/grep.1.html)
* [Linux Redirection Operators](https://tldp.org/LDP/abs/html/io-redirection.html)
