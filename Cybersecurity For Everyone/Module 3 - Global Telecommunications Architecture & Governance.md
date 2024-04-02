
# Summary
- The Internet is a **broad set of interconnected networks** that exchange information using a shared set of communication protocols
- **encapsulation** accounts for the variety of communication protocols in use, by allowing us to send data in one protocol over another protocol. 
- the **OSI Model** is a conceptual model describing data transfer. Information (headers & protocol data) is added as we go **down** the model.

| Protocol     | Description                                                                           | Examples                             |
| ------------ | ------------------------------------------------------------------------------------- | ------------------------------------ |
| Application  | Presents Data to the User (below the actual "application")                            | HTTP, DNS                            |
| Presentation | Formats Data for Application Layer                                                    | encryption, decryption, translation  |
| Session      | Opens, Maintains, Closes end-2-end connections                                        | Web Sockets                          |
| Transport    | Ensures Timely & Accurate end-2-end communication, inter-network flow & error control | TCP, UDP                             |
| Network      | Facilitates Inter-Network communication, routing & addressing                         | IP, BGP                              |
| Data Link    | Facilitates Intra-Network communication, intra-network flow & error control           | 802.11, 802.3                        |
| Physical     | Bits transferred over physical medium                                                 | Wires, Cables, Terrestrial Microwave |
- Governance is the human **process of managing various technical, informational, and operational issues**
- Governing the Internet involves **various approaches, stakeholders, and levels of governance**, like.....
	- specific technical standards (NIST 800-53, PCI DSS) vs high level strategies (executive orders, National Cyber Strategy)
	- protecting buisnesses from cyberattacks vs protecting individual citizens from violations of privacy
	- laws and regulations at the national level (GDPR, HIPAA, FTCA) vs policies within an organization
- Effective governance is necessary because of the increasing importance of information technology in our world. 


# L1 - How Data Moves: Encapsulation
- Internet is a broad set of interconnected networks
- WWW sits on top of the internet

## Encapsulation
- ability for devices to communicate require protocols - shared instructions that tell nodes how to communicate
- ex: (Application instructions)/(Routing instructions)/(Physical Medium instructions)
- Such instructions are encapsulated - nested within each other

## OSI Model
-> conceptual model describing data transfer regardless of the underlying technology
- headers added as we go down the OSI model
- Information added as data goes down the OSI model, transported over layer 1, then unpacked up the OSI model
- vulnerabilities at each layer are exploited by hackers

