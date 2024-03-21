# Networking Basics
**Network** - group of interconnected systems that share data
**Node / Host** - addressable device on a network
**Server** - hard/software that provides network resource
**Client** - device that accesses resource

# Network Devices
**Hubs** - used long time ago, caused security vulnerabilities
**Switches** - allows you to manage traffic in a LAN
**Router** - connects different networks
**VLAN** - segmenting network without subnets

# Protocols
-> set of rules for formatting, processing, and transferring data
-> like a *common language*, can be used regardless of OS, hardware, etc

# Medium
-> how data is transferred

## Cable
- coaxial
- twisted pair
- fibre optic

# Network Services
## DNS - "phonebook"
-> resolves domain names to ip addresses

- after a lookup of a domain, the ip of the domain is stored in the host's cache memory
- DNS lookup will stay in cache for a certain *TTL* (Time To Live)
	- Very long TTL can cause problems, see [[#Authority of DNS]]

### "Hierarchy of DNS"
*!!! Omit stop resolver if external DNS*
Cache Memory
(If not found, queries to Resolver)

Resolver (ISP) DNS 
(if not found, resolver redirects to Root server)

Root server (12 sets in the world)
(Root server finds the corresponding TLD server, tells to resolver)

TLD (Top Level Domain) server *stores address information for top level domains, ex: .com*
(TLD tells resolver Authoritative Name Server address)

Authoritative Name server stores *everything about the domain*
 (AN server responds with IP to resolver, resolver passes to client)

### Authority of DNS
**Authoritative** - DNS lookup came from a responsible server
**Non-Authoritative** - DNS lookup did not come from responsible server, likely *cached info*
-> Non Authoritative result does not necessarily mean that info is wrong, but if IP address of domain changed then result could be wrong

### DNS record types
!!!! A single DNS lookup result could contain more than one record, ex: SOA is typically at header of record
- A (Host) - provides IPv4 from FQDN (fully qualified domain name)
	- *Forward Lookup* / *A-Lookup*
- AAAA - IPv6 from FQDN
	- *Forward Lookup* / *Quad-A-Lookup*
- PTR - provides FQDN from IP (*opposite of A*)
	- *Reverse Lookup*
- SOA (Start Of Authority) - info about authoritative name server, TTL, etc
- NS - lists name servers for a domain(alternative to SOA)
- SRV - Service Records, lists critical services & IP
- CNAME (alias) - supports alternate names for a single domain
- MX (mail) - determines the host name (not IP) of the mail server
- TXT (Text) - contains useful information in plain text, ex:...
	- SPF (Sender Policy Framework) protocol, mail servers check incoming mail for unauthorised sender
	- DKIM (Domain Keys Identified Mail), digitally sign outgoing mail -> can be verified by recipient 

### Zone Transfers
-> Replication of a DNS database (on a DNS server), sending to a secondary server for *redundancy*

## DHCP - "name assigning"
-> Dynamic Host Configuration Protocol
-> Allocates a IP address for a client on the network for a certain period of time

**Scope** - range of IP addresses that can be issued
**Leases** - temporarily issued IPs (all addresses except reserved ones)
**Reservations** - Addresses reserved for particular nodes (based on MAC address)
**Exclusions** - Manually configured list of addresses that *will not be assigned*

### DHCP Lease Process - "DORA"
#### Discover
- client broadcasts discover message to all devices on network, to discover the DHCP server

#### offer
- server responds with a list of available IP addresses

#### request
- client requests the first IP address offered

#### acknowledge
- server removes assigned IP address from available ones

## IPAM - IP Address Management
-> series of software tools that track IP address usage
-> might be used in incident response & forensics

# Encapsulation
*Data travels down the OSI Model*


- At each layer, something is added to help data travel from node to node

## PDU (Protocol Data Unit)s
- Application, Presentation, Session - Data 
- Transport - Segment
- Network - Packet
- Data Link - Frame
- Physical - Bits


[Screenshot 2022-06-26 at 6.19.07 PM.png]]

# OSI Model
*All People Seem To Need Data Processing*
-> Open Systems Interconnection Model
-> Facilitates Interoperability between devices, even of different vendors
-> As we go up the OSI Model, devices gain "intelligence"

## Physical
-> transmits raw bits over a physical medium
ex: cables, connectors, hubs
*dumb devices - don't know where data goes*

## Data Link
-> formats bits into frames, in order for them to be able to traverse through a network
-> 2 sublayers, 
**LLC** (Logical Link Control), "upper" layer, provides services to Network layer, 
-> flow control of frames, error detection

**MAC** (Medium Access Control), "lower" layer, defines how devices access the physical layer, 
-> MAC addressing, encapsulation
-> CSMA / CD (Wired Connection), CSMA / CA (Wireless)
- Ethernet (CSMA / CD) - 802.3
- Wireless (CSMA / CA) - 802.11
- Token Passing - 802.5 (no longer used)

| IEEE Standard | Technology Type | Media Access Method | Description                                                                                                     |
| ------------- | --------------- | ------------------- | --------------------------------------------------------------------------------------------------------------- |
| 802.3         | Ethernet        | CSMA/CD             | Hosts "take turns" transmitting on single wire, start over if collision                                         |
| 802.5         | Token Ring      | Token Passing       | Single control frame traverses network, nodes hold onto frame when communicating, passes frame on when finished |
| 802.11        | Wireless        | CSMA/CA             | Nodes try to avoid collisions by detecting active transmissions; or use RTS / CTS                               |
| 802.12        | Polling         | N/A                 | Polling server asks each node if they need to transmit                                                          |
|               |                 |                     |                                                                                                                 |

### MAC Address
a.k.a *physical addressing*
-> 48 bit address in hexadecimal
First 24 bits indicate manufacturer
Next 24 bits are unique to NIC

[Pasted image 20220627121641.png]]

