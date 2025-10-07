**Topic :** Learning linux
**Reference :** Linux Cheat Sheet By Geeks for Geeks + Chatgpt


# PWD

**Introduction:** Displays the current working directory path.
**Command:** `pwd`
**Example:** /home/user/Documents

# LS

**Introduction:** Lists all files and directories in the current directory.
**Command:** `ls`
**Example:** ls -l

# MKDIR

**Introduction:** Creates a new directory.
**Command:** `mkdir [directory_name]`
**Example:** mkdir new_folder

# CD

**Introduction:** Changes the current directory.
**Command:** `cd [directory_name]`
**Example:** cd /home/user/Desktop

# RMDIR 

**Introduction:** Removes an empty directory.
**Command:** `rmdir [directory_name]`
**Example:** rmdir temp_folder

# RM

**Introduction:** Removes files or directories.
**Command:** `rm [file_name]`
**Example:** rm file.txt

# CP

**Introduction:** Copies files or directories.
**Command:** `cp [source] [destination]`
**Example:** cp notes.txt /home/user/backup/

# MV

**Introduction:** Moves or renames files and directories.
**Command:** `mv [source] [destination]`
**Example:** mv oldname.txt newname.txt

# TOUCH

**Introduction:** Creates an empty file or updates its timestamp.
**Command:** `touch [file_name]`
**Example:** touch newfile.txt

# CAT 

**Introduction:** Displays the content of a file.
**Command:** `cat [file_name]`
**Example:** cat readme.txt

# HEAD

**Introduction:** Displays the first 10 lines of a file by default.
**Command:** `head [file_name]`
**Example:** head log.txt

# TAIL

**Introduction:** Displays the last 10 lines of a file.
**Command:** `tail [file_name]`
**Example:** tail error.log

# GREP

**Introduction:** Searches for a specific pattern in a file.
**Command:** `grep [pattern] [file_name]`
**Example:** grep 'error' server.log

# CHMOD

**Introduction:** Changes file permissions.
**Command:** `chmod [permissions] [file_name]`
**Example:** chmod 755 script.sh

# CHOWN

**Introduction:** Changes ownership of a file or directory.
**Command:** `chown [user]:[group] [file_name]`
**Example:** chown root:root config.txt

#  DF

**Introduction:** Displays disk space usage of file systems.
**Command:** `df -h`
**Example:** df -h

# DU

**Introduction:** Displays disk usage of files and directories.
**Command:** `du -h`
**Example:** du -h /home/user/Documents

# FREE

**Introduction:** Displays memory usage statistics.
**Command:** `free -h`
**Example:** free -h

# UNAME

**Introduction:** Displays system information.
**Command:** `uname -a`
**Example:** uname -a

# TOP

**Introduction:** Displays running processes and system resource usage.
**Command:**`top`
**Example**: top

# PS

**Introduction:** Displays running processes.
**Command:** `ps -aux`
**Example:** ps -aux

# KILL

**Introduction:** Terminates a process using its Process ID (PID).
**Command:** `kill [PID]`
Example: kill 1023

# PING 

**Introduction:** Checks network connectivity with a host.
**Command:** `ping [hostname]`
**Example:** ping google.com

# IFCONFIG

**Introduction:** Displays or configures network interface information.
**Command:** `ifconfig`
**Example:** ifconfig

# IP ADDR 

**Introduction:** Displays IP address and network details.
**Command:** `ip addr show`
**Example:** ip addr show

# CURL 

**Introduction:** Transfers data from or to a server using URLs.
**Command:** `curl [URL]`
**Example:** curl https://example.com

# WGET

**Introduction:** Downloads files from the internet.
**Command:** `wget [URL]`
**Example**: wget https://example.com/file.zip

# TAR 

**Introduction:** Creates or extracts .tar archive files.
**Command:** tar -`cvf archive.tar files/`
**Example:** tar -xvf archive.tar

# ZIP

**Introduction:** Compresses files into a zip archive.
**Command:** `zip [archive_name.zip] [files]`
**Example:** zip project.zip *.txt

# UNZIP

**Introduction:** Extracts .zip archive files.
**Command:** `unzip [archive_name.zip]`
**Example:** unzip project.zip

# ADDUSER

**Introduction:** Creates a new user account.
**Command:**` adduser [username]`
**Example:** adduser john

# PASSWD

**Introduction:** Changes the password for a user.
**Command:** `passwd [username]`
**Example:** passwd john

# WHOAMI

**Introduction:** Displays the current logged-in username.
**Command:** `whoami`
**Example:** whoami

# HISTORY

**Introduction:** Displays a list of previously executed commands.
**Command:** `history`
**Example:** history

# CLEAR

**Introduction:** Clears the terminal screen.
**Command:** `clear`
**Example:** clear

# ECHO

**Introduction:** Displays a line of text or variable value.
**Command:** `echo [text]`
**Example:** echo 'Hello, Linux!'

# MAN 

**Introduction:** Displays the manual page for a command.
**Command**: `man [command]`
**Example:** man ls

# LOCATE

**Introduction:** Finds files by name quickly using an index.
**Command:** `locate [file_name]`
**Example:** locate notes.txt

# FIND

**Introduction:** Searches for files in a directory hierarchy.
**Command:** `find [path] -name [file_name]`
**Example:** find /home -name notes.txt

# EXIT

**Introduction:** Exits the terminal or current session.
**Command:** `exit`
**Example:** exit