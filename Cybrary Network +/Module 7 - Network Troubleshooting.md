# Troubleshooting Process
## Identify the Problem
- Gather information (when, where, upon what condition)
- Try to duplicate the problem, narrow down possible causes
- Question Users 
- Document progress

## Establish a Theory
- Isolate the root cause - your "theory"
- Go Top Down or Bottom up of OSI model
ex: can you ping device? -> can you connect via tcp? -> 

## Test the Theory
- test if the theory is correct, and resolve the problem
- repeat if incorrect

# Hardware Tools
## Crimper
-> tool that deforms one end of a wire to create a connection, ex: forces copper into RJ45 format
![](https://images.thdstatic.com/productImages/1a450d0b-0b92-4372-a47f-9c90428e535b/svn/klein-tools-crimpers-vdv226011sen-64_1000.jpg)

## Cable Tester
-> tests cable connectivity
![](https://media.cablematic.com/__sized__/images_1000/ct00600-01-thumbnail-1080x1080-70.jpg)

## Punchdown Tool
-> used for inserting wires into connectors, and other actions where a impact is needed
![](https://m.media-amazon.com/images/I/71i9F8H37TL._AC_SL1500_.jpg)

## OTDR (Optical Time Domain Reflector)
-> sends out a signal to detect the *location of a break* in a optical fibre cable
![](https://upload.wikimedia.org/wikipedia/commons/0/08/OTDR_-_Yokogawa_AQ7270_-_1.jpg)

## Tone Generator
-> identify and trace wires, useful in congested cable bundles
![](data:image/jpeg;base64,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)

## Loopback Adapter
-> a dummy NIC used as a testing tool for virtual network enviorments

![](https://cdn-reichelt.de/bilder/web/xxl_ws/E910/DELOCK_86931_01.png)

## Multimeter
-> device that can take multiple electronic measurements (ex: voltage, resistance, etc)
![](http://dam-assets.fluke.com/s3fs-public/flukeig/products/images/dmm/jpeg/27ii_300dpi_256x356mm_c_nr-9197-1500x1000.jpg)

## Spectrum Analyser
-> displays signal strength in relation to frequency range
![](https://kr.element14.com/productimages/large/en_GB/3107580-40.jpg)


# Software Tools
## Packet Sniffer
-> application on a device with a NIC set to promiscuous mode, *monitors network traffic*

## Wifi Analyser
-> discovers nearby *wireless APs* and their signal strengh

## Port Scanner
-> software that scans a target device for open ports

## Bandwidth Speed Tester
-> measures connection speed + bandwidth


# Command Line Tools
## Ping
-> tests physical connectivity
pathping returns the route that the packet takes

## Traceroute
-> tracing packets from source to destination (traces router hops)
Tracert for Windows, Traceroute for Mac/Linux

## Nslookup & Dig
-> DNS utilities, DIg for Linux Nslookup for Mac

## Ipconfig (windows) Ifconfig (Linux/Mac)
-> displays TCP / IP configurations, can send DHCP request, flush DNS, etc

## IpTables
-> linux packet filtering / forwarding utility (like a host-based firewall)

## Netstat
-> displays active network connections, network statistics & routing table

## tcpdump
-> captures network packets

## nmap
-> port scanner, displays hosts & services on network

## route
-> displays + manipulates routing table

## arp
-> used to display arp cache

# Issues w/ Cable
## Attenuation
-> deterioration of signal over distance

## Latency / Jitter
Latency - fixed delay
Jitter - variable delay

## Crosstalk
-> EMI (ElectroMagnetic Interference) between adjacent copper wires
- twisted pair attempts to solve this by twisting wires

## EMI
-> signals interfering with each other, can cause data corruption
- even with shielding, devices are still succeptible

## Incorrect Pin Out / TX TR Mismatch
**TX / TR Mismatch** - when crossover cable is used with devices that should use straight through
-> make sure to use [[#Cable Tester]]s to verify correct cable connector type

## Improper Cable Type
ex: using a cat3 cable with a gigabit switch *'wastes'* the gigabit capacity of the switch

## Bad Port
-> check the lights on ports
- can be caused by [[#EMI]], ports are very susceptible to radiation

## Tranceiver Mismatch
**Tranceiver** (trans/re ceiver) - can transmit or receive radio signals using a antenna
-> make sure that we have the right transceiver type / enviornment

## Duplex Mismatch
-> when two devices end up with mismatched duplex settings

## Damaged Cables
-> constantly monitor

## Bent Pins
-> be careful w/ pins, go slowly when connecting

## Bottlenecks
-> serious amount of latency, due to overwhelming concentration of traffic into a device
likely suspects: firewall, proxies, routers

