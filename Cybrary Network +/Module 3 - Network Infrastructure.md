# Network Topology
**Physical Topology** - The physical arrangement of devices on a computer network & how they communicate with each other

**Logical Topology** - The logical arrangement of devices on a network & how they communicate
+ describes how signals act on a network

## Bus Topology
-> every device on network is connected to the same network cable
- single collision domain, has to use CSMA/CD
- terminator at each end, to prevent signal bounce
- single point of failure (cable)

## Ring Topology
-> the connectivity of nodes resembles a ring
- packets travel from node to node until it reaches its destination
- single point of failure (each node)


## Star Topology
-> nodes connecting into a central node, which directs traffic
! if central node is layer 1, ex: hub -> then logical ring toplogy
- single point of failure

## Partial Mesh
-> some computers are connected to every other computer, while some are not
- used for peripheral computers connected to central mesh
- somewhat fault tolerant, more cost effective compared to full mesh


## Full Mesh
-> every device is connected to every other device
- expensive, but very fault tolerant

## Hybrid 
-> uses two or more different topologies


# Wired Communications

## RS-232 Cable
-> used for Serial connections (ex: modems)
- DB-8 or DB-9 *connector*
- Replaced by USB, rarely used

**Serial Communication** - sending one bit at a time, faster rate, like a "machine gun"
**Parallel Communication** - sending multiple bits at a time, slower rate, like a "shotgun"


## Coaxial
-> copper cable specifically built with a metal shield
- mainly used for Cable TV

### cable
- plastic jacket is fire resistant
- metalic shield prevents from EMI
- right in the middle (speed & cost)

