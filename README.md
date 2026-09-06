# README.md
linux-filesystem-and-commands
# 🐧 Linux File System &  Commands

A beginner-friendly guide to understanding the Linux directory structure and essential command-line utility tools.

---

## 📂 Linux Directory Structure

In Linux, everything starts from the root directory (`/`). Here are the key directories and their purpose:

| Directory | Purpose |
| :--- | :--- |

|/ [root]|
|├── sbin/ [System binaries for admin]|
|├── usr/ [User programs & data]|
│ ├── bin/ [User commands: cp, ls, sh, tar, vi, man]
│ ├── contrib/ [Contributed software]
│ ├── lib/ [Libraries]
│ ├── local/ [Locally installed software]
│ ├── sbin/ [Admin tools]
│ ├── share/
│ │ └── man/ [Manual pages]
│ └── vue/ [Old BSD folder, rarely used now]
├── dev/ [Device files]
├── etc/ [System configs]
│ ├── group [User groups file]
│ ├── passwd [User accounts file]
│ └── profile [Default shell settings]
├── opt/ [Optional 3rd party software]
├── var/ [Variable data/logs]
│ ├── mail/
│ ├── news/
│ ├── tmp/
│ └── vue/
├── stand/ [Standalone programs]
│ └── vmunix [Kernel file - old Unix name]
├── tmp/ [Temporary files]
└── home/ [User home folders]
    ├── user1/
    ├── user2/
    └── user3/

# 🐧 Linux Commands & File System Cheat Sheet

A beginner-friendly guide to understanding the Linux directory structure and essential command-line utility tools.

---

## 📂 Linux Directory Structure

In Linux, everything starts from the root directory (`/`). Here are the key directories and their purpose:

| Directory | Purpose |
| :--- | :--- |
| `/` | **Root:** The top-level directory of the entire file system. |
| `/bin` | **Essential User Binaries:** Basic commands needed for system boot (e.g., `ls`, `cp`, `cd`). |
| `/etc` | **Configuration Files:** System-wide settings and program configuration files. |
| `/home` | **User Home Directories:** Personal storage for users (e.g., `/home/username/`). |
| `/var` | **Variable Data:** Files that frequently change, such as system logs (`/var/log`) and database files. |
| `/usr` | **User Programs:** Secondary hierarchy for read-only user data, utilities, and applications. |
| `/tmp` | **Temporary Files:** Location where applications store temporary session files (usually cleared on reboot). |
| `/dev` | **Device Files:** Hardware devices represented as files (e.g., storage drives, terminal devices). |

---

## 🛠️ Essential Linux Commands

### 1. Navigating the File System
* **`pwd`** — Print Working Directory (shows your current location).
  ```bash
  pwd