[Cloudflare's OSI Model](https://www.cloudflare.com/en-gb/learning/ddos/glossary/open-systems-interconnection-model-osi/)

| Protocol | Description | Examples|
| -------- | ----------- | -------| 
| Application | Presents Data to the User (! does not include actual application, but protocols & data manipulation below application) | HTTP, DNS|
| Presentation | Formats Data for Application Layer | encryption, decryption, *translation* - changing data format, ex: CSV into json |
| Session | Opens, Maintains, Closes end-2-end connections| Web Sockets | 
| Transport | Ensures Timely & Accurate end-2-end communication, inter-network flow & error control| TCP, UDP|  
| Network | Facilitates Inter-Network communication, routing & addressing | IP, BGP | 
| Data Link | Facilitates Intra-Network communication, intra-network flow & error control| 802.11, 802.3 |
| Physical| Bits transferred over physical medium| Wires, Cables |


# L2 - How Data Moves: Application Layer
- Application layer acts as an interface between the application and 
	- the network you want to communicate on
	- the human viewing the application

## Ex: DNS
-> Phonebook of the internet
- computer translates a human-readable web address to a IP address

## Hierarchy of DNS
PC -> Local DNS
local DNS <-> root DNS 
- (has list of TLD server addresses)
local DNS <-> TLD DNS
- TLD - ex: .com, directs to specific AN server
local DNS <-> AN (Authoritative Name) server
- AN server has all info about a domain
Local DNS -> PC

# L3 - How Data Moves: Network Layer
*Network layer* - routing information between independent networks

## Where to go?
-> IP Address
- Internet Protocol assembles data into a packet, with a address header

## How to get there?
- Thousands of networks are grouped into ASes (Autonomous Systems)
- ASes are managed by large organisations that manage thousands of IP addresses, ex: ATNT, Sprint

- Intra ASes, data is transferred via IP
- inter ASes, data is routed via *BGP* - Border Gateway Protocol
	- ASes are connected to a few other ASes
	- BGP routers continuously monitor ASes that it is connected to
	- BGP routers obtain best route to destination AS, encapsulates & sends packet

## Security Considerations
-> BGP operates in trusting that ASNs will honestly report routes, 
- If a AS incorrectly reports routes, users could be redirected to malicious websites / completely blocked from accessing web content
	- ex: 2008, Pakistani ISP advertised false BGP routes to youtube's ASN, youtube was inaccessible for hours

# L4 - How Data Moves: Physical Layer
## Summary
-> Various technologies use electromagnetic signals to transmit logical data
- Fibre optics link long distances, TM used for point-to-point, Satelites move data over radio waves
- Such physical networks converge at IXPs

## Electromagnetic Spectrum
- 3 technologies that utilise Electromagnetic Spectrum to transmit logical data over physical medium

### Fibre Optic
-> leverage visible light to transmit data
-> the presence of light == 1, absence == 0
- Vast majority of international communications passes over Fibre Optic
- Fibre Optic laid underseas

### Terrestrial Microwave
-> uses directed microwaves to transmit data
- Series of repeaters move energy across territory
- Uses Point-to-Point transmission, therefore repeaters have to be within line of sight

### Satelite Technology
-> Satelites use radio waves to send signals to antennas on Earth, Ground Stations transmit & receive radio waves

## Intersection
- But, these different physical mediums have to be connected somewhere
- Physical infrastructure converge @ *Internet Exchange Points* 
- This provides the physical connections for AS peering relationships

# L5 - What is Governance?
## Summary
-> Governance is the process of managing various technical, informational, and operational issues
-> cyber is a young, volatile field

## Governance 
- We need human processes to manage the myriad of technical, informational, and operational issues surrounding our use of technology
ex: How should private use of technology be regulated? Should this technology used offensively? 
-> Governance is the process by which we manage the technical, informational, and operational issues that arise

- managing something as large as the internet requires governance structures
ex: what cyber activity is permissable?
- Multiple stakeholders are involved in this process - private & public institutions, citizens & governments, etc

## [2014 The Regime Complex for Managing Global Cyber Activities](https://www.cigionline.org/sites/default/files/gcig_paper_no1.pdf)
- Major issues in cyber governance:
	- ECrime - now a significant economic & social concern
	- Espionage - should regulations be set regarding cyberespionage?
	- Censorship - Is unrestricted access to the internet a human right?
	- Privacy / Surveliance

- Cyber is a very new and volatile field
- Cyber has really increased in importance - not just a buzzword:
	- in 2014, cybercrime cost $80 billion annually - "States may think that costs are not high enough to merit action"
	- Today, cybercrime costs $8 trillion - every 3 days cyber crime costs $80 billion
- Stuxnet happened a long time ago, imagine the capabilities of today's threat actors & especially APTs

# L6 - Governing the Internet
## Summary
-> governance of internet takes place across several topics, several levels, and several entities
- Technical Governance - standards for technical implementations
- Data Security / Privacy
- Critical Infrastructure
- International Relations


## Technical Governance
- Governance for even a single technology can be challenging, because of interconnections to other technologies
ex: Car in a Smart City
- encrypt or not transmissions?
- send on what frequency?
- store data where?
- what is private data?

## Managing Technical Structures
-> we need institutions & processes managing...
- research & engineering requirements
- each parts of the technology stack
ex: 
- W3C (WWW Consortium) - provides open platform for the public to manage standards of web development
- ICANN - manages processes for internet domain names
- IAB (Internet Architecture Board) - long-term technical direction for internet development, through RFCs
- IETF - short-term immediate needs of internet develpoment

## Information Security
-> governing the protection of information is a completely different challenge
 - Many different standards for protected information
	 - ex: Geolocation, health information, usernames, etc
- Industry standards - ex: HIPAA
- State-level standards - MPIPA
- Nation-level standards - GDPR

## Critical Infrastructure
-> some internet systems are so critical to society that we need to specifically govern them
- challenge, b/c much of such systems are owned by private enterprises

## International Relations
-> extending governance to international actions
- ex: offensive use of cyber, content filters, etc