-> In a network, the Network Interface Controller scans traffic for it's own MAC address

### ARP (Address Resolution Protocol)
-> Maps IP addresses to MAC addresses
-> Info stored in arp cache

## Network
-> Decides which physical path packets will take
- Protocols starting with 'I', ex: ICMP, IPSec
- Routers, Level 3 Switches

### IP addressing
a.k.a *logical addressing*

### ICMP
-> Internet Control Messaging Protocol
-> Tests basic physical connectivity
used in ping, traceroute

## Transport
-> Transmits data through TCP / UDP
-> End to End transmission of data
-> Ports are "added" at this layer

**TCP** - Connection Oriented, reliable, slow
**UDP** - Connectionless, unreliable, fast

### TCP (Transmission Control Protocol)
- Used when data integrity is important, ex: FTP, Emails, SSH
- 3 way handshake
	- SYN ("Do u want to talk?")
	- SYN / ACK ("Yes I want to talk")
	- ACK ("Ok")
- Data can be delivered after the handshake
- TCP will resend data if a packet is missing

### UDP (User Datagram Protocol)
- Used for "lossy" applications, where packet loss is acceptable ex: DNS lookups, Video Streaming, VoIP
- *"Fire and Forget"* protocol, does not care if packets reach destination
- Faster than TCP

## Session
-> Setup, Maintenance, Termination of a *Connection*
- Protocols include...
	- RPC (Remote Procedure Call) - calling a procedure on a different device
	- SIP (Session Initiation Protocol) - protocol for VoIP session
	- SQL (Structured Query Language) - performing operations in databases

## Presentation
-> Ensures that Data is in a useable format + Encryption
-> Only layer without any protocols
- Formatting - presenting data in a *universal format*, ex: files presenting in mac & linux
- Compression - removes redundancy in files, improves network efficiency
- Encryption - At layer 6, *file encryption*

## Application
-> drive applications that humans interact with
-> layer with the *"most intelligence"*, knows about the data
- Certificate services - provide authentication for systems
- Proxy servers - node that acts as a *gateway* between client & server
- WAF (Web Application Firewall) - Firewall that monitors HTTP/S traffic
	- Client -> WAF -> Server

- Protocols: 
	- SNMP (Simple Network Management Protocol)
	- FTP (File Transfer Protocol) - TCP file transfer
		- TFTP (Trivial File Transfer Protocol) - UDP file transfer


# TCP/IP Model
## RFC (Requests for Comments)
-> TCP / IP is a *open protocol*, community contributors can submit changes to IETF
- A RFC cannot be modified once submitted, a new one has to be made

## TCP / IP Protocols
**Port Number** - software identifier such that devices understand which protocol to use for incoming traffic
-> Ports serve as a conceptual entryway into a system, or a endpoint


### FTP (File Transfer Protocol) - PORT 21 / TCP
-> File transfer w/ TCP, unsecure b/c of unencrypted authentication

