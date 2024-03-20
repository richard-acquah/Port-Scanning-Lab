# Port-Scanning-Lab

## Objectives
Port scanning is essential in detecting open ports and services on a network. The labs demonstrate how Nmap is used to map out the network, discover open ports and services and the operating systems of devices on the network. The primary focus of this lab is scanning a virtual network and scanme.nmap.org using Nmap and online port scanners.
## Skills learned
+ Network enumeration.
+ Vulnerability scanning.
+ Enhanced knowledge of network security.
## Resources / Tools / Utilities
+ Virtual lab - pf sense firewall, Kali VM, Ubuntu VM, Windows 10 VM and Metasploitable 3 VM.
+ Windows 10 22H2 Pro
+ Internet Access
## PORT SCANNING USING NMAP
### Network Diagram and Virtual Machines.

![netmap1](https://github.com/richard-acquah/Port-Scanning-Lab/assets/136107996/c5894afe-482b-41df-8acd-0063d01a79ad)
<img width="1920" alt="v machines used1" src="https://github.com/richard-acquah/Port-Scanning-Lab/assets/136107996/6d9f24b8-2608-4d94-a939-c74f90907cec">

## Nmap Installation Verification
First, verify if Nmap is installed on the Kali VM. To verify, the command ***nmap --version*** is used:

<img width="512" alt="verify nmap1" src="https://github.com/richard-acquah/Port-Scanning-Lab/assets/136107996/d6eca86f-296a-4f2f-8825-60da3036162f">

## Host Discovery
The first scan is used to discover hosts on the network 192.168.10.1/24. The command ***sudo nmap -sn 192.168.10.1/24***. The _-sn_ switch is used to disable port scanning thereby discovering only the hosts available on the network. The result shows the discovered host's IP addresses.

<img width="583" alt="result of nmap discover host1" src="https://github.com/richard-acquah/Port-Scanning-Lab/assets/136107996/518cd57f-1a9a-4d3c-96b9-0c52beb0105a">

## Ports and Services Discovery
To discover open ports on the discovered hosts, the command ***sudo nmap 192.168.10.1-7***. The command without a specified switch defaults to _SYN port scan_. Again, since the IP addresses of the hosts are known, and the IP range is specified in the command.
+ The first host is the default gateway with 192.168.10.1 as its IP address. The host has all scanned ports filtered by the firewall except for ports 53, 80 and 443 which allow DNS traffic and web traffic to pass through.
+ The second host is the Ubuntu VM with 192.168.10.3 as its IP address. The host filters all Nmap traffic from accessing any of its ports.
+ The Third host is the Windows 10 VM with 192.168.10.5 as its IP address. It shows three open ports 135, 139 and 445. These vulnerable ports and attackers can be used as entry points and should be disabled when not in use.\
+ The fourth host is the Metasploitable 3 VM. This VM is made vulnerable intensionally with numerous security flaws. The VM has an IP address of 192.168.10.6 and a dozen open ports running various services.

  <img width="492" alt="port scan result1" src="https://github.com/richard-acquah/Port-Scanning-Lab/assets/136107996/6244a477-793b-4d7a-8778-33d019a5ff41">

## Operating System Discovery
To discover the operating system of a host device on the network, the ***-O*** switch is used with the Nmap command. The host with IP 192.168.10.5 is used. An aggressive scan can also be done to discover the host's OS with additional valuable information. The switch ***A*** is used. The OS discovery scan uses probability percentage to guess the OS. The accuracy of the guess is inferred from the probability score. A higher percentage denotes better accuracy.

***-O*** Switch

<img width="497" alt="os discovery scan1" src="https://github.com/richard-acquah/Port-Scanning-Lab/assets/136107996/4c9df403-fbc7-4de0-8565-50ae99ba627f">

***-A*** Switch

<img width="502" alt="os discovery -A1" src="https://github.com/richard-acquah/Port-Scanning-Lab/assets/136107996/a0feb807-99b1-4e4d-8b46-72359050cabb">

## USING ONLINE PORT SCANNER FOR ENUMERATION
To perform port scanning using online tools requires internet access. The tool used in this lab is Pentest Tools and it can accessed at https://app.pentest-tools.com.
On the Pentest Tool web interface dashboard, click SCAN WITH TOOL to view available tools and select Port Scanner.

<img width="928" alt="pentest dashboard1" src="https://github.com/richard-acquah/Port-Scanning-Lab/assets/136107996/b24343a3-7b7b-4403-a3b0-46d4f93d17ac">
<img width="920" alt="tools1" src="https://github.com/richard-acquah/Port-Scanning-Lab/assets/136107996/5e1aec9c-772e-4a7e-b0c7-418a9f1b7bbe">

The Port Scanner interface is displayed:




