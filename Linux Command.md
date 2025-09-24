# Linux-Base-Knowledge
How To know about Linux

1. What Linux is?
###
Linux is an `operating system` (OS) built on the `Linux kernel.` It is `open-source` and free to use.
---

2. Where can Linux be used?

- Servers (web servers, database servers, etc.) → Examples: Ubuntu Server, CentOS, Debian.
- Desktop computers → Examples: Ubuntu Desktop, Linux Mint, Fedora.
- Embedded devices → Examples: routers, IoT devices, Android.
- Supercomputers & Cloud → Most cloud platforms like AWS, Google Cloud, and Azure run on Linux.
---

3. **Linux has many variants called distributions (distros).**  
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
---

4. **Linux has a standard file system hierarchy, which is different from Windows.**  
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
---
