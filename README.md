# Week 02 – Footprinting, Reconnaissance & Network Scanning

**Cybersecurity Internship | Networkwalks**

This repository contains the practical work I completed during Week 02 of my Cybersecurity Internship at Networkwalks.

This week's activities covered two practical modules:

- **W2-PM1:** Footprinting and Reconnaissance using Kali Linux tools.
- **W2-PM5:** Network Scanning and Network Discovery using Zenmap.

The practicals helped me understand how to collect domain information, identify website technologies, check DNS records, discover active devices on a network and visualise network topology.

## Objectives

The main objectives of Week 2 were:

- To understand the basics of footprinting and reconnaissance.
- To gather publicly available information about a target domain.
- To identify website technologies using Kali Linux tools.
- To understand DNS lookup and enumeration.
- To check for Web Application Firewalls.
- To perform network discovery using Zenmap.
- To identify active hosts and understand network topology.

## Lab Environment

| Parameter | Details |
|---|---|
| Operating System | Kali Linux and Windows |
| Network Scanning Tool | Zenmap / Nmap |
| Nmap Version | 7.993 |
| Footprinting Tools | WHOIS, WhatWeb, Nslookup, cURL, Wafw00f and DNSenum |
| Target Domain | networkwalks.com |
| Network Interface | Wi-Fi |
| Local IP Address | 192.168.2.110 |
| Default Gateway | 192.168.2.14 |
| Network Subnet | 192.168.2.0/24 |

## Authorization and Scope

These activities were performed for educational purposes as part of my cybersecurity internship.

The footprinting activity focused on the assigned training domain, networkwalks.com. Network scanning was performed on my local Wi-Fi network within the authorised scope.

No exploitation or unauthorised access was performed.

---

# Practical 1 – Footprinting and Reconnaissance (W2-PM1)

## Objective

The objective of this practical was to collect publicly available information about a target domain using six different tools available in Kali Linux.

## Tools Used

1. WHOIS
2. WhatWeb
3. Nslookup
4. cURL
5. Wafw00f
6. DNSenum

### 1. WHOIS – Domain Information Gathering

WHOIS is used to collect publicly available domain registration information.

**Command Used:**

```bash
whois networkwalks.com
```

**Observations:**

- Domain registration information can be collected.
- Registrar details can be checked.
- Nameserver information can be identified.
- Domain creation and expiry details may be available.

**Security Significance:**

WHOIS helps security professionals understand domain registration details and gather information during the reconnaissance stage.

### 2. WhatWeb – Website Technology Identification

WhatWeb is used to identify the technologies and software used by a website.

**Command Used:**

```bash
whatweb https://networkwalks.com
```

**Observations:**

The tool was used to check the technologies and server information associated with the target website. The actual detected results are documented in the corresponding screenshot.

**Security Significance:**

WhatWeb helps identify the technologies used by a website and understand its publicly visible technical information.

### 3. Nslookup – DNS Lookup

Nslookup is used to resolve a domain name and find its associated IP address.

**Command Used:**

```bash
nslookup networkwalks.com
```

**Observations:**

- DNS server information can be identified.
- The IP address associated with the domain can be checked.
- DNS resolution helps understand how domain names connect to IP addresses.

**Security Significance:**

Nslookup helps security professionals understand domain resolution and basic DNS information.

### 4. cURL – HTTP Response Analysis

cURL is used to inspect HTTP response headers returned by a website.

**Command Used:**

```bash
curl -I https://networkwalks.com
```

**Observations:**

- HTTP response status can be checked.
- Server information may be displayed.
- Content type and other HTTP response headers can be inspected.

**Security Significance:**

HTTP header analysis helps understand the publicly visible configuration of a web server.

### 5. Wafw00f – Web Application Firewall Detection

Wafw00f is used to identify whether a website is protected by a Web Application Firewall (WAF).

**Command Used:**

```bash
wafw00f https://networkwalks.com
```

**Observations:**

The tool checks for the presence of a Web Application Firewall and displays its detection results, if available.

**Security Significance:**

It helps understand the security technologies used to protect web applications.

### 6. DNSenum – DNS Enumeration

DNSenum is used to collect DNS-related information associated with a domain.

**Command Used:**

```bash
dnsenum networkwalks.com
```

**Observations:**

- DNS records can be identified.
- Nameserver information can be collected.
- Mail server information may be available.
- Additional DNS-related information can be examined.

**Security Significance:**

DNS enumeration helps understand domain infrastructure and publicly available DNS information.

## Evidence – Footprinting and Reconnaissance

The following screenshots document the commands and results obtained during the practical.

1. WHOIS – Domain Information

<img width="1395" height="562" alt="image" src="https://github.com/user-attachments/assets/934439a1-d2ef-4988-bb50-5cc7d3912b3d" />

2. WhatWeb – Technology Identification

<img width="1492" height="215" alt="image" src="https://github.com/user-attachments/assets/2795481b-24f9-422b-9b22-cb39261d2daa" />

3. Nslookup – DNS Lookup

<img width="432" height="227" alt="image" src="https://github.com/user-attachments/assets/03e38ad5-6ad2-4122-855a-61fc5cd614e4" />

4. cURL – HTTP Response

<img width="1492" height="397" alt="image" src="https://github.com/user-attachments/assets/3568e35e-8191-47ce-bff7-b6eb34634953" />

5. Wafw00f – WAF Detection

