---
{"dg-publish":true,"permalink":"/cybersecurity/module-1-and-2/day-6-wednesday/","created":"2025-02-13T16:10:10.714+05:30","updated":"2025-02-20T20:47:14.317+05:30"}
---

# **Networking and Firewalls**

---
## **IPv4 Addressing**

IPv4 (Internet Protocol version 4) is a numerical label assigned to devices connected to a network for identification and communication. It uses a 32-bit address, written in dotted decimal notation (e.g., `192.168.1.1`).

### **IP Address Classes:**

|Class|Starting IP|Ending IP|Default Subnet Mask|Purpose|
|---|---|---|---|---|
|A|1.0.0.0|126.255.255.255|255.0.0.0|Large Networks|
|B|128.0.0.0|191.255.255.255|255.255.0.0|Medium Networks|
|C|192.0.0.0|223.255.255.255|255.255.255.0|Small Networks|
|D|224.0.0.0|239.255.255.255|-|Multicasting|
|E|240.0.0.0|255.255.255.255|-|Research & Reserved|

## **Netmask & Subnet Mask**

- **Netmask:** A 32-bit mask used to divide an IP address into network and host portions.
    
- **Subnet Mask:** A special netmask that helps in defining subnets within a network. Example: `255.255.255.0` indicates that the first 3 octets define the network, and the last octet defines the host.
    

## **Gateway**

A gateway is a device (typically a router or firewall) that connects different networks, allowing communication between them. In an industry setting, a gateway can be a router or the IP of a firewall.

## **CIDR (Classless Inter-Domain Routing) Range**

CIDR notation is a method for allocating IP addresses and routing.

- Format: `IP address / Subnet Bits`
    
- Example: `192.168.1.0/24` (24 bits for the network, 8 bits for hosts).
    

## **Network ID & Broadcast ID**

- **Network ID:** The first address in the subnet (e.g., `192.168.20.0/21`).
    
- **Broadcast ID:** The last address in the subnet (e.g., `192.168.20.255`).
    
- **Network Range:** The range of usable IPs (e.g., `192.168.20.1 - 192.168.20.254`).
    
- **Total IPs Possible:** `2^Host Bits - 2` (subtracting network and broadcast addresses).
    

### **Example Calculation:**

- Given: `192.168.20.15`, Netmask: `255.255.255.0`
    
- **Network ID:** `192.168.20.0/21`
    
- **Broadcast ID:** `192.168.20.255`
    
- **Network Range:** `192.168.20.1 - 192.168.20.254`
    
- **Total Number of IPs:** `2^(32 - subnet bits) - 2`
    
- **Host Bits:** `32 - 24 = 8`
    

## **Firewall & Windows Defender Firewall**

A firewall is a security system that monitors and controls incoming/outgoing traffic based on security rules.

- **Explicitly Allow:** Grants access to specific rules.
    
- **Explicitly Deny:** Blocks access regardless of other rules.
    
- **Deny All:** Blocks all traffic unless explicitly allowed.
    
- **Whitelist:** A strict policy where only explicitly allowed traffic is permitted.
    
- **First IP Used as Gateway:** The first usable IP in a subnet is typically reserved for the gateway.
    
- **Only IP for External Access:** The gateway is the only IP allowing outbound traffic.
    

## **Network Devices: Switch**

A network switch connects devices within a LAN (Local Area Network) and directs data packets only to the intended device.

## **Linux Networking & Package Management Commands**

|   |   |
|---|---|
|Command|Description|
|`sudo`|Execute command as root|
|`apt search apache2`|Search for Apache package|
|`sudo -s`|Open a root shell|
|`whoami`|Display current user|
|`sudo whoami`|Check if sudo grants root access|
|`sudo apt update`|Update package lists|
|`sudo apt install apache2`|Install Apache web server|
|`systemctl status apache2`|Check Apache status|
|`sudo systemctl start apache2`|Start Apache service|
|`apt purge <package>`|Completely remove a package|
|`apt remove <package>`|Remove a package but keep config files|
|`sudo apt install members`|Install the 'members' package|
|`members sudo`|List users in the sudo group|
|`sudo systemctl enable apache2`|Enable Apache to start at boot|

