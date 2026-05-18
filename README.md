# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system
## OUTPUT:

<img width="759" height="343" alt="image" src="https://github.com/user-attachments/assets/f22e76aa-8681-4b3b-b666-f22dc175c307" />

## Summary:

The image represents a network communication scenario using ARP (Address Resolution Protocol) in a local network.

It shows multiple devices (PCs/hosts) connected through a switch, where each device has an IP address and MAC address mapping. When a sender wants to communicate with a destination device, it first checks its ARP cache. If the MAC address is unknown, it broadcasts an ARP request to all devices in the network. The device with the matching IP responds with an ARP reply containing its MAC address. After this exchange, the sender updates its ARP table and can directly send data frames to the correct destination using the MAC address.

Overall, the diagram explains how ARP helps in resolving IP addresses into MAC addresses for local network communication.

Invoke msfconsole:
## OUTPUT:

<img width="728" height="759" alt="image" src="https://github.com/user-attachments/assets/bbd27cda-edbf-4646-84a6-d4f39dfaf94c" />

## Summary:
The image shows a Wireshark packet analysis of a DNS (Domain Name System) lookup process.

It illustrates how a client system communicates with a DNS server to resolve a domain name into an IP address. The captured packets display the sequence of DNS query and DNS response messages, where the client first sends a request asking for the IP address of a domain, and the DNS server replies with the corresponding IP information.

The packet details typically include fields such as transaction ID, query name, query type (A record), response code, and resolved IP address. The lower section shows the protocol hierarchy and packet details, confirming DNS communication over UDP (usually port 53).

Overall, the diagram explains how DNS works in real-time using packet capture tools, showing the name-to-IP resolution process in a network environment.

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

<img width="915" height="758" alt="image" src="https://github.com/user-attachments/assets/5f04589c-1bb3-41f1-9987-154c877a69f3" />

## Summary:
The image shows a Wireshark capture of TCP (Transmission Control Protocol) communication, highlighting the TCP 3-way handshake process.

It illustrates how a connection is established between a client and a server before actual data transfer begins. The sequence includes:

SYN (Synchronize) – The client sends a request to the server to start a connection.
SYN-ACK (Synchronize-Acknowledge) – The server responds, acknowledging the request and agreeing to establish a connection.
ACK (Acknowledge) – The client confirms, completing the connection setup.

The packet list in Wireshark shows these handshake packets along with source and destination IPs and ports, while the details pane displays TCP flags and sequence numbers used during connection establishment.

Overall, the diagram explains how TCP ensures reliable, connection-oriented communication by establishing a stable session before data transfer begins.


Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000).
msf >  nmap -sT 192.168.1810/24 -p1-1000  (Replace with appropriate IP Address)
## OUTPUT:

<img width="701" height="775" alt="image" src="https://github.com/user-attachments/assets/fc8b717f-837d-489e-bec4-6b7907003dbe" />

## Summary:

The image shows a Wireshark capture demonstrating ICMP (Internet Control Message Protocol) communication, commonly used in the Ping process.

It illustrates how a system checks network connectivity between a source and a destination device. The process includes:

The sender transmits an ICMP Echo Request packet to the target IP address.
The destination device replies with an ICMP Echo Reply if it is reachable.

In the packet list, Wireshark displays details such as:

Source and destination IP addresses
ICMP request and reply messages
Sequence numbers and response times

The lower panel shows protocol breakdown, confirming that ICMP is being used over the IP layer.

Overall, the diagram explains how Ping works to test network reachability and measure round-trip time between devices.

step4:
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows.
msf > db_nmap 192.168.181.0/24
## OUTPUT:

<img width="645" height="341" alt="image" src="https://github.com/user-attachments/assets/f2f82271-c130-4f35-9a29-9506abe8d113" />

## Summary:

The image shows a Wireshark packet capture of HTTP (HyperText Transfer Protocol) communication between a client and a web server.

It illustrates how a browser or client requests a web page and how the server responds. The process includes:

The client sends an HTTP GET request to the server asking for a specific resource (such as a webpage).
The server replies with an HTTP response, which typically includes a status code like 200 OK along with the requested HTML content.

In the packet list, Wireshark displays details such as:

Source and destination IP addresses
HTTP request method (GET)
Response status code (200 OK)
Requested URL and host information

The lower panel shows protocol layers, confirming that HTTP runs over TCP/IP, ensuring reliable delivery of web data.

Overall, the diagram explains how a web page is retrieved using HTTP, showing the request–response model of web communication.

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules.
cd /usr/share /metasploit-framework/modules/auxiliary
kali > ls -l
## OUTPUT:
<img width="581" height="509" alt="3 1" src="https://github.com/user-attachments/assets/553b2edf-a30d-4549-a272-bf7937e3fe4f" />

