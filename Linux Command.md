 # Linux-Base-Knowledge

1.  **What Linux is?**  
Linux is an `operating system` (OS) built on the `Linux kernel.` It is `open-source` and free to use.
###

2.  **Where can Linux be used?**

- Servers (web servers, database servers, etc.) → Examples: Ubuntu Server, CentOS, Debian.
- Desktop computers → Examples: Ubuntu Desktop, Linux Mint, Fedora.
- Embedded devices → Examples: routers, IoT devices, Android.
- Supercomputers & Cloud → Most cloud platforms like AWS, Google Cloud, and Azure run on Linux.
###

3.  **Linux has many variants called distributions (distros).**  
Each distro has different package management systems and purposes.

| **Category**         | **Example Distros**               | **Description** |
|----------------------|-----------------------------------|-----------------|
| **Debian-based**     | Ubuntu, Linux Mint, Kali Linux    | Easy to use, large community, package manager: **APT**. |
| **Red Hat-based**    | CentOS, Fedora, Rocky Linux       | Commonly used for enterprises and servers, package manager: **YUM** or **DNF**. |
| **Arch-based**       | Arch Linux, Manjaro               | For advanced users, highly customizable. |
| **Security-focused** | Kali Linux, Parrot OS             | Designed for hacking, penetration testing, and digital forensics. |
| **Lightweight**      | Lubuntu, Puppy Linux              | Best for computers with low specifications. |

### 🔹 Recommendations for Beginners:
- **Ubuntu Desktop** → User-friendly and easy to learn.  
- **Ubuntu Server** → Great for learning networking and server management.
###

4.  **Linux has a standard file system hierarchy, which is different from Windows.**  
In Linux, everything is treated as a file — even hardware devices like hard drives and network cards.

### **Main Directory Structure**

| **Folder** | **Function** |
|------------|--------------|
| `/`        | Root directory (the top level). |
| `/home`    | Personal folder for each user. |
| `/etc`     | System configuration files. |
| `/bin`     | Core programs/commands such as `ls`, `cp`, `mv`. |
| `/var`     | Logs, cache, and variable files. |
| `/usr`     | Additional programs and libraries. |
| `/tmp`     | Temporary files. |
| `/dev`     | Devices such as hard drives (`/dev/sda`), USB, etc. |

> 💡 **Tip:** In Linux, **everything is treated as a file**, including devices like hard drives and network cards.
###

5. **Linux Access Modes**  
Linux has two main modes:
###
5.1. User Mode (non-root)  
- **Used for:** Daily activities.
- **Limitations:** Cannot modify core system files.  
- **Prompt symbol:** `$`
- Example:  
```bash
user@hostname:~$
```
5.2. Root Mode (superuser)  
- Used for: Full control of the system.  
- Privileges: Can modify or delete any files, including core system files.  
- Prompt symbol: `#`  
- Example:  
```bash
root@hostname:~#
```
###

6. **Basic Commands You Should Master**  
Essential Linux Commands to Master  
Here are the most important commands, grouped by their functions:  

6.1. File System Navigation  
Used to move around and view folders.  
|**Command**  |**Function**                         |**Example**  |
|-------------|-------------------------------------|-------------|
|`pwd`	       |Show current directory.	            |pwd|
|`ls`	        |List folder contents.	              |ls -l (detailed view)|
|`ls -a`      |Show all files including hidden (.).	|ls -a|
|`cd`	        |Change directory.	                  |cd /home|
|`cd ..`      |Go up one level.	                    |cd ..|
|`cd ~`	      |Go to user’s home directory.	        |cd ~|
|`tree`	      |Show folder structure as a tree.	    |tree /etc|

> 💡 If tree is not installed:
```bash
sudo apt install tree    # Debian/Ubuntu
sudo yum install tree    # CentOS/Red Hat
```
###

6.2. File & Folder Management  
Used to create, copy, move, or delete files and folders.  
| Command   | Function                          | Example                     |
|-----------|-----------------------------------|-----------------------------|
| `touch`   | Create an empty file.            | `touch file.txt`            |
| `mkdir`   | Create a new folder.             | `mkdir data`                |
| `mkdir -p`| Create nested folders.           | `mkdir -p project/app/logs` |
|`nano/vim` | Edit File on terminal            | `nano file.txt`              |
| `cp`      | Copy a file.                      | `cp file.txt backup.txt`    |
| `cp -r`   | Copy a folder and its contents.   | `cp -r /data /backup`       |
| `mv`      | Move or rename a file.            | `mv file.txt /home/user/`   |
| `rm`      | Delete a file.                    | `rm file.txt`               |
| `rm -r`   | Delete a folder and its contents. | `rm -r folder/`             |
| `rm -rf`  | **Force delete** without confirmation ⚠ **Dangerous!** | `rm -rf /important` |
###

