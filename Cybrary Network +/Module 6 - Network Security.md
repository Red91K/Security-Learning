# Physical Security
**CCTV** (Closed Circuit Television) - often a set of cameras that are networked to a single host
**Asset Tracking Tags** -  allows companies to better track inventory, ex: barcode
**Tamper Prevention** - ways of knowing if a device has been tampered with, ex: Syslog
**Employee Training** - often the best security measure,  to identify common effects

**Prevention / Deterrence** - ex: Motion Detection, Access Control Hardware
**Detection / Correction** - ex: CCTV, Tamper Detection

# Authentication
-> method proving that a identity is true

## "Types" of Authentication
**Type 1** - Something you know
- Passwords, Passphrases, Cognitive Passwords
**Type 2** - Something you have
- **Memory Cards** - compact storage device that holds unencryptecd information, ! very easy to copy & fool -> PIN needs to be used 
- **Smart Cards** - more secure version of memory cards, used in modern credit cards, via generating a one time code
- Hardware Key, Digital Certificate, Cookies
**Type 3** - Something you are; Biometrics
- Physiological - fingerprint, iris, face, etc
- Somewhere you are - gps
- Something you do - swipe pattern, typing speed, etc
! concerns: user acceptance, time for enrolment, no way to change if leaked


## Authentication Errors
**Type 1** - False Rejection
**Type 2** - False Acceptance
-> as Type 1 goes down, Type 2 goes up, and vice versa
! where they meet on a graph is the **CER** (Crossover Error Rate) - lower is better
- iris scans have the lowest CER (in type 3)


! The strongest authentication is *Multi-Factor*, combining at least two types
! **Mutual Authentication** (two parties proving their identity to each other) is also desirable

## NAC (Network Access Control)
-> approach to network security, combines user authentication w/ endpoint security policies
-> checks a computer's *"health"*, ex: antivirus software, firewall, OS version, etc
-> only authenticates if requirements are met, or can redirect to a different subnet

# Single Sign On
-> allowing users to authenticate to a central authentication server, so that they recieve access to multiple unique systems

## Pros
- Convenient for end users
- Centralised Control -> easy to administer

## Cons
- Single point of failure

## Kerberos
-> network authentication protocol & service, designated to operate in unsecure network
- Uses symmetric key encryption
- Needs a **KDC** (Key Distribution Center)
	- Authentication Server
	- Ticket Granting Server
### Concerns: 
- Clocks must be synchronized within 5 mins of each other
- Single point of failure (the KDC)
- Vulnerable to brute force attacks

### *"Carnival"* Analogy
- First, you get a wristband @ the entrance to the carnival (you only need to do this once)
- From then on, you need to show the ticket booth your wristwatch to buy a ticket
- You need to show each ride the corresponding ticket to ride it

## Federated Services
- If we want to use single sign on beyond our local domain, we need to use Federated Services
-> trusts that are preconfigured so that authentication credentials can be passed back and forth

### SAML (Security Association Markup Language)
-> language & protocol for transferring identity data between two parties, used for SSO (Single Sign On) for web applications
- User tries to access **Service Provider** (ex: Web Application), redirected to **Identity Provider**
- User authenticates to **IdP**, receives SAML *token*
- User sends token to **SP**, **SP** validates token
- SP sends data
! with web applications, the SAML token is often stored inside session cookies

### OpenID Connect
-> takes some weight off the client browser, more procecssing by Relying Party & OpenID provider

### Oauth 2.0
-> framework that is part of OpenID, provides delegation of permissions to applications
- Goal is to increase *usability* & *interoperability*
ex: do you allow Grammarly to view your gmail?

# Network Attacks
## DOS (Denial of Service) attack
-> a volumetric attack, where the attacker attempts to overwhelm a system with a large volume of traffic
- DDOS - distributed DOS, many devices (often hijaked) performing DOS attacks
ex: ping flood, SYN flood

## Social Engineering
-> attack vector that relies heavily on human interaction, manipulating people into breaking security policies
ex: Phising, spear phishing (targeted to one person), whaling (targeted to high profile), vishing (voice phishing), smishing (sms), SPAM Mail

## Insider Threat
-> a attack vector created by a person working within the organisation (either with malintent or not)
ex: someone forgetting to lock a door

## War Driving
-> attempting to find unsecure networks, and then steal data / use it to transport malicious traffic

## Logic Bombs
-> type of malware, executed only when a logical statement is met
- can be used to evade sandbox detection

## Ransomware
-> encrypting important files and requiring a ransom

## DNS Attacks
-> attacks targeting the availability of a DNS service
- there are so many attacks on DNS because it is essential to a network
- **DNS DOS** - a simple denial of service on a DNS server can take down so many services that require DNS
- **DNS Spoofing** - intercepting a DNS request and returning a fake DNS record (MITM attack)
- **DNS Pharming**  using DNS spoofing or poisoning to redirect users to malicious servers
- **DNS Poisoning** - where a DNS *resolver's cache* is *poisoned* with a false entry (ex: via a unsolicited DNS reply)

## ARP Poisoning
-> poisoning the ARP cache of the target computer, often via a unsolicited reply
! modern OS is protected against unsolicited replies

## Spoofing
-> falsifying identify in order to gain unauthorised access, ex: MAC addr, Email, IP addr
- "technical" social enginnering

## Brute Force
-> systematically checking all possible passwords until it is found
**Dictionary Attacks** - brute force attack with a dictionary of common characters

## VLAN Hopping
-> gaining access to other VLANS, defeats the purpose of network segmentation -> can access unauthorised resources

## MITM (Man In the Middle)
-> "active eavesdropping", where the attacker acts like a proxy

# Risk Management
-> identifying, assessing and controlling threats to a organisation
## Access Controls
-> "technical controls"
-> ways to minimise the damage a attacker can inflict, by restricting who can view and use resources

### Network Segmentation
-> architectural approach that divides a network into subnets or VLANs, thus separating untrusted entities from trusted resources

### Hashing
-> a function that maps arbitrarily long data into a fixed length string
-> used to ensure *data integrity*

### Digital Signature
-> a hash encrypted with a private key, ensures *non repudiation* (can't dispute integrity)

### Access Control Lists
-> list of rules that specify the requirements for a user to access a resource

## Administration Controls
-> "Human controls", training, procedure and policy that lessens the impact of threats for individuals
ex: separation of duties, on & off boarding procedures, auditing, training, etc

# Penetration Testing
-> performing a simulated cyber attack against a device or a network

audit - test compliance
vulnerability analysis - tests weaknesses
pentesting - tests if you can withstand a attack