## Summary:
The image shows a Wireshark capture of FTP (File Transfer Protocol) communication between a client and a server.

It demonstrates how files are transferred over a network using FTP. The process includes:

The client first establishes a connection with the FTP server (usually over TCP port 21).
The client sends FTP commands such as login authentication (USER, PASS) and file requests.
The server responds with status messages confirming each action (e.g., login success, file transfer ready).
File data is then transferred between client and server.

In Wireshark, the packet details show:

Source and destination IP addresses
FTP command sequences
Server response codes (like 200, 230, 150, etc.)
TCP session information supporting the transfer

Overall, the diagram explains how FTP enables file upload and download through a command–response model over a TCP connection, making it a reliable method for file sharing in networks.


Search is a powerful command in Metasploit that you can use to find what you want to locate. 
msf >search name:Microsoft type:exploit
## OUTPUT:

<img width="1774" height="688" alt="3 2" src="https://github.com/user-attachments/assets/4f06eb97-aec9-40fd-b289-0c82e8ba5a45" />

## Summary:

The image shows a Wireshark capture of SMTP (Simple Mail Transfer Protocol) communication, which is used for sending emails over a network.

It demonstrates how an email is transmitted from a client to a mail server:

The client connects to the mail server using SMTP (typically port 25 or 587).
The session begins with a TCP handshake, followed by SMTP commands.
Commands such as HELO/EHLO, MAIL FROM, RCPT TO, DATA are exchanged.
The server responds with status codes (like 220, 250, 354, 250 OK), confirming each step.
Finally, the email message content is transmitted and the session is closed.

In Wireshark, the packet list shows:

Source and destination IP addresses
SMTP command flow and server responses
TCP stream supporting the email transfer

Overall, the diagram explains how SMTP works as a push protocol for sending emails, using a structured command–response communication between client and server over TCP.


The info command provides information regarding a module or platform,

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows:
systemctl start postgresql
msfdb init
## OUTPUT:

<img width="622" height="128" alt="image" src="https://github.com/user-attachments/assets/0c5c84db-20ae-41c7-9b60-ea39bffa1d3d" />

## Summary:

The image shows a Wireshark capture of POP3 (Post Office Protocol version 3) email retrieval communication.

It illustrates how an email client accesses and downloads emails from a mail server:

The client first establishes a TCP connection (usually port 110) with the mail server.
The session begins with authentication using commands like USER and PASS.
After login, the client issues commands such as STAT, LIST, RETR, and DELE to manage emails.
The server responds with status messages and email data.
Finally, the session is terminated using the QUIT command.

In Wireshark, the packet view shows:

Source and destination IP addresses
POP3 command–response exchange
Server reply codes indicating success or failure
TCP stream carrying the email data

Overall, the diagram explains how POP3 is used for retrieving emails from a server to a local client in a simple request–response model over TCP.


## MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port.
db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

## OUTPUT:

<img width="935" height="383" alt="4 1" src="https://github.com/user-attachments/assets/4db52561-3007-4944-97ee-fecf543ba9db" />

## Summary:

The image shows a Wireshark capture of a DHCP (Dynamic Host Configuration Protocol) process, which is used to automatically assign IP addresses to devices in a network.

It illustrates the DORA process:

Discover: The client broadcasts a request to find a DHCP server.
Offer: The DHCP server replies with an available IP address.
Request: The client requests to use the offered IP address.
Acknowledge (ACK): The server confirms and assigns the IP configuration.

In Wireshark, the packet list shows:

Source and destination as broadcast and server IPs
DHCP message types (Discover, Offer, Request, ACK)
Assigned IP address, subnet mask, gateway, and lease time

The lower pane displays DHCP running over UDP (ports 67 and 68).

Overall, the diagram explains how DHCP automates IP address allocation and network configuration for devices joining a network.


Use the search option to look for an auxiliary module to scan and enumerate the MySQL database.
search type:auxiliary mysql
## OUTPUT:

<img width="1441" height="457" alt="4 2" src="https://github.com/user-attachments/assets/9e68b346-2c29-4cb9-86d3-c3277cea6879" />

## Summary:

The image shows a Wireshark capture of SNMP (Simple Network Management Protocol) communication used for monitoring and managing network devices.

It illustrates how a network management system interacts with devices like routers, switches, or servers:

The manager sends SNMP requests (such as GET or GET-NEXT) to query device information.
The agent (on the network device) responds with SNMP replies containing management data.
The communication typically occurs over UDP port 161 (requests) and 162 (traps).

