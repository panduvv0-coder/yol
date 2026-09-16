# Basic Linux Commands

This guide provides an introduction to fundamental Linux commands for interacting with the file system, viewing files, controlling processes, and getting system information.

## Navigation

### pwd
Print the absolute path of the current working directory.

```bash
pwd
```

### ls
List files and directories in the target location.

```bash
ls
```

List detailed information including permissions, owner, size, and modification date:

```bash
ls -l
```

List all files including hidden files starting with `.`:

```bash
ls -la
```

### cd
Change current directory.

Move to a specific directory:

```bash
cd /path/to/directory
```

Navigate to your home directory:

```bash
cd ~
```

Move up one directory level:

```bash
cd ..
```

## File & Directory Management

### mkdir
Create a new directory.

```bash
mkdir my_folder
```

Create nested parent directories if they do not exist:

```bash
mkdir -p parent/child/nested
```

### touch
Create an empty file or update timestamps of an existing file.

```bash
touch newfile.txt
```

### cp
Copy files or directories.

Copy a file:

```bash
cp file1.txt file2.txt
```

Copy a directory recursively:

```bash
cp -r folder1 folder2
```

### mv
Move or rename files and directories.

Rename a file:

```bash
mv oldname.txt newname.txt
```

Move a file to a different directory:

```bash
mv file.txt /path/to/destination/
```

### rm
Delete files or directories.

> ⚠️ **Warning**: The `rm` command permanently deletes files. There is no trash bin in the command line! Always double-check path inputs before running `rm -rf`.

Remove a file:

```bash
rm file.txt
```

Recursively and forcefully remove a directory and its contents:

```bash
rm -rf directory_name
```

## Viewing Files

### cat
Display file contents or concatenate files.

```bash
cat file.txt
```

### less
View file contents page-by-page. Press `q` to exit.

```bash
less largefile.txt
```

### head
View the first few lines of a file (defaults to 10 lines).

```bash
head file.txt
```

Specify the number of lines to display:

```bash
head -n 20 file.txt
```

### tail
View the last few lines of a file (defaults to 10 lines).

```bash
tail file.txt
```

Monitor a file in real-time for changes (useful for log files):

```bash
tail -f logfile.log
```

## Searching

### find
Search for files and directories in a directory hierarchy based on name or criteria.

```bash
find . -name "*.txt"
```

### grep
Search for matching text patterns inside files.

```bash
grep "search_term" file.txt
```

Perform a case-insensitive search recursively through directories:

```bash
grep -rn "search_term" /path/to/search/
```

## Permissions & Ownership

### chmod
Change access permissions (read `r`, write `w`, execute `x`) of a file or directory.

```bash
chmod +x script.sh
```

Set permission using octal notation:

```bash
chmod 755 file.txt
```

### chown
Change file owner and group.

Change user owner:

```bash
chown user file.txt
```

Change user owner and group together:

```bash
chown user:group file.txt
```

## System Info

### whoami
Display the username of the current user.

```bash
whoami
```

### uname
Display system and kernel details.

```bash
uname -a
```

### df
Display disk space usage for file systems.

```bash
df -h
```

### du
Estimate file and directory space usage.

```bash
du -sh directory_name
```

## Process Control

### top
Display real-time Linux process viewer and resource usage. Press `q` to exit.

```bash
top
```

### ps
List currently running processes.

```bash
ps aux
```

### kill
Terminate a process using its Process ID (PID).

```bash
kill 1234
```

> ⚠️ **Warning**: Forcefully killing a process (`kill -9 PID`) does not give the process a chance to save state or clean up resources.

```bash
kill -9 1234
```

## Getting Help

### man
Display the official user manual page for a command. Press `q` to exit.

```bash
man ls
```

### --help
Display help summary and available options for a command.

```bash
ls --help
```

---

## Command Cheat-Sheet

| Command | Description | Example Usage |
| ------- | ----------- | ------------- |
| `pwd` | Print working directory | `pwd` |
| `ls` | List directory contents | `ls -la` |
| `cd` | Change directory | `cd /var/log` |
| `mkdir` | Make directory | `mkdir -p docs/notes` |
| `touch` | Create empty file | `touch notes.txt` |
| `cp` | Copy files/folders | `cp -r src/ dst/` |
| `mv` | Move/rename files | `mv file1.txt file2.txt` |
| `rm` | Remove files/folders | `rm -rf old_folder/` |
| `cat` | Concatenate and print file content | `cat file.txt` |
| `less` | Page-through file content | `less file.txt` |
| `head` | View top lines of file | `head -n 5 file.txt` |
| `tail` | View bottom lines of file | `tail -f app.log` |
| `find` | Search for files in directory tree | `find . -name "*.sh"` |
| `grep` | Search text patterns in files | `grep -rn "error" logs/` |
| `chmod` | Change file permissions | `chmod +x run.sh` |
| `chown` | Change file ownership | `chown user:group file.txt` |
| `whoami` | Print current username | `whoami` |
| `uname` | Print kernel & system information | `uname -a` |
| `df` | Display filesystem disk usage | `df -h` |
| `du` | Display directory space usage | `du -sh folder/` |
| `top` | Interactive process viewer | `top` |
| `ps` | Report current process snapshot | `ps aux` |
| `kill` | Send signal to terminate process | `kill 1234` |
| `man` | Display command manual | `man grep` |
| `--help` | Print command usage help summary | `grep --help` |