6.3. Viewing & Reading Files   
Used to read file contents without editing them.   
| Command      | Function                          | Example                     |
|--------------|-----------------------------------|-----------------------------|
| `cat`        | Show file contents directly.      | `cat file.txt`              |
| `less`       | View file contents page by page.  | `less file.txt`             |
| `head`       | Show the first 10 lines.          | `head file.txt`             |
| `head -n 20` | Show the first 20 lines.          | `head -n 20 file.txt`       |
| `tail`       | Show the last 10 lines.           | `tail file.txt`             |
| `tail -f`    | Follow a log in real-time.        | `tail -f /var/log/syslog`   |
###

6.4. Searching Files & Content  
Used to search for files or text inside files.  
| Command   | Function                              | Example                     |
|-----------|---------------------------------------|-----------------------------|
| `find`    | Search for files by name/location.    | `find / -name file.txt`     |
| `locate`  | Search files using a database (faster). | `locate nginx.conf`         |
| `grep`    | Search for text inside a file.        | `grep "error" log.txt`      |
| `grep -r` | Search text in a folder recursively.  | `grep -r "password" /etc/`  |

> 💡 **If `locate` is not installed:**
 ```bash
  sudo apt install mlocate
  sudo updatedb
  ```
###

6.5. User & Group Management  
Manage users, passwords, and groups.  
| Command        | Function                     | Example                     |
|----------------|------------------------------|-----------------------------|
| `whoami`       | Show current username.       | `whoami`                    |
| `id`           | Show user and group details. | `id`                         |
| `adduser`      | Create a new user.           | `sudo adduser username`      |
| `passwd`       | Change a user’s password.    | `passwd username`            |
| `deluser`      | Delete a user.               | `sudo deluser username`      |
| `groups`       | Show groups of a user.       | `groups`                      |
| `usermod -aG`  | Add a user to a group.       | `sudo usermod -aG sudo username` |
###

6.6. Permissions & Ownership  
File permissions:  
r = `Read`  
w = `Write`  
x = `Execute`  
|**Command**|**Function**	            |**Example**|
|-----------|-------------------------|-----------|
|`ls -l`    |Show file permissions.   |	ls -l|
|`chmod`	   |Change permissions.	    |chmod 755 script.sh|
|`chown`    |Change file ownership.	  |chown root:root script.sh|
|`umask`    |Show default permissions.|	umask|  
- Example:
```bash
-rwxr-xr-x
| ||| || |
| ||| || └─ Others
| ||| └─── Group
| ||└───── Owner
| └─────── File type (-=file, d=directory)
```
###

6.7. System & Process Monitoring  
Monitor CPU, RAM, processes, and running services.  
| Command     | Function                              | Example               |
|-------------|---------------------------------------|-----------------------|
| `top`       | Show running processes in real-time.  | `top`                 |
| `htop`      | Interactive version of `top` (install first). | `htop`        |
| `ps aux`    | Show all processes.                   | `ps aux`              |
| `kill`      | Kill a process by PID.                | `kill 1234`           |
| `killall`   | Kill all processes by name.           | `killall nginx`       |
| `free -h`   | Show memory usage.                    | `free -h`             |
| `df -h`     | Show disk usage.                      | `df -h`               |
| `du -sh`    | Show folder size.                     | `du -sh /var/log`     |
| `uptime`    | Show system uptime.                   | `uptime`              |
|`shutdown`   | Shutdown system instantly             | `sudo shutdown now`   |
|`reboot`     | Reboot system instantly               | `sudo reboot`         |
> 💡 **Note:**  
- Install `htop` if it's not available:
  ```bash
  sudo apt install htop    # Debian/Ubuntu
  sudo yum install htop    # CentOS/Red Hat
  ```
- Check if any shutdown/reboot schedule avail
  ```bash
  who -r
  ```
  or message system
  ```bash
  last -x | grep shutdown
  ```
###

6.8. Networking  
Essential commands for network engineers and troubleshooting.  
| Command        | Function                          | Example                       |
|----------------|-----------------------------------|-------------------------------|
| `ip a`         | Show IP addresses and interfaces. | `ip a`                         |
| `ping`         | Test connectivity to another host.| `ping google.com`              |
| `traceroute`   | Trace the path to a host.         | `traceroute google.com`        |
| `netstat -tulnp` | Show active ports and services.  | `netstat -tulnp`               |
| `ss -tulnp`    | Modern replacement for netstat.   | `ss -tulnp`                     |
| `curl`         | Test HTTP/HTTPS connection.       | `curl http://example.com`      |
| `wget`         | Download files from the internet. | `wget http://example.com/file.zip` |
| `nslookup`     | Check DNS records.                | `nslookup google.com`           |
| `dig`          | More detailed DNS lookup.         | `dig google.com`                |  

