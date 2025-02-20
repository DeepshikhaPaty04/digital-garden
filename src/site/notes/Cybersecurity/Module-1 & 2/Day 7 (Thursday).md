---
{"dg-publish":true,"permalink":"/cybersecurity/module-1-and-2/day-7-thursday/","created":"2025-02-13T16:17:03.592+05:30","updated":"2025-02-20T22:20:02.656+05:30"}
---

# **Linux Filesystem Hierarchy & Networking Concepts**

## **Filesystem Hierarchy Standard (FHS)**

[Reference link](https://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html)

The **Filesystem Hierarchy Standard (FHS)** defines the directory structure and directory contents in Linux operating systems. Some key directories include:


---

## **File System Hierarchy (FHS)**

- `**/etc**` **directory:** Configuration files.
    
- `**/home**` **directory:** User home directories.
    
- `**/root**` **directory:** Superuser's home.
    
- `**/tmp**` **directory:** Temporary files.
    
- `**/media**` **directory:** Auto-mounted removable media.
    
- `**/mnt**` **directory:** Temporary mount points.
    

---

## **Linux Commands & Package Management**

### **APT (Advanced Package Tool) - Debian Package Manager**

- `sudo apt update` → Updates package lists.
    
- `sudo apt install apache2` → Installs Apache.
    
- `sudo apt purge apache2` → Completely removes a package.
    
- `apt search apache2` → Searches for Apache in repositories.
    
- `sudo apt remove apache2` → Uninstalls Apache but keeps config files.
    

### **Systemctl (Service Management)**

- `systemctl status apache2` → Checks Apache status.
    
- `sudo systemctl start apache2` → Starts Apache service.
    
- `sudo systemctl stop apache2` → Stops Apache service.
    
- `sudo systemctl restart apache2` → Restarts Apache service.
    
- `sudo systemctl enable apache2` → Enables Apache at boot.
    
- `sudo systemctl disable apache2` → Disables Apache at boot.
    

---

## **Essential Linux Commands**

### **Navigation & File Management**

- `clear` → Clears the terminal screen.
    
- `whoami` → Shows current user.
    
- `whatis whoami` → Provides a brief description of `whoami`.
    
- `man whoami` → Displays manual page (`q` to quit).
    
- `pwd` → Prints the current directory.
    
- `ls` → Lists files and directories.
    
- `ls -a` → Shows hidden files.
    
- `ls -l` → Displays file details.
    
- `ls -la` → Detailed listing including hidden files.
    
- `history` → Shows command history.
    
- `cd /home/star/world/asia/india` → Absolute path navigation.
    
- `cd asia/india/odisha` → Relative path navigation.
    
- `cp mysdi.txt ../pinky/new_file.txt` → Copies a file.
    
- `rm pinky/mysdi.txt` → Deletes a file.
    
- `mv pinky.txt new_pinky.txt` → Renames a file.
    
- `which nano` → Finds the location of `nano`.
    

### **Editing & Viewing Files**

- `nano filename` → Opens a file in Nano editor.
    
- `cat filename` → Displays file contents.
    
- `tac filename` → Displays file contents in reverse.
    
- `grep 'pattern' filename` → Searches for a pattern in a file.
    
- `echo "Hello"` → Prints text.
    

### **Checksums & Networking**

- `sha256sum filename` → Computes SHA-256 hash.
    
- `sha1sum filename` → Computes SHA-1 hash.
    
- `md5sum filename` → Computes MD5 hash.
    
- `hostname` → Displays system hostname.
    
- `ifconfig` or `ip a` → Shows network interfaces.
    
- `ping -c 1 10.0.2.15` → Sends a ping request.
    

---

## **Wireshark & Network Analysis**

- **Wireshark:** A packet analyzer tool for capturing network traffic.
    
- **Display Filters:** Used to filter captured network packets.
    
- **Sniffing Attack:** Intercepting and logging network traffic.
    

### **Ethernet & IPv4**

- **Ethernet:** Most common wired network technology (IEEE 802.3 standard).
    
- **Ethernet Frame:** Data encapsulation unit in Ethernet networks.
    
- **IPv4 Header:** Contains source/destination IP, checksum, etc.
    
- **Loopback Adapter:** Used for self-communication (e.g., `127.0.0.1`).
    

### **Paths in Linux**

- **Absolute Path:** Starts from `/` (root directory).
    
- **Relative Path:** Starts from the current directory.
    
- **Root Directory:** The topmost directory (`/`).
    

---

## **Additional Topics**

- **Shells:** Bash (default in most Linux), Zsh (Kali Linux), sh, K-Shell.
    
- **Snapshot & Rollback:** Used in cloud security (e.g., CloudSEK ASM).
    

### **References:**

- [IPv4 - Wikipedia](https://en.wikipedia.org/wiki/IPv4)
    
- [IPv4 Header - JavaPoint](https://www.javatpoint.com/ipv4-header-in-computer-networks)