(Don't need to know)
**client-server architecture**
1. client initiates control TCP connection, from ephemeral port (client) to port 21 (server)
**PASSIVE FTP**
2. (after successful connection) FTP connection from ephemeral port (client) to port 21 (server)
**ACTIVE FTP**
2. (after successful connection) FTP connection from port 21 (server) to ephemeral port (client)

### SSH (Secure Shell) - PORT 22 / TCP
-> used to perform operations securely over a unsecured network

- client-server architecture
- SSH used for SCP (Secure Copy Protocol), S/FTP (secure FIle Transfer Protocol)
	- !! Therefore, SCP and S/FTP uses port 22
- two major versions, SSH1 & SSH2, SSH 2 has less encryption options, but less vulnerable

### TELNET (Teletype Network) - PORT 23 / TCP
-> protocol used to transmit data in plain text (unencrypted) 

- one of the first internet protocols
- UNSECURE, don't use for accessing any kind of sensitive data

### SMTP (Simple Mail Transfer Protocol) - Port 25 / TCP
-> communication protocol for mail transfers, for *Sending & Receiving*
- Send & Receive mail over *TCP*
- Widely used in email servers & mail transfer services

### TACACS+ - Port 49 / TCP
-> remote authentication service, fully encrypts packets
- Used for remote administration
- centralises all logins onto a network
- 3 Functions....
- Authentication
	- Device tunnels onto a network, provides username & password
	- username & pw forwarded to TACACS+ server, server checks legitamacy
- Authorization
	- Device runs command on network
	- request forwarded to TACACS+ server, check if device has corresponding privileges
- Accounting
	- Every part of the TACACS+ session is forwarded to TACAS+ server, 
	- Logs forwarded to Syslog, IDS, etc

### DNS (Domain Name Service) - Port 53 / Default UDP, TCP if packet too big
-> Internet's "phonebook", designed to be *Hierarchical*
see [[#DNS - phonebook]]

### DHCP (Dynamic Host Configuration Protocol) - Port 67,68 / TCP
-> Allows computers to request IP addresses

### TFTP (Trivial FTP) - Port 69 / UDP
-> unreliable FTP over UDP, typically used for file transfer over LAN

### HTTP (HyperText Transfer Protocol) - Port 80 / TCP
-> used for communication between client & web server
- not secure

### POP (Post Office Protocol) - Port 110 / TCP (plain text), TCP/995 (w/TLS)
-> One way protocol for *email retrieval*, mail server -(unread emails)> client 
- Currently version 3 (POP3)
- Does not synchronise across different devices

### IMAP (Internet Mail Application Protocol) - TCP / 143, 993 (w/TLS)
-> Another *email retrieval* protocol
- Stores emails on a mail server, and synchronises read / unread across devices
- SMTP sends mail to mail server, POP & IMAP retrieves mail

### NTP (Network Time Protocol) - Port 123 / UDP
-> protocol for clock synchronisation between devices on network

### SNMP (Simple Network Management Protocol) - UDP / 161
-> used to monitor network devices, only SNMP v3 is encrypted

**Agent** - any SNMP enabled device, contains objects

**Objects** 
- measurements specific to each device (ex: temperature, uptime, etc)
- each object is assigned a OID (object id)

**MIB (Management Information Base)**
- all Objects and their corresponding OIDs are stored in each device's MIB
- The central manager uses MIBs to request specific objects from a device

**Central Manager** -  A device responsible for communicating with agents

**NMS** - Network Management System, piece of software that can communicate with agents

**SNMP Trap Messages** - messages sent over 162/udp by agents, if a critical event happens

### LDAP (Lightweight Directory Access Protocol) - TCP/UDP / 389/636(Secure)
-> industry standard protocol for accessing & maintaining Active Directory databases

**Active Directory** - "authentication servers"
- a distributed database containing information about user credentials, permissions, groups, etc
- used to allocate network resources
- responsible for Authentication & Authorisation 

### HTTPS - TCP/443
-> Uses SSL(Secure Sockets Layer) / TLS (Transport Layer Security)

### SQL Server - TCP / 1433

### SQLnet - TCP / 1521
-> connects client & server

### MySQL - TCP / 3306

### RADIUS (Remote Authentication Dial-In User Services) - UDP / 1812/1813
-> similar to [[#TACACS - Port 49 TCP]], centralised, remote authentication 
! 802.1x & EAPoL (Extensible Authentication Protocol over LAN)
- Used for remote access, not remote administration

### RDP (Remote Desktop Protocol) - TCP / 3389
-> provides GUI for remote access of a computer

### SIP (Session Initiaion Protocol) - TCP/5060 & 5061
-> manages VoIP sessions


# Network Storage
## NAS (Network Attached Storage)
-> Storage device that acts as a node on a network, making files accessible through protocols such as SMB (Server Messaging Blocks) & NFS (Network Filing System)
- remote disk appears as external storage volume

## SAN (Storage Area Network)
-> a specific network for file storage & access, connected to users via high speed cables
- makes a remote disk appear like a local disk

### SAN Architecture
3 Layers....
- **Host Layer** - devices that want to access files
- **Fabric Layer** - medium & networking devices that connect hosts to storage 
- **Storage Layer** - storage devices, typically organised into RAID groups for redundancy

### FCoE (Fiber Channel over Ethernet)
-> Network Topology that connects a *ethernet* network to a *fibre channel* network

**FC Switch** - Layer 3 switch, forwards FC traffic & provides FC services
**FC Forwarder** - Layer 3 switch, forwards FC traffic (basically a router for FC, not a switch)

## ISCSI (Internet Small Computer Systems Interface)
-> protocol that transports SCISI (data transfer protocol) data 
- works with existing infrastructure (no need for fibre channel)

**LUN (Logical Unit Number)** - pointer pointing to the address on a SAN network where data is stored (LUN obfuscates where data is being stored)

## Infiniband
-> very high performance communication standard, relatively new
- can be used to connect servers and SANs

## Jumbo Frames
->  increasing the max payload size of a frame
- increases transmission rates, but increases network latency

# Remote Access
## Dial Up
-> accessing via telephone line
-> PPP is secured with PAP / CHAP / EAP 

**PPP** - protocol used for WAN connections over telephone line
- if a user is dialing in, they are sending their data over cable and their data is not formatted into layer 2 frames
- In order for end-to-end WAN connections on a telephone line to happen, PPP adds layer 2 info to the data being dialed in

**PPPoE** - encapsulates PPP frames inside Ethernet frames, thus supporting connections to LANs with multiple nodes

!! PPP is not designed with security, other protocols needed to secure

**PAP** (Password Authentication Protocol) - password, but transmitted over plain text
-> Don't use
**CHAP** (Challenge Handshake Authentication Protocol) - client responds to a challenge from a server, which can only be answered if the client has the correct password
!! CHAP allows us to authenticate without having to send the password
-> used to be used
**EAP** (Extensible Authentication Protocol) - Supports other authentication methods
-> used nowadays

## Tunneling
-> Tunneling is the function of VPN (Virtual Private Network)s
-> *encapsulates* one protocol within another, creating a Virtual Network
-> can also provide encryption & authentication, 
-> can route non-routeable protocols & IP addresses (ex: IPv4 across IPv6 network)
! Tunneling replaced DIal-Up
](https://i.ytimg.com/vi/s37S5pf6wn0/maxresdefault.jpg)

### Common Protocols
- [[#PPTP Point to Point Tunneling Protocol]] 
- [[#L2TP Layer 2 Tunneling Protocol]]
- [[#IPSec]] (IP Security)
- [[#GRE]] (Generic Routing and Encapsulation)
- SSL (Secure Sockets Layer) / TLS (Transport Layer Security)

### PPTP (Point to Point Tunneling Protocol)
-> Tunneling based on **PPP** (Point to Point Protocol)
- Only works across IP networks
- Uses MPPE for encryption
- Uses **PAP**, **CHAP**, or **EAP** for authentication

### L2TP (Layer 2 Tunneling Protocol)
-> tunneling protocol that works across all network types
! Enhanced version of PPTP
- no built in security, needs [[#IPSec]]
- was made to address the fact that PPTP only worked on IP networks

### IPSec
-> secure protocol that encrypts & authenticates packets -> *confidentiality & integrity*
-> + encapsulation

#### IPSec Mode - Tunnel vs Transport
**Tunnel** - whole IP packet is encapsulated inside IPSec 'capsule', whole packet "wrapped up"
-> more secure
**Transport** - IPSec capsule only encapsulates IP payload, exposes destination & origin
-> faster performance

#### IPSec protocols
**AH** (Authentication Header)
- ensures *integrity* via a ICV (Integrity Check Value) (a checksum)
- checks the *entire packet*

**ESP** (Encapsulating Security Protocol)
- ensures *confidentiality (ENCRYPTION) + integrity* 
- only the *payload*

**IKE** (Internet Key Exchange) 
- sets up encryption algorithm + keys
- consists of two protocols...
	- Oakley - uses Diffie Hellman to agree on a key
	- ISAKMP - manages keys, SA (Security Associations) and SPI (Security Parameter Index)

**SA** (Security Association) - two or more identifiers for each secure connection

**SPI** (Security Parameter Index) - random number unique for each secure connection

### GRE (Generic Route Encapsulation)
-> GRE tunnels allow packets to traverse incompatible networks (ex: IPv4 packet over IPv6 network)
- adds a extra IP header, thus creating a point-to-point connection
- lacks encryption & flow control
- can forward multicast traffic, unlike VPNs


#### Encapsulation and De-Encapsulation on the Switch

Encapsulation—A switch operating as a tunnel source router encapsulates and forwards GRE packets as follows:

1.  When a switch receives a data packet (payload) to be tunneled, it sends the packet to the tunnel interface.
    
2.  The tunnel interface encapsulates the data in a GRE packet and adds an outer IP header.
    
3.  The IP packet is forwarded on the basis of the destination address in the outer IP header.
    

De-encapsulation—A switch operating as a tunnel remote router handles GRE packets as follows:

1.  When the destination switch receives the IP packet from the tunnel interface, the outer IP header and GRE header are removed. 
    
2.  The packet is routed based on the inner IP header.