### **APT (Advanced Package Tool)**

APT is the package manager for Debian-based Linux distributions like Ubuntu, used to install, update, and remove software.

### **Debian-Based Linux**

Debian-based Linux distributions are operating systems built on the Debian Linux framework. They use the `APT` package manager and follow Debian’s software repository structure. Examples include:

- **Ubuntu**
    
- **Kali Linux**
    
- **Linux Mint**
    
- **Parrot OS** These distributions are known for their stability, extensive software support, and strong community backing.
    

## **Communication in the Same Network**

Devices within the same subnet can communicate without a router. If they are in different subnets, they need a gateway.

## **Linux Commands Explained**

### **1. `sudo apt update`**

- This command updates the package lists for APT (Advanced Package Tool) to ensure you get the latest available versions of software and security patches.
- It does not upgrade or install any new packages but refreshes the package repository metadata.
- **Example Output:**
     `Get:1 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB] Reading package lists... Done`
    

---

### **2. `sudo apt install apache2`**

- Installs the Apache2 web server package on a Debian-based Linux system.
- The `sudo` command ensures that the installation runs with administrative privileges.
- **Example Usage:**
    `sudo apt install apache2`
    
- During installation, it may prompt for confirmation (`Y/n`).

---

### **3. `systemctl status apache2`**

- Checks the status of the Apache2 service.
- It provides information on whether the service is **active (running)**, **inactive**, or **failed**.
- **Example Output:**
    `apache2.service - The Apache HTTP Server    Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)    Active: active (running) since Mon 2024-02-20 12:34:56 UTC; 5min ago`
    

---

### **4. `sudo systemctl start apache2`**

- Starts the Apache2 web server service.
- If Apache is installed but not running, this command ensures it is up and running.
- **Example Usage:**
    `sudo systemctl start apache2`
    

---

### **5. `apt search apache2`**

- Searches the available package repositories for Apache2 and related packages.
- Helps find package names and descriptions before installation.
- **Example Output:**
    `apache2/focal-updates,focal-security 2.4.41-4ubuntu3.9 amd64     Apache HTTP Server`
    

---

### **6. `sudo -s`**

- Opens a root shell, giving full administrative access.
- Equivalent to switching to the root user (`su`) but uses `sudo`.
- **Example Usage:**
    `sudo -s root@hostname:/home/user#`
    

---

### **7. `whoami`**

- Displays the current logged-in username.
- **Example Output:**
    `user1`
    

---

### **8. `sudo whoami`**

- Runs `whoami` with root privileges, returning `root` if executed successfully.
- **Example Output:**
    `root`
    

---

### **9. `rm filename`**

- Deletes the specified file.
- **Example Usage:**
    `rm myfile.txt`
    
- **Warning:** There is no undo option; deleted files cannot be recovered easily.
- To force deletion without confirmation:
    `rm -f filename`
    
- To remove a directory and all its contents:
    `rm -r directory_name`


### *Note:*
- apt : package manager
- systemctl : service manager
- enable : service is there in the system startup

## Difference Between `enable` and `start`


| `systemctl start apache2` | Starts the Apache2 service immediately but does not enable it on boot. |
| ------------------------- | ---------------------------------------------------------------------- |

| `systemctl enable apache2` | Ensures Apache2 starts automatically on every system boot. |
| -------------------------- | ---------------------------------------------------------- |

| `systemctl enable --now apache2` | Enables and starts Apache2 immediately. |
| -------------------------------- | --------------------------------------- |


---
## *Homework:

- Study **IPv4 and Ethernet**
    
- Review the **OSI Model**