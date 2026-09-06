# README.md
linux-filesystem-and-commands
# 🐧 Linux File System &  Commands

A beginner-friendly guide to understanding the Linux directory structure and essential command-line utility tools.

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
