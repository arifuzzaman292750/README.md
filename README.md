# README.md
linux-filesystem-and-commands
# 🐧 Linux File System &  Commands

A beginner-friendly guide to understanding the Linux directory structure and essential command-line utility tools.

---

## 📖 What you will learn

- 🐧 Linux File System
- 💻 Basic Linux Commands
- 📁 File & Directory Management
- 🔍 Searching & File Reading
- 🔐 Basic Security Commands
- 🧪 Practical Command Examples

---

## 📂 Linux Directory Structure

In Linux, everything starts from the root directory (`/`). Here is the standard directory tree structure:

```text
/ [root]
├── sbin/ [System binaries for admin]
├── usr/ [User programs & data]
│   ├── bin/ [User commands: cp, ls, sh, tar, vi, man]
│   ├── contrib/ [Contributed software]
│   ├── lib/ [Libraries]
│   ├── local/ [Locally installed software]
│   ├── sbin/ [Admin tools]
│   ├── share/
│   │   └── man/ [Manual pages]
│   └── vue/ [Old BSD folder, rarely used now]
├── dev/ [Device files]
├── etc/ [System configs]
│   ├── group [User groups file]
│   ├── passwd [User accounts file]
│   └── profile [Default shell settings]
├── opt/ [Optional 3rd party software]
├── var/ [Variable data/logs]
│   ├── mail/
│   ├── news/
│   ├── tmp/
│   └── vue/
├── stand/ [Standalone programs]
│   └── vmunix [Kernel file - old Unix name]
├── tmp/ [Temporary files]
└── home/ [User home folders]
    ├── user1/
    ├── user2/
    └── user3/


## ⌨️ Terminal Shortcuts

| Shortcut | Action |
| :--- | :--- |
| <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd> | Open a terminal |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>R</kbd> | Open another terminal horizontally |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>D</kbd> | Open another terminal vertically |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>+</kbd> | Zoom in terminal font |
| <kbd>Ctrl</kbd> + <kbd>-</kbd> | Zoom out terminal font |

---

## 🛠️ Frequently Used Commands

| Command | Description |
| :--- | :--- |
| `pwd` | Print working directory |
| `cd` | Change directory |
| `ls` | List files and directories |
| `mkdir` | Create a new directory |
| `rmdir` | Remove an empty directory |
| `rm` | Remove files and directories |
| `cp` | Copy files or directories |
| `mv` | Move or rename files/directories |
| `cat` | Display file content |
| `less` | View file content page by page |
| `head` | Show first 10 lines of a file |
| `tail` | Show last 10 lines of a file |
| `touch` | Create an empty file or update timestamp |
| `nano` | Edit file in nano editor |
| `chmod` | Change file permissions |
| `chown` | Change file owner and group |
| `ps` | Show running processes |
| `top` | Real-time process monitor |
| `df` | Show disk spaces usage |
| `du` | Show directory size |
| `man` | Show manual of a command |
| `grep` | Search text in a file |
| `find` | Find files by name |
| `tar` | Create or extract a tar archive |
| `unzip` | Extract a zip file |
| `zip` | Create a zip archive |
| `ping` | Check connectivity to a host |
| `ip` | Show IP address and network info |
| `clear` | Clear terminal screen |
| `history` | Show command history |

---

## 📁 File and Directory Commands

```bash
# Create files
touch test.txt                  # Create an empty file
nano test.txt                   # Create/edit file in CLI editor
mousepad test.txt               # Create/edit file in GUI editor

# File operations
cat test.txt                    # Read a file content
cp test.txt test                # Copy a file to a directory
mv test.txt test                # Move (cut) a file to a directory
mv test.txt move.txt            # Rename a file
rm test.txt                     # Delete a file

# Directory operations
mkdir test                      # Create a folder/directory
rm -rf test                     # Delete a folder recursively
mv test move                    # Move a folder into another folder
cp -r test copy                 # Copy a folder to another folder

# Search files ignoring error messages
find / -name "test.txt" 2>/dev/null

# Search all .txt files in the Desktop directory
find ~/Desktop -name "*.txt" 2>/dev/null

# Search all .txt files across the entire file system
find / -name "*.txt" 2>/dev/null

# Search for specific text inside a file
grep "whoami" commands.txt

# System & User Management
passwd kali                     # Change password for user 'kali'
whoami                          # Display current user
id                              # Display user ID and group details

# Network & Ports
ping google.com                 # Check network connectivity
ip a                            # Show IP address (or 'ifconfig')
netstat -tuln                   # Show active listening open ports
ss -tuln                        # Show open ports (modern alternative)

# Permissions & Execution
chmod +x zphisher.sh            # Grant executable permission to script
ls -la                          # List files with permissions & hidden files
./zphisher.sh                   # Run the executable script

# Software & Repositories
git clone [https://test.com](https://test.com)      # Clone a Git repository
sudo dpkg -i ./softname.deb     # Install a .deb software package

# Directory Exploration & Archiving
cd /usr/bin                     # Navigate to directory with system binaries
tree -L 2                       # Display directory tree structure up to 2 levels deep
unzip file.zip                  # Extract a .zip archive
tar -cvf file.tar <dir>         # Create a .tar archive
tar -xvf file.tar               # Extract a .tar archive
tar -czvf file.tar.gz <dir>     # Create a compressed .tar.gz archive
tar -xzvf file.tar.gz           # Extract a compressed .tar.gz archive

---

## 🎯 Important Linux Directories & Files for Ethical Hacking

| Directory / File | Why it matters for Hacking & Privilege Escalation |
| :--- | :--- |
| `/etc/passwd` | List of all system users. Shows existing user accounts. |
| `/etc/shadow` | Hashed user passwords (root access required). Prime target for password cracking. |
| `/etc/group` | User groups and group permissions. |
| `/home/username/` | User personal files, SSH keys, and `.bash_history` (sensitive info exposure). |
| `/root/` | Root user home directory; often contains scripts, notes, and admin credentials. |
| `/var/log/auth.log` | Records all login attempts (SSH, sudo, failed logins). Used to track brute force attacks. |
| `/etc/ssh/sshd_config` | SSH server configuration (port changes, root login settings). |
| `/etc/crontab` & `/var/spool/cron/` | Scheduled cron jobs. Prime target for privilege escalation and persistence/backdoors. |
| `/etc/hosts` | Local DNS overrides. Used for network redirection and local phishing tests. |
| `/etc/fstab` | Mounted filesystems at boot time. Can reveal hidden or unmounted drives. |
| `/etc/sudoers` | Defines `sudo` privileges. Major privilege escalation target. |
| `/proc/` | Virtual filesystem containing live process & kernel info (e.g., `/proc/net/tcp`, `/proc/version`). |
| `/sys/` | Exposes kernel and hardware device details. |
| `/bin`, `/usr/bin`, `/sbin` | Standard binary locations. Useful for checking SUID binaries and trojaned commands. |
| `/var/log/` | System log directory (`syslog`, `apache2/`, `kern.log`). Used to analyze vulnerabilities or cover tracks. |
| `/var/www/html/` | Default web root folder. Target location for uploading webshells. |
| `/srv/` | Data folder for site-specific services served by the system. |
| `/opt/` | Third-party applications (e.g., Metasploit, Burp Suite). Often contains custom/misconfigured software. |
| `/tmp/` | World-writable directory. Ideal location to drop payloads and local exploits. |
| `/dev/` | Device files. Direct raw disk access or memory inspection targets. |
| `/boot/` | Kernel images and GRUB configs. Target location for rootkits/bootkits. |
| `/usr/local/bin/` | Preferred path for dropping custom scripts, administrative tools, or backdoors. |