<img width="1061" height="575" alt="image" src="https://github.com/user-attachments/assets/81467b81-2300-407b-a9d9-b638e49d3a3e" />

6. DNSenum – DNS Enumeration

<img width="1080" height="472" alt="image" src="https://github.com/user-attachments/assets/a58a031a-1024-4200-b402-494a135cb1fe" />


---

# Practical 2 – Network Scanning Using Zenmap (W2-PM5)

## Objective

The objective of this practical was to discover active devices on a local network, identify their IP addresses and understand network topology using Zenmap.

## Tools Used

- Windows
- Zenmap
- Nmap 7.993

## Network Details

| Parameter | Details |
|---|---|
| Network Interface | Wi-Fi |
| IP Address | 192.168.2.110 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 192.168.2.14 |
| Network Range | 192.168.2.0/24 |

### Step 1 – Identifying the IP Address

The Windows Command Prompt was used to identify the local IP address and network configuration.

**Command Used:**

```cmd
ipconfig
```

The command displayed the IPv4 address, subnet mask and default gateway of the Wi-Fi network.

### Step 2 – Performing a Ping Scan

Zenmap was used to perform a host discovery scan on the local network.

**Target:**

```text
192.168.2.0/24
```

**Command Used:**

```bash
nmap -sn 192.168.2.0/24
```

The `-sn` option performs host discovery without performing a port scan.

### Step 3 – Active Hosts Discovered

The scan successfully identified three active hosts on the local network.

| IP Address | MAC Address / Identification |
|---|---|
| 192.168.2.14 | 84:D8:1B:44:00:3C – TP-Link Technologies |
| 192.168.2.109 | F6:33:85:E1:E6:53 – Unknown |
| 192.168.2.110 | Windows PC used for scanning |

### Scan Details

- Scan Type: Ping Scan.
- IP Addresses Scanned: 256.
- Active Hosts Found: 3.
- Scan Duration: Approximately 3.37 seconds.
- Nmap Version: 7.993.

### Step 4 – Network Topology

After completing the scan, the Topology tab in Zenmap was opened to view the discovered hosts.

The topology view displayed the discovered devices as graphical nodes along with the local host.

The diagram showed three discovered devices connected visually to the localhost node.

This helped me understand how network discovery results can be represented through a graphical network diagram.

**Observation:**

The scan identified three active hosts. The topology diagram provided a visual representation of the discovered hosts and their relationships in the Zenmap interface.

**Result:**

The network scanning activity was completed successfully. I was able to identify active hosts, check available MAC address information and generate a network topology diagram using Zenmap.

## Evidence – Network Scanning

### 1. Zenmap Host Discovery

<img width="667" height="490" alt="image" src="https://github.com/user-attachments/assets/64e5cb60-896d-4217-b773-eb72af31546f" />


### 2. Zenmap Network Topology

<img width="1263" height="702" alt="image" src="https://github.com/user-attachments/assets/7302de9b-d81e-473c-b828-f24dde27f5cf" />


---

# Consolidated Findings

| No. | Practical | Tool Used | Key Findings |
|---|---|---|---|
| 1 | PM1 | WHOIS | Collected domain registration information. |
| 2 | PM1 | WhatWeb | Checked website technologies. |
| 3 | PM1 | Nslookup | Performed domain-to-IP resolution. |
| 4 | PM1 | cURL | Inspected HTTP response headers. |
| 5 | PM1 | Wafw00f | Checked for WAF presence. |
| 6 | PM1 | DNSenum | Performed DNS enumeration. |
| 7 | PM5 | Zenmap | Discovered three active hosts. |
| 8 | PM5 | Zenmap Topology | Generated a graphical network topology. |

# Security Recommendations

1. Regularly review publicly exposed website information.
2. Keep website technologies and software updated.
3. Review DNS records and remove unnecessary entries.
4. Monitor HTTP response headers for unnecessary information disclosure.
5. Properly configure and monitor Web Application Firewalls.
6. Perform regular network discovery within authorised networks.
7. Investigate unknown devices connected to the network.
8. Maintain updated network documentation and topology diagrams.
9. Perform security testing only within an authorised scope.

# Learning Outcomes

Through these practical activities, I learned:

- How to collect domain registration information using WHOIS.
- How to identify website technologies using WhatWeb.
- How to perform DNS lookups using Nslookup.
- How to inspect HTTP response headers using cURL.
- How to identify Web Application Firewalls using Wafw00f.
- How to enumerate DNS records using DNSenum.
- How to perform network discovery using Zenmap.
- How to identify active devices on a network.
- How to understand and interpret network topology diagrams.
- The importance of documenting results during cybersecurity testing.

# Conclusion

During Week 2 of my Cybersecurity Internship at Networkwalks, I worked on practical activities related to footprinting, reconnaissance and network scanning.

I explored different Kali Linux tools used for collecting domain and website information. I also performed a network discovery scan using Zenmap, which helped me identify three active hosts on my local Wi-Fi network and generate a network topology diagram.

These activities helped me improve my understanding of information gathering, DNS enumeration, website technology identification and network discovery. I also learned the importance of analysing results, documenting observations and following an authorised testing scope.

# Author

**Name:** Alby John

**Role:** Cybersecurity Intern

**Internship:** Networkwalks

**Domain:** Cybersecurity

**Week:** 02

**Modules:** W2-PM1 and W2-PM5