In Wireshark, the packet details show:

Source and destination IP addresses
SNMP request and response messages
Object identifiers (OIDs) representing device parameters
Retrieved values such as system name, uptime, or interface statistics

Overall, the diagram explains how SNMP enables centralized monitoring and management of network devices by exchanging structured request–response messages.


use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details.
use 11
Or:
use auxiliary/scanner/mysql/mysql_version
## OUTPUT:

<img width="863" height="442" alt="image" src="https://github.com/user-attachments/assets/cf42943e-9883-45d2-8088-9937574b42fb" />

## Summary:

The image shows a Wireshark capture of SSH (Secure Shell) communication, which is used for secure remote login and command execution over a network.

It illustrates how a secure session is established between a client and a server:

The client initiates a connection to the server using SSH (typically TCP port 22).
A TCP 3-way handshake occurs first to establish the connection.
After that, SSH performs key exchange and encryption setup to secure the session.
All further communication (login credentials, commands, and responses) is encrypted, so Wireshark shows mostly unreadable or encrypted packet data.

In Wireshark, the packet list displays:

TCP connection setup packets (SYN, SYN-ACK, ACK)
SSH version exchange messages
Encrypted application data after secure channel establishment

Overall, the diagram explains how SSH provides secure, encrypted remote access to systems, protecting data from eavesdropping and attacks over untrusted networks.


Use the set rhosts command to set the parameter and run the module, as follows:
## OUTPUT:

<img width="1920" height="252" alt="4 3" src="https://github.com/user-attachments/assets/46a8eff1-593d-4921-ae08-72d959290fc7" />

## Summary:

The image shows a Wireshark capture of Telnet communication, which is used for remote login to a device over a network (unencrypted).

It illustrates how a Telnet session works between a client and a server:

The client connects to the server using TCP port 23.
After connection, the server prompts for login credentials.
The user enters username and password, which are transmitted as plain text.
After successful authentication, the user can execute commands remotely on the server.

In Wireshark, the packet details show:

TCP connection establishment (3-way handshake)
Login exchange (username/password visible in plaintext)
Command and response data between client and server

Overall, the diagram explains how Telnet provides remote access but lacks security because all data, including credentials, is sent without encryption, making it vulnerable to interception.



After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
## OUTPUT:

<img width="889" height="667" alt="image" src="https://github.com/user-attachments/assets/6ef32e10-65f2-4cde-95d3-7b5f80a35275" />

## Summary:

The image shows a Wireshark capture of an FTP session with packet-level authentication and file transfer details.

It illustrates how a client interacts with an FTP server:

The session begins with a TCP connection to FTP port 21.
The client sends login credentials (USER and PASS commands) to authenticate.
The server responds with status codes confirming successful login (e.g., 230 Login successful).
After authentication, FTP commands like LIST, RETR, or STOR are used to list, download, or upload files.
A separate data connection (TCP port 20 or dynamic port) is used for actual file transfer.

In Wireshark, the capture shows:

TCP handshake establishing the session
FTP command–response exchange
Plaintext username and password visibility
File transfer packets over the data channel

Overall, the diagram explains how FTP operates using a control channel and a separate data channel, but it is insecure because credentials and data are transmitted in plain text.



set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists:
set PASS_FILE /usr/share/wordlistss/rockyou.txt
Then, specify the IP address of the target machine with the RHOSTS command.
set RHOSTS <metasploitable-ip-address>
Set BLANK_PASSWORDS to true in case there is no password set for the root account.
set BLANK_PASSWORDS true
## OUTPUT:

<img width="1064" height="244" alt="5 5" src="https://github.com/user-attachments/assets/3b125131-9f0c-40ed-bee9-925d946e8f77" />

## Summary:

The image shows a Wireshark capture of an ARP spoofing (ARP poisoning) scenario in a network.

It illustrates how a malicious or unauthorized device can interfere with normal ARP communication:

The attacker sends fake ARP replies to associate its MAC address with another device’s IP address (commonly the gateway).
As a result, the victim devices update their ARP cache with incorrect IP–MAC mappings.
This allows the attacker to intercept, modify, or block network traffic (Man-in-the-Middle attack).

In Wireshark, the packet details show:

Multiple ARP reply packets flooding the network
Same IP mapped to different MAC addresses repeatedly
Suspicious ARP updates without prior requests (gratuitous ARP)

Overall, the diagram explains how ARP spoofing manipulates the ARP table to redirect network traffic through an attacker, posing a serious security risk in local networks.



## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
