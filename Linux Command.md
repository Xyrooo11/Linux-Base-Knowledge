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
A. User Mode (non-root)**  
- **Used for:** Daily activities.
- **Limitations:** Cannot modify core system files.  
- **Prompt symbol:** `$`
Example:
```bash
user@hostname:~$
```
B. Root Mode (superuser)  
- Used for: Full control of the system.  
- Privileges: Can modify or delete any files, including core system files.  
- Prompt symbol: `#`  
Example:
```bash
root@hostname:~#
```
###

6. **Basic Commands You Should Master**  
Essential Linux Commands to Master  
Here are the most important commands, grouped by their functions:  

A. File System Navigation  
Used to move around and view folders.  
|**Command**  |**Function**                         |**Example**  |
|-------------|-------------------------------------|-------------|
|pwd	        |Show current directory.	            |pwd|
|ls	          |List folder contents.	              |ls -l (detailed view)|
|ls -a        |Show all files including hidden (.).	|ls -a|
|cd	          |Change directory.	                  |cd /home|
|cd ..	      |Go up one level.	                    |cd ..|
|cd ~	        |Go to user’s home directory.	        |cd ~|
|tree	        |Show folder structure as a tree.	    |tree /etc|

> 💡 If tree is not installed:
```bash
sudo apt install tree    # Debian/Ubuntu
sudo yum install tree    # CentOS/Red Hat
```
###

B. File & Folder Management  
Used to create, copy, move, or delete files and folders.  
| Command   | Function                          | Example                     |
|-----------|-----------------------------------|-----------------------------|
| `touch`   | Create an empty file.            | `touch file.txt`            |
| `mkdir`   | Create a new folder.             | `mkdir data`                |
| `mkdir -p`| Create nested folders.           | `mkdir -p project/app/logs` |
| `cp`      | Copy a file.                      | `cp file.txt backup.txt`    |
| `cp -r`   | Copy a folder and its contents.   | `cp -r /data /backup`       |
| `mv`      | Move or rename a file.            | `mv file.txt /home/user/`   |
| `rm`      | Delete a file.                    | `rm file.txt`               |
| `rm -r`   | Delete a folder and its contents. | `rm -r folder/`             |
| `rm -rf`  | **Force delete** without confirmation ⚠ **Dangerous!** | `rm -rf /important` |
###

C. Viewing & Reading Files   
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

D. ## Searching Files & Content  
Used to search for files or text inside files.  
| Command   | Function                              | Example                     |
|-----------|---------------------------------------|-----------------------------|
| `find`    | Search for files by name/location.    | `find / -name file.txt`     |
| `locate`  | Search files using a database (faster). | `locate nginx.conf`         |
| `grep`    | Search for text inside a file.        | `grep "error" log.txt`      |
| `grep -r` | Search text in a folder recursively.  | `grep -r "password" /etc/`  |

>💡 **If `locate` is not installed:**
```bash
sudo apt install mlocate
sudo updatedb
```
###

E. User & Group Management  
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

F. Permissions & Ownership  
File permissions:  
r = `Read`  
w = `Write`  
x = `Execute`  
|**Command**|**Function**	            |**Example**|
|-----------|-------------------------|-----------|
|ls -l	    |Show file permissions.   |	ls -l|
|chmod	    |Change permissions.	    |chmod 755 script.sh|
|chown	    |Change file ownership.	  |chown root:root script.sh|
|umask	    |Show default permissions.|	umask|
Example:  
```bash
-rwxr-xr-x
| ||| || |
| ||| || └─ Others
| ||| └─── Group
| ||└───── Owner
| └─────── File type (-=file, d=directory)
```
###

G. System & Process Monitoring  
Monitor CPU, RAM, processes, and running services.  
| Command     | Function                              | Example               |
|-------------|---------------------------------------|-----------------------|
| `top`       | Show running processes in real-time.  | `top`                 |
| `htop`      | Interactive version of `top` (install first). | `htop`        |
| `ps aux`    | Show all processes.                   | `ps aux`              |
| `kill`      | Kill a process by PID.                | `kill 1234`           |
| `killall`   | Kill all processes by name.           | `killall nginx`       |
| `free -h`   | Show memory usage.                     | `free -h`             |
| `df -h`     | Show disk usage.                       | `df -h`               |
| `du -sh`    | Show folder size.                      | `du -sh /var/log`     |
| `uptime`    | Show system uptime.                    | `uptime`              |

>💡 **Note:**  
- Install `htop` if it's not available:
  ```bash
  sudo apt install htop    # Debian/Ubuntu
  sudo yum install htop    # CentOS/Red Hat
  ```
###

8. Networking
Command	Function	Example
ip a	Show IP addresses and interfaces.	ip a
ping	Check connectivity.	ping google.com
traceroute	Trace route to a host.	traceroute google.com
netstat -tulnp	Show active ports/services.	netstat -tulnp
ss -tulnp	Modern version of netstat.	ss -tulnp
curl	Test HTTP/HTTPS requests.	curl http://example.com
wget	Download files.	wget http://example.com/file.zip
nslookup	Check DNS records.	nslookup google.com
dig	Detailed DNS lookup.	dig google.com
9. Software Management (Package Manager)

Debian/Ubuntu (APT):

sudo apt update
sudo apt upgrade
sudo apt install nginx
sudo apt remove nginx


Red Hat/CentOS (YUM/DNF):

sudo yum update
sudo yum install nginx
sudo yum remove nginx

10. Compression & Archiving
Command	Function	Example
tar -cvf	Create tar archive.	tar -cvf backup.tar folder/
tar -xvf	Extract tar archive.	tar -xvf backup.tar
tar -czvf	Create compressed tar.gz file.	tar -czvf backup.tar.gz folder/
tar -xzvf	Extract tar.gz file.	tar -xzvf backup.tar.gz
zip	Create zip file.	zip backup.zip file.txt
unzip	Extract zip file.	unzip backup.zip
11. System Information
Command	Function	Example
uname -a	Show Linux kernel info.	uname -a
hostname	Show device hostname.	hostname
uptime	Show uptime.	uptime
lsblk	List storage devices.	lsblk
df -h	Show disk usage.	df -h
du -sh	Show folder size.	du -sh /home
12. Help & Documentation
Command	Function	Example
man <command>	Manual page for a command.	man ls
<command> --help	Quick help.	ls --help
whatis	Short description of command.	whatis ls
apropos	Search commands by keyword.	apropos network
13. Useful Terminal Shortcuts
Shortcut	Function
Ctrl + C	Cancel running command.
Ctrl + D	Exit terminal or shell.
Ctrl + L	Clear screen (same as clear).
↑ / ↓	Scroll through command history.
Tab	Auto-complete file/folder names.
