### **2. Basic Linux Commands**

---

Learning basic Linux commands is essential for managing and navigating the Linux filesystem, performing file operations, editing text files, and managing file permissions. This section covers commands for navigating the filesystem, file manipulation, text editing, and managing permissions and ownership in both **RedHat** and **Ubuntu** Linux.

---

#### **Navigating the Filesystem**

1. **`ls` (List Directory Contents)**:
   - The `ls` command lists files and directories in the current working directory.
   
   **Example**:
   ```bash
   ls
   ```
   - To list hidden files (files starting with a dot `.`):
   ```bash
   ls -a
   ```
   - To list detailed information (permissions, owner, size, etc.):
   ```bash
   ls -l
   ```
   - Combine options (show hidden files in detailed format):
   ```bash
   ls -la
   ```

2. **`cd` (Change Directory)**:
   - The `cd` command is used to navigate between directories.

   **Example**:
   - To change to the `/home` directory:
   ```bash
   cd /home
   ```
   - To go back to the previous directory:
   ```bash
   cd -
   ```
   - To navigate up one level in the directory tree:
   ```bash
   cd ..
   ```

3. **`pwd` (Print Working Directory)**:
   - The `pwd` command shows the current working directory.

   **Example**:
   ```bash
   pwd
   ```
   Output:
   ```bash
   /home/user
   ```

4. **`find` (Search for Files and Directories)**:
   - `find` is used to search for files and directories based on criteria like name, size, modification time, etc.

   **Example**:
   - To find files named "test.txt" in the `/home` directory:
   ```bash
   find /home -name "test.txt"
   ```

5. **`locate` (Find Files by Name)**:
   - The `locate` command is a faster alternative to `find`, using a pre-built index to search files.
   
   **Example**:
   ```bash
   locate test.txt
   ```

---

#### **File Operations**

1. **`cp` (Copy Files and Directories)**:
   - Copies files and directories from one location to another.
   
   **Example**:
   - To copy a file:
   ```bash
   cp file1.txt /path/to/destination/
   ```
   - To copy a directory and its contents:
   ```bash
   cp -r /source/directory /path/to/destination/
   ```

2. **`mv` (Move or Rename Files)**:
   - Moves or renames files and directories.
   
   **Example**:
   - To rename a file:
   ```bash
   mv oldname.txt newname.txt
   ```
   - To move a file to another directory:
   ```bash
   mv file1.txt /path/to/destination/
   ```

3. **`rm` (Remove Files and Directories)**:
   - Deletes files and directories.
   
   **Example**:
   - To remove a file:
   ```bash
   rm file1.txt
   ```
   - To remove a directory and its contents:
   ```bash
   rm -r /path/to/directory/
   ```

4. **`touch` (Create Empty Files)**:
   - Creates an empty file or updates the timestamp of an existing file.
   
   **Example**:
   ```bash
   touch newfile.txt
   ```

5. **`mkdir` (Make Directory)**:
   - Creates a new directory.
   
   **Example**:
   ```bash
   mkdir new_directory
   ```
   - To create a nested directory structure:
   ```bash
   mkdir -p /path/to/new_directory/sub_directory
   ```

6. **`rmdir` (Remove Empty Directory)**:
   - Deletes an empty directory.
   
   **Example**:
   ```bash
   rmdir empty_directory
   ```

7. **`cat` (Concatenate and Display File Contents)**:
   - Displays the contents of a file.
   
   **Example**:
   ```bash
   cat file.txt
   ```

8. **`more` and `less` (Paging Through File Contents)**:
   - `more` and `less` allow you to view large files one screen at a time.
   
   **Example**:
   ```bash
   more largefile.txt
   ```
   ```bash
   less largefile.txt
   ```

---

#### **Working with Text Files**

1. **`nano` (Simple Text Editor)**:
   - `nano` is a straightforward, user-friendly text editor for command-line environments.
   
   **Example**:
   - To create or edit a file using `nano`:
   ```bash
   nano newfile.txt
   ```
   - Inside `nano`, use `Ctrl + O` to save and `Ctrl + X` to exit.

