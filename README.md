# Nmap Installation and Basic Usage Guide

This guide provides instructions on how to install and perform basic network scanning using **Nmap** (Network Mapper) on Kali Linux. Nmap is an open-source tool widely used by cybersecurity professionals for network discovery and security auditing.

## Prerequisites
- A Debian-based Linux distribution (like Kali Linux).
- Terminal access.
- `sudo` privileges for installation and certain scan types.

---

## Installation

1.  **Update the package list:**
    Before installing new software, it's good practice to update your package list.
    ```bash
    sudo apt update
    ```

2.  **Install Nmap:**
    Install Nmap using the `apt` package manager. The `-y` flag automatically answers yes to prompts.
    ```bash
    sudo apt install nmap -y
    ```

3.  **Verify the installation:**
    Check that Nmap was installed successfully by viewing its version.
    ```bash
    nmap --version
    ```

---

## Usage Examples

In the examples below, the target IP address is `10.0.2.6` (a locally hosted Metasploitable vulnerable virtual machine). Replace this with the IP address or hostname of your authorized target.

### 1. Basic Service and Version Scan
This scan checks for open ports and attempts to determine the version of the services running on them.
```bash
nmap -sV -T4 10.0.2.6