> 💡 **Note:**  
- Install `traceroute` if it's not available:
  ```bash
  sudo apt install traceroute    # Debian/Ubuntu
  sudo yum install traceroute    # CentOS/Red Hat
  ```
###

6.9. Software Management (Package Managers)  
Different Linux distributions use different package managers.  
- Debian/Ubuntu (`apt`):  
  ```bash
  sudo apt update        # Update package list
  sudo apt upgrade       # Upgrade installed software
  sudo apt install nginx # Install software
  sudo apt remove nginx  # Remove software
  ```  
- Red Hat/CentOS (yum/dnf):  
  ```bash
  sudo yum update        # Update software
  sudo yum install nginx # Install software
  sudo yum remove nginx  # Remove software
  ```  
> 💡 Note:  
On modern Red Hat-based systems, `dnf` is the replacement for `yum.`  
- Example:  
  ```bash
  sudo dnf install nginx
  ```
###

6.10. Compression & Archiving  
Used to compress or extract files.  
| Command       | Function                         | Example                       |
|---------------|----------------------------------|-------------------------------|
| `tar -cvf`    | Create a tar archive.           | `tar -cvf backup.tar folder/` |
| `tar -xvf`    | Extract a tar archive.          | `tar -xvf backup.tar`         |
| `tar -czvf`   | Create a compressed tar.gz archive. | `tar -czvf backup.tar.gz folder/` |
| `tar -xzvf`   | Extract a tar.gz archive.       | `tar -xzvf backup.tar.gz`     |
| `zip`         | Create a zip file.              | `zip backup.zip file.txt`     |
| `unzip`       | Extract a zip file.             | `unzip backup.zip`            |  
> 💡 **Pro Tips:**  
- `tar` is commonly used for Linux backups and packaging multiple files.  
- Add `-v` (verbose) to see which files are being processed.
- For zip with multiple files:  
  ```bash
  zip backup.zip file1.txt file2.txt file3.txt
  ```
###

6.11. System Information  
Check hardware and OS details.  
| Command     | Function                              | Example          |
|-------------|---------------------------------------|------------------|
| `uname -a`  | Show Linux kernel info.               | `uname -a`       |
| `hostname`  | Show device hostname.                 | `hostname`       |
| `uptime`    | Show how long the system has been running. | `uptime`     |
| `lsblk`     | List storage devices.                 | `lsblk`          |
| `df -h`     | Show disk usage.                      | `df -h`          |
| `du -sh`    | Show folder size.                     | `du -sh /home`   |  
> 💡 **Pro Tips:**  
- Use `lsblk -f` to view filesystems and mount points.
- Combine `df -h` and `du -sh` to monitor storage health.
- To view CPU details:
  ```bash
  lscpu
  ```
- To check memory details:
  ```bash
  free -h
  ```
###

6.12. Help & Documentation  
Every command has built-in help.  
| Command         | Function                              | Example       |
|-----------------|---------------------------------------|---------------|
| `man <command>` | Open manual page for a command.       | `man ls`      |
| `<command> --help` | Show quick help.                   | `ls --help`   |
| `whatis`        | Show a short description of a command.| `whatis ls`   |
| `apropos`       | Search for commands by keyword.       | `apropos network` |  
> 💡 **Tips:**
- Use the **`man`** command to read detailed documentation. Press:
  - `Space` → Next page  
  - `q` → Quit manual  
- Example:
  ```bash
  man grep
  ```
###

6.13. Useful Terminal Shortcuts  
| Shortcut    | Function                        |
|-------------|---------------------------------|
| `Ctrl + C`  | Cancel a running command.       |
| `Ctrl + D`  | Log out / exit shell.           |
| `Ctrl + L`  | Clear the screen (`clear`).     |
| `↑ / ↓`     | Navigate through command history.|
| `Tab`       | Auto-complete filenames/folders.|  
> 💡 **Tips:**
- Press `Tab` twice to see **all available commands** or file suggestions.
- Combine `Ctrl + L` with `clear` to refresh your workspace for better visibility.
- If you accidentally freeze your terminal, try:
  ```bash
  Ctrl + Q
  ```
###

7. Tips for Learning Linux  
- Use a Virtual Machine like VirtualBox to practice safely without risking your main system.
- Recommended beginner-friendly distros: Ubuntu Server or Debian.
- Get used to working through the terminal instead of relying on the GUI.  
Always read command documentation using:  
 ``` bash
 man <command>
 ```  
Example:  
 ```bash
 man ls
 ```