2. **`vi` or `vim` (Advanced Text Editor)**:
   - `vi` (or its enhanced version `vim`) is a powerful text editor with modes for editing and command execution.
   
   **Example**:
   - To open a file using `vi`:
   ```bash
   vi file.txt
   ```
   - In `vi`, press `i` to enter **insert mode** (for editing).
   - Press `Esc` to exit **insert mode** and return to **command mode**.
   - To save and exit:
   ```bash
   :wq
   ```

3. **`head` (View the First Few Lines of a File)**:
   - Displays the first 10 lines of a file by default.
   
   **Example**:
   ```bash
   head file.txt
   ```

4. **`tail` (View the Last Few Lines of a File)**:
   - Displays the last 10 lines of a file by default. Useful for monitoring log files.
   
   **Example**:
   ```bash
   tail file.txt
   ```
   - To continuously view updates to a file (useful for logs):
   ```bash
   tail -f logfile.log
   ```

---

#### **Permissions and Ownership**

Linux uses a permission model to control who can read, write, and execute files and directories. Every file has an owner and a group associated with it, and permissions for the owner, group, and others.

1. **File Permissions Format**:
   - Permissions are displayed as a string of 10 characters (e.g., `-rwxr-xr--`):
     - The first character indicates whether it’s a directory (`d`) or a file (`-`).
     - The next three characters represent **owner** permissions (r = read, w = write, x = execute).
     - The next three represent **group** permissions.
     - The last three represent **others** permissions.

2. **`chmod` (Change File Permissions)**:
   - `chmod` is used to change the read (`r`), write (`w`), and execute (`x`) permissions of a file.

   **Examples**:
   - Grant **read**, **write**, and **execute** permissions to the file owner, **read** and **execute** permissions to the group, and no permissions to others:
   ```bash
   chmod 750 file.txt
   ```
   Breakdown of `750`:
   - `7` (owner) = read (4) + write (2) + execute (1) = 7
   - `5` (group) = read (4) + execute (1) = 5
   - `0` (others) = no permissions

   - To give all users (owner, group, and others) **read** and **write** permissions:
   ```bash
   chmod 666 file.txt
   ```

3. **`chown` (Change File Ownership)**:
   - `chown` changes the owner of a file or directory.

   **Example**:
   - To change the owner of a file to user `john`:
   ```bash
   chown john file.txt
   ```
   - To change both the owner and group:
   ```bash
   chown john:admin file.txt
   ```

4. **`chgrp` (Change Group Ownership)**:
   - `chgrp` changes the group ownership of a file or directory.
   
   **Example**:
   ```bash
   chgrp admin file.txt
   ```

---

### **Examples**

#### **1. Create a Directory in RedHat and Ubuntu**

1. Create a directory:
   ```bash
   mkdir my_directory
   ```
2. Create a nested directory structure:
   ```bash
   mkdir -p parent_directory/child_directory
   ```

#### **2. Create, Edit, and Delete Files Using `nano` and `vi` in RedHat and Ubuntu**

1. Create a file using `nano`:
   ```bash
   nano newfile.txt
   ```
   - Add some text, then save with `Ctrl + O` and exit with `Ctrl + X`.

2. Create a file using `vi`:
   ```bash
   vi newfile.txt
   ```
   - Press `i` to enter insert mode, type some text, then press `Esc` to return to command mode.
   - Save and exit with `:wq`.

3. Delete the file:
   ```bash
   rm newfile.txt
   ```

#### **3. Change File Permissions Using `chmod`**

1

. Give the owner read, write, and execute permissions, the group read and execute permissions, and others no permissions:
   ```bash
   chmod 750 script.sh
   ```

2. Allow everyone to read and write a file:
   ```bash
   chmod 666 document.txt
   ```

---

Mastering these basic commands will give you the foundation needed to perform many essential tasks on a Linux system, regardless of the distribution you're using!
