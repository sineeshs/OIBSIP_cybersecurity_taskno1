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
```
**Options used:**

-sV: Enables service version detection.

-T4: Sets the timing template to "Aggressive" for a faster scan. Nmap offers six timing templates (T0 to T5), where T0 is the slowest (stealthiest) and T5 is the fastest.

### 2. Operating System (OS) Detection
This scan attempts to guess the operating system running on the target machine based on network fingerprints. Note that OS detection requires root privileges.

```Bash
sudo nmap -O 10.0.2.6
Options used:
```
-O: Enables OS detection.

### 3. Exporting Scan Results
You can save the output of your Nmap scans for later review or to feed into other tools. The following command runs a scan and saves the results in three common formats (XML, normal Nmap output, and grepable format).

```Bash
nmap -sV -T4 -oA nmap_scan_results 10.0.2.6
Options used:
```
-oA <basename>: Outputs the results in the three major formats simultaneously, using the provided <basename> for the files.

After the scan completes, you can list the files to see the output:

```Bash
ls
```
You should see files like nmap_scan_results.nmap, nmap_scan_results.gnmap, and nmap_scan_results.xml. You can view the contents of the XML file, for example, using:

```Bash
cat nmap_scan_results.xml
