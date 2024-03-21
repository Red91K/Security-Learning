# IPv4 Basics
## IP Addressing
-> 32-bit address for both networks and hosts
- called *'logical addressing'* because your IP can change 
- subnet masks determine local vs remote traffic
- each IP will have a Network ID and Host ID

### Network ID
-> Address with *Host portion bits all set to 0*
- Not assigned to any device, references an entire network
ex: 192.168.0.0

## Classful Subnet Masks
-> Subnet Masks allow us to distinguish between the Network portion & Host portion of the IP address

IP Class | Subnet Mask | Ip Range | Description
------------- | --------------- | --------------------|------------
A | 255.0.0.0 | 1.0.0.0 - 127.255.255.255 | ISP / Huge networks
B | 255.255.0.0 | 128.0.0.0 - 191.255.255.255 | Big networks
C | 255.255.255.0 | 192.0.0.0 to 223.255.255.255 | Small networks

ex: (Class C) 192.168.0.33
Network - 192.168.0.0
Host - .33

## Binary Addressing
Example Number | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1
------------- | ---- | -- | -- | -- | -- | -- | -- | -- 
156 | 1 | 0 | 0 | 1 | 1 | 1 | 0 | 0
192 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0
255 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1

-> 255 isn't a special number in subnet masks, it is simply all the binary bits being 1s 

## Remote Addressing
-> nodes use subnet mask to identify remote traffic
-> nodes forward remote traffic to default gateway (router)
-> router then forwards packet to remote network

## Unicasting
-> *one to one*
-> Typical, Node to Node communication
- can be routed through internet

## Multicasting
-> *one to many*
-> Sends the same packet to multicast clients in a multicast group
- clients use a special program to subscribe to a multicast group

## Broadcasting
-> *one to all*
-> sends the same packet to all hosts on a network
!! to create a broadcast, fill the *host portion with 1s*
ex: 255.255.255.255 / 192.168.0.255

# Special Purpose Addresses
## RFC 1918
-> reserved for private, internal use only
- Used behind a NAT router
- 10.x.x.x
- 192.168.x.x
- (rare) 172.16.x.x - 172.31.x.x 

## Loopback (Localhost)
127.0.0.1

## APIPA (Automatic Private IP Addressing)
169.254.x.x
-> automatically obtains a Private IP starting with 169.254 if DHCP server is unresponsive / no more IP addresses
a APIPA address only works for LAN communications

# CIDR (Classless Inter Domain Routing)

## Subnetting
*Why do we subnet*
-> to isolate networks into broadcast domains
-> to ease administration
-> create different security domains
-> differentiate QoS

## classless subnetting
- classfull addressing is too all or nothing
-> we can 'borrow' bits one by one

ex: original classful mask of 255.0.0.0 (11111111.00000000.00000000)
we steal one bit -> (11111111.10000000.0000)
-> 255.128.0.0

we steal one more bit -> (11111111.10000000.00000000)
-> 255.192.0.0

!! for each x number of bits borrowed, you create 2^x subnets

Bits Borrowed | Binary representation | Decimal | Subnet #
------------- | ---- | -- | -- 
1 | 10000000 | 128 | 2
2 | 11000000 | 192 | 4
3 | 11100000 | 224 | 8
4 | 11110000 | 240 | 16
5 | 11111000 | 248 | 32
6 | 11111100 | 252 | 64
7 | 11111110 | 254 | 128
8 | 11111111 | 255 | 256

## allocating IP addresses
256 / total number of subnets created = increment

However, first IP is for the default gateway, last is a broadcast address

## VLSM (Variable Length Subnet Masking)
-> allows each subnet to have it's own subnet mask


# IPv6
-> 128 bit hexadecimal, separated by ':' s
-> 340 trillion trillion trillion addresses

- can replace consecutive zeroes with ::,
	- ex: 2001:OD88:AC10:FE01:0000:0000:0000:0000 -> 2001:OD88:AC10:FE01::
	- But, it can only be done once, & they have to be consecutive

- loopback / localhost - 0:0:0:0:0:0:0:1 or ::1
- Link-Local (IPv6's APIPA) - FE80
- Unique Local (Internal Private IP address) - FC00 or FD00
- FF - multicast
!! IPv6 does not have broadcast

## Why IPv6?
- Built in security (IPSec was created as part of IPv6)
- Larger Address Space
- Auto-configuration of addresses

## Dual-Stack
-> hosts that run both IPv4 & v6, and can communicate with devices with either protocol

**ISTAP** (Intra-Site Automatic Tunnel Addressing Protocol) routers are designed for a *dual stack enviornment*
-> translates IPv6 packet to IPv4

## Tunneling
### 6 to 4
-> used to pass IPv6 traffic across the IPv4 internet
- IPv6 packets are encapsulated inside v4 packets
- Packets are then routed to their destination as v4 packets, and are decapsulated
! Destination IPv4 address has to be public, not behind NAT

## Teredo (Microsoft) & Miredo (Open-Source)
-> IPv4 UDP tunneling of IPv6 packets, over port 3544
! can tunnel through NAT

## GRE (Generic Route Encapsulation)
-> GRE tunnels allow packets to traverse incompatible networks
-> creates a point-to-point tunnel

## 4 to 6
-> tunnels v4 traffic over v6 network
! not really used right now, because v6 is not that popular