![](https://www.telnetww.com/wp-content/uploads/2020/05/coaxial-cable-diagram-1-1024x686.png)

### connector
Both used for Cable TV


## Twisted Pair
-> pairs of wires twisted together to reduce crosstalk (electromagnetic interference)
- mainly used for telephone
- no shielding-> susceptible to EMI (ElecroMagnetic Intereference) & RFI (Radio Frequency Intereference)
- 100m before Attenuation
- slowest & cheapest

### catagories (aka cat)
Catagory 3: 10 Mbps
Catagory 5: 100 Mbps
Catagory 5e & 6: 1000 Mbps (Gigabit Internet)
Catagory 7: 10Gbps

### cable types
#### Straight through
-> T568a & T568B, used to *connect a node to a network device* (ex: computer to router)
- Not cross compatible, usually a organization sticks with one (568B is more common)
![](https://cdn.shopify.com/s/files/1/0014/6404/1539/files/T568A_vs_T568B___trueCABLE_1024x1024.jpg?v=1588882478)

- *Same pin assignments* on both ends
![](https://www.computercablestore.com/themes/ComputerCableStore/content/images/Topics/StraightThrough1.jpg)

#### crossover cables
-> used to *connect two network devices together*, has T568A on one end, T568B on another

- *Changed pin assignents* (T568A -> B or vice versa)
![](https://www.computercablestore.com/themes/ComputerCableStore/content/images/Topics/Crossover1.jpg)

#### Rollover
-> used to connect to another device's console / terminal (*create a interface*)

- *opposite* pin assignments
![](https://www.computercablestore.com/themes/ComputerCableStore/content/images/Topics/Rollover.jpg)

### connector
! RJ45 is for networking, RJ11 is for telephone

## fiber optic
- typically used to get data to router, twisted pair used inside network
- used for internet
- Optical transmission, Cannot be intercepted
- Immune to EMI / RFI
- fastest & most expensive

### single mode
- small core, less dispersion of light
- single beam of light
- up to 100km, used as *backbone* of internet

### multimode
- larger core, more dispersion
- more expensive
- up to 2km, used inside LANs

### WDM (Wavelength Directional Multiplexing)
- Bidirectional communication over single fibre
- CWDM (Coarse WDM) - 4 x 3.125 GB/s -> 12.5 GB/s
- DWDM (Dense WDM) - 160 x 10 GB/s -> 1.6 TB/s

### cable
- Highly reflective core allows light to 'bounce around'
- Cladding is non-reflective, so that light does not reenter core
- Coating provides mechanical protection

### connector
#### LC (Local connector)
- push down to connect, release locks
- popular now b/c of small connector size 

#### ST (Straight Tip)
- bayonet connectors, twist to 
- slightly larger than LC

#### SC (SUBSCRIBER CONNECTOR)
- locks into place

#### MTR-J (MECHANICAL TRANSFER  REGISTERED JACK)
- smallest connector


## Ethernet Standards
- Ethernet is the most popular networking technology
- Ethernet uses Twisted Pair (copper) and Fiber optic

**Baseband** - using a single frequency over medium, single stream of data
**Broadband** - using multiple frequencies over medium, multiple, simultaneous streams

### 10BASE-T (Twisted Pair)
-> 10mb/s Baseband Twisted Pair
- Two pairs of wire in cable
- Cat 3 cable
- 100m maximum

### 100BASE-TX
-> 100mb/s Baseband Twisted Pair
- "Fast Ethernet"
- Two pair
- Cat 5 minimum
- 100m max

### 1000BASE-T
-> 1GB/s Baseband Twisted Pair
- Gigabit Ethernet
- Four pair
- Cat 5 / 5e
- 100m max

### 10GBASE-T
-> 10GB/s Baseband Twisted Pair
- 4 pair
- Uses very high frequency (500 MHz compared to 125 for gigabit)
- Cat 6
	- Unshielded: 55m, Shielded: 100m
- Cat 6a
	- Both 100m

### 40GBASE-T
-> 40GB/s Baseband Twisted Pair
- 4 Pair
- Cat 8
- 30m

### 100BASE-FX
-> 100mb/s Baseband Fiber Optic
- Multimode Fiber, but uses laser -> more expensive
- 2 km

### 100BASE-SX
-> 100mb/s Baseband Fiber Optic (LED)
- Multimode, but uses LED -> less expensive
- 300m

### 1000BASE-SX
-> 1GB/s BaseBand Fiber Optic (Short Laser)
- Uses shorter wavelength laser, usually multimode
- 220 - 550m

### 1000BASE-LX
-> 1GB/s Baseband Fiber Optic (Long Laser)
- Uses longer wavelength laser,
	- Multimode: 550m
	- Singlemode: 5km

### 10GBASE-SR
-> 10GB/s Baseband Fiber Optic (Short Range)
- Multimode
- 26 - 400m

### 10GBASE-LR
-> 10GB/s Baseband Fiber Optic (Long Range)
- Singlemode
- 10km

## Transceivers
-> Layer 1 signal converter
ex: fiber to copper
- almost always powered
- Transmitter + Receiver

**Bi-Directional** - usually, you would need two transceivers for bidirectional conversion, but BiDi transceivers fixes this

### GBIC (GibaBit Interface Converter)

### SPF & SPF+ (Small Form-factor Pluggable)
- SPF - 1GB/s
- SPF+ - 16GB/s (supports Gigabit)

### 40G QSFP & QSFP+ (Quad Small Form-factor Pluggable)
- 4 channel, 4 x 1GB/s
- QSFP+ = 4 x 10GB/s

# Wifi
## 2.4 GHz
- Better indoor range, b/c signal penetrates through most obstacles
- Limited number of channels
- High probability of interference, b/c more commonly used

## 5 GHz
- Supports more channels, 
- Higher transmission rate
- Less interferance
- Limited range, b/c doesn't penetrate obstacles

## 802.11
-> IEEE standard for CSMA/CA, the media access stanadard of wireless communication

### 802.11a (not seen today)
- one of the first 802 standards (1999)
- 5˝GHz -> shorter range than 802.11b
- 54mb/s

### 802.11b (not seen today)
- one of the first, 1999
- 2.4GHz -> better range than 802.11a, but more interference
- 11mb/s

### 802.11g
- (2003) upgrade to 802.11b, backwards compatible w/ 802.11b
- 2.4GHz
- 54mb/s

### 802.11n (Wifi-4)
- (2009) upgrade to 802.11a&b&g
- 5 & 2.4 GHz
- larger channel width -> can transmit more data at a time
- uses **MIMO** (Multiple Input Multiple Output) - using multiple antennas
- 150mb/s x 4 -> 600mb/s

### 802.11ac (WIFI5)
- (2014) upgrade to 802.11n
- 5GHz
- Allows signal bonding & Denser signal modulation -> increased transmission rates 
- 867mb/s x 8 -> 6.9Gb/s

### 802.11ax (WIFI6)
- (2021) upgrade to Wifi5
- 5 & 2.4 GHz
- 1201 mb/s per channel x 8 -> 9.6 GB/s

# Other Wireless Tech
## Z-Wave
-> low energy, used for communication btween smart devices

## ANT+
-> for health devices

## Bluetooth
-> range of 10m
- but vulnerable, **bluesnarfing** (stealing info) **bluejacking** (brute force hacking)

## RFID (Raidio Frequency Identification)
-> **active** RFID has built in power, **passive** RFID requires power input

# Antennas
**Omnidirectional** - all directions equally
**Directional** - one direction concentrated

# Wireless Security
## WEP (Wired Equivalent Privacy)
-> very first wireless security standard

- Shared authentication passwords
- Weak initialisation vector (random number that obfuscates the encryption algorithm, for a stream cipher)
- RC-4 algorithm (**Steam Cipher** - encryption one bit at a type) -> fast, but vulnerable

## WPA (Wifi Protected Access)
- Stronger Initialisation Vector
- Still used RC-4
- TKIP (Temporal Key Integrity Protocol) - every packet had a 128 bit encryption key + hashing
- Backwards compatible w/ WEP

## WPA2
- CCMP (replaced TKIP) - **Block Cipher** (sending data in blocks)
	- AES (Advanced Encryption Standard) -> slower, but far stronger
	- Message Integrity Check
- Might be succeptible to Brute force attack, by deriving cryptographic hash from a captured four way handshake between the client and the WAP
- Not backwards compatible

## WPA3
- GCMP - stronger encryption than CCMP
	- AES
	- MIC
	- GMAC (Galios Message Authentication Code)
- Uses SAE (Simultaneous Authentication of Equals), a *Diffie-Hellman* key exchange to prevent such brute force attack

# Wireless Attacks
## Rouge Access Point
-> the connection of a unauthorised WAP to a network
- if not properly secured, can open network up to malicious devices
- can be prevented by using RADIUS / 802.1x or setting security policies
- Not a cyberattack on it's own

## Evil Twin Attack
-> a malicious Rogue Access Point with a deceptively similar SSID, type of man-in-the middle attack, *'wireless phishing'*
- can be combined with deauth attack
- 'One step up' from Rogue Access Point, turns into cyberattack

## How to Defend...?
- constantly scan for Rougue Access points
- Use VPNs on public networks
- Use RADIUS / 802.1x

## NDES (Network Device Enrolment Support)
-> uses certificates issued to legitimate network devices to prevent Evil Twin Attacks

# Network Devices
## Hubs
-> *'multi-port repeater'*, Layer 1 device that replicates signal out to all ports
- deprecated b/c inefficient & sniffers can sniff all packets

## Switch
-> Layer 2 device that uses MAC adressing to direct frames
- Uses ASIC chip (uses hardware to direct traffic)

## Bridges
-> like a Switch with 2-4 ports, connects two physical networks

## Router
-> Layer 3 device that routes traffic between IP networks or subnets, connects networks 
- Uses software to direct packets
- Isolates broadcast traffic

## MLS (Multi-Layer Switch)
-> switch + router

# VLANs (Virtual Local Area Networks)
-> a broadcast domain that is partitioned from a LAN, *at the data link layer*
- layer 2 or MLS can implement VLANs

## VLAN Tagging / Trunking
-> Problem arises, b/c we don't have a port for connecting to other devices
**Trunk Port** - "VLAN Neutral" port for connecting to other network devices
**VLAN Tag** - info added to a frame containing the VLAN it originates from

## Port Mirroring
-> method of monitoring network traffic, sending copies of packets going to one port to another
- usually used to forward traffic to IDS/IPS or a sniffer

## CAM (Content Addressable Memory) Table
-> maps MAC addresses to ports on switches
- MAC flooding can jeopardise
- Without a CAM table, a switch would act like a hub, b/c it doesn't know which devices are connected to which ports

## STP (Spanning Tree Protocol)
-> IEEE 802.1D, prevents *logical loops* in networks with *redundant switches*
- without STP, broadcasts will loop around endlessly, causing "broadcast storms" + possible MAC address corruption

## Switch Security Measures
### DHCP Snooping
-> a security feature in swiches, that acts like a *"DHCP Firewall"*, blocking DHCP Offers from invalid DHCP servers

**DHCP Spoofing** is a attack where the attacker attempts to respond to a DHCP request, and set itself as the *Default Gateway* -> possibility for snooping or Man-In-the-Middle Attack

DHCP uses DORA (Discover Offer Request Acknowledge)
- Victim sends Discover to all devices
- Attacker recieves Discover message, sends forged Offer
- Request (victim) & Ack (attacker)

### Flood Guards
-> security feature implemented in switches, that prevents against Denial Of Service attacks
- Ex: UDP, TCP, SYN, MAC floods
- Looks for unusual amount of traffic

### Root Guard
-> Prevents root bridge (in [[#STP Spanning Tree Protocol]]) from being changed without admin permission

### BPDU (Bridge Protocol Data Unit) Guard
**BPDU** is the data unit for the [[#STP Spanning Tree Protocol]]
-> prevents BPDUs from being sent from *non-trunk ports*
- otherwise, this could cause bridging loops or incorrect STP info

# Routing
-> selecting the path that packets will take across networks

**Static Routing** - form of routing when the router uses a manually configured route, instead of a dynamically configured one
- Often manually entered into the device's routing table (`Route -add`)

## Distance Vector Routing
-> makes a decision based on *"how many hops away"*, does not care about length of each hop
**RIP** (Routing Information Protocol) - Distance Vector Routing protcol, currently v2
**Routing by Rumor** - RIP uses this, routers 'learn' paths by talking to each other
- Routers can only talk to others directly connected to them
- ex: A - B - C
- If B is 1 hop away from C, A knows that it is 2 hops away from C
! however, this can cause something called *Count to Infinity*

**Count to Infinity** - a error when a connection between two routers goes down, and because of this nearby routers continuously increment their distance vectors
- ex: A - B -x- C
- A knows it is 2 hops away from C, B knows it is 1 hop away
- When A goes down, B asks C for it's distance vector to C
- A tells B (2 hops), B sets it's own to 3
- A can't connect to C, asks B, sets it's own to 4
- etc...

*Poison Reverse* - a way to prevent *Count to Infinity*, 
- routers set it's maximum Distance Vector to 16, 
- during Çount to Infinity, once a device gets to 16, it understands that there is a downed link
- That device then sends it's distance vector back, telling other devices that there is a downed link

**Split Horizon** - prevents *Count to Infinity*, by never sending routing information back to a interface that it recieved routing info from


## Link State Routing
**OSPF** (Open Shortest Path First) - most common Link State Routing Protocol
- each router creates it's own *topology table*, learns network *on it's own*
- every router directly communicates with every other router, via **LSA** (Link State Advertisements), which constantly check if the connection is active
- if a LSA does not reach a router, it marks the link as down
! very resource intensive, designed for larger networks with more capable routers

## Exterior Gateway Protocols
**BGP** (Border Gateway Protocol) - main routing protocol for the internet
- Routing on the internet is performed by *ASes* (Autonomous Systems)
- Again, periodically tests for active connections

# NAT (Network Address Translation)
-> processing of mapping a internal IP address to a public one, or vice versa
- typically done by router / default gateway

## PAT (Port Address Translation) / Overload NAT
- Allows a *one to many* relationship, via the use of ports
- NAT device assigns a specific port to a node connected on the internal network
- PAT is a subset of NAT

## Dynamic NAT
-> one to one relationship, a single device is connected to a NAT device

## Static NAT
-> requires user to manually set up NAT table

# Firewalls
-> security device that monitors and controls incoming & outgoing traffic, based on predefined rules
- Can be either software or hardware based

## Layer 3 (Network) Firewall
- Static Packet Filtering, examines source & destination IP & Port + protocol (TCP, UDP, etc)
- essentially just a router w/ access control rules, fast but very basic

## Circuit Level Gateway (Layer 4 - Transport)
-> firewall that inspects TCP & UDP packets

## Layer 5 (Session)
- Stateful Filtering, understands the *state of the connection* (ex: who initiated)
- Can prevent unsolicited replies (ex: DNS reply without a request)

## Layer 7 (Application)
- Application Proxies / Firewalls / Proxies
- **Deep Packet Inspection** - inspecting both the header & payload of a packet
- -> can inspect certificates, content, time, etc
- **Forward Proxy** - inspects outgoing traffic
- **Reverse Proxy** - inspects incoming traffic

### WAF (Web Application Firewall)
-> L7 Firewall that focuses on http and https traffic
- ex: XSS (Cross Site Scripting), Injection Attacks, etc

## Next-Gen
-> Firewalls that combine traditional firewalls with additional features such as...
- Deep Packet Inspection
- Intrusion Prevention Systems
- TLS/SSL certificate inspection
- QoS / Bandwidth inspection
- Antivirus

## Security Zones
-> A Network is often segmented into different security zones...
- Untrusted (ex: internet)
- Trusted (LAN)
- **DMZ** (Screened, semi trusted) - aka a "perimeter" network contains external-facing resources that are open to the (untrusted) internet
	- Such resources are ones that should be accessed from untrusted hosts, ex: email, web servers
	- Often monitored for malicious activity, acts like a "buffer zone"

## Best Practices
- Block un-necessary ICMP (Ping) packets -> can prevent ping based DOS
- Keep ACLS (Access Control Lists) simple
- Implicit Deny -> blocking traffic by default, using a whitelist
- Ingress + Egress filtering (Emphasis on egress), because a attack will almost always feature outbound traffic
- Log, Log, Log
- Drop fragmented packets


# IDS (Intrusion Detection Systems)
-> passive tool, *identifies, logs, and alerts admins of* suspicious activity

**Analysis Engine** - analyses data collected by a sensor
**Signature Database** - contains signatures of known attacks
- Pattern Matching - most attacks have distinct "signatures" or Indicators of Compromise
- Profile Matching - aka behavioural matching, uses AI or complex algorithms to detect *anomalies*, ex: amount of traffic, specific requests / packets, etc

## HIDS (Host-based IDS)
-> software IDS, monitors activities on the system it is installed on 
- ex: launched processes, system log files, script execution, 

## NIDS (Network-based IDS)
-> Sniffer + Analysis Engine = NIDS
- Examines a network (or a subnet)
- Network card set to promiscuous -> captures all packets

# IPS (Intrusion Prevention Systems)
-> active tool, designed to stop a attack
- ex: sending TCP `[.R]` (Reset) flags, modifying firewall settings

# Honeypots
-> a intentionally placed vulnerable system (usually in the DMZ) intended to shift the focus of attackers away from the actual network

# SIEMs (Security Information and Event Managers)
-> a centralised security solution that collects logs and event data from devices, and turns it into actionable information
- SIEMs can help organisations perform Threat Intelligence, Incident Response, Forensics, etc
- Modern SIEMs feature UEBA and SOAR

**UEBA** (User and Entity Behaviour Analytics) - Gathers analytics on baseline activity, thus helping to identify abnormal activity

**SOAR** (Security Orchestration, Automation and Response) - Automates response to security incidents


# UTM (Unified Threat Management) Systems
-> a device that combines many security features into one, ex: a router = WAP + Firewall + Switch

# Load Balancers
-> devices that distribute the flow of packets, by balancing out traffic to each node connected to the load balancer

**Traffic Shaping** - a bandwidth management technique that delays less important packets to increase QoS for priority services


# WAN Communications
## Circuit Switched Network
-> a physical path is dedicated for each connection
- Connection oriented -> more reliable, more costly, slower
- each data unit know the full path that it will take
- POTS (Plain Old Telephone System) networks are circuit switched

## Packet Switched
-> breaks data into individual packets
- connectionless -> less reliable, less costly, faster
- no physical path between source and destination
- each data unit only knows it's final destination, routers in between decide where to forward the packet 
- IP networks, WAN, LAN uses circuit switching
### VOIP (Voice Over IP)
-> way of delivering voice communications over IP networks instead of traditional Circuit Switched networks
- Uses RTP (Real-time Transfer Protocol)

## Multi-Protocol Labeled Switching
-> routing traffic based on "labels" instead of network addresses
- determines the *entire path* of a packet, *at the first router the packet reaches*, and puts the info into the label
	- **LSR** (Label Switch Router)s can label data packets
	- **LSP** (Label Switching Path) is the path that a packet will take
	- **LER** (Label Edge Router) is the final router the packet will pass through, and strips the packet of it's label
- Works over almost all protocols IP, Ethernet, Frame Relay
- more efficient, because the routing decision only has to be made once
- costly, hardware can be expensive

## Demarcation Point
-> point where WAN network ends, and connects to LAN
**Smart Jack** - a (new) device that allows the WAN provider to diagnose & reconfigure the Demarc point
