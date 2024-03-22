# Network Diagrams

**Logical Diagram** - shows how data flows, less details

**Physical Diagram** - represents physical connectivity, far more detailed

**Rack Diagrams** - (Racks are steel shelving systems for network equipment), provides documentation for each appliance on the rack

**Network change management** - the process through which organizations standardize the way they implement network changes

**Network Configuration & Process Management** - identifying baselines for traffic and performance

**SOP / Work Instructions** - step-by-step instructions for performing a certain activity

# Policies & Best Practices
**Security Policy** - a continuously updated document containing everything about a organization's IT security
**Least Privilege** + **Need to Know** - give only the minimum priviledges & access to info
**Dual Control**  - policy requiring two or more devices / users to cooperate in order to gain access, prevents abuse / misuse
**M of N Control**  - protection measure that requires that a minimum number of agents (M) out of the total number of agents (N) work together to perform high-security tasks

## Limit Administrative Privileges
-> (root in linux, admin in windows / mac) 
- limit access to these accounts, and ensure that proper authentication is in place
- **Separation of Duties** - split administrative duties between different accounts 

## Password Policy
- Consider MFA (Multi-Factor Authentication), as well as alternate forms of authentication (ex: biometrics)
- Follow NIST Guidelines for passwords & authentication
- Have a robust password policy (guidelines on what a password should look like)
- Add duration between login attempts
- Increase password entropy

## On & Off Boarding
- On-Boarding - provide hardware, create credentials, sign NDAs, go over Acceptable Use Policy
- Off-Boarding - remove privileges / access

## Only use correctly licensed software

## Data Loss Prevention
-> preventing exfiltration of sensitive data
- preventing info such as SSN, credit card info, credentials, etc from leaving the network

## Personal Devices
-> leave a VLAN or subnet for personal, unsecured devices (guest network)
**POCE** (Personally Owned Corporate Enabled) - personal device that can be used on corporate network
**COPE** (Corporate Owned Personal Enabled) - personal devices that the company ownes

# Scanning, Monitoring, and Patching
## Event Management
-> a event is *any noticable change in state* of a network or a device, a event turns into a incident if it has *negative consequences*

## SNMP Monitors
-> often integrated into a SIEM, polls information from SNMP enabled devices
**MIB** (Management Information Base) - formatted txt file that specifies data types and privlidges for each unique OID (Object Identifier) / unique device

## Metrics
-> identify a baseline for different metrics, in order to identify unusual activity
- ex: Packet Drops, Bandwidth, Throughput, etc

## Log Reviewing
-> helps identify if a attack is happening / suspicious activity in general
- logs are often "protected" by hashes

## Patch Management
- document patches well, so that we can roll back to previous installations

## Packet / Traffic Analysis
- **Passive Analysis** - simply sniffing traffic
- **Active Analysis** - performing actions and listening for a change in traffic

# Fault Management
-> being able to withstand failures of one or more devices

**KPI** (Key Performance Indicator) - provides insights into the longevity of a component
**MTTF** (Mean Time To Fail) - average time before failure for non-reparable devices, essentially it's *lifespan*
**MTBF**  (Mean Time Before Failure) - average time before needing repair (repairable devices)
**MTTR** (Mean Time To Repair) - Average time for repair

**SLA** (Service Level Agreements) - legally binding contracts from vendors that guarantee the quality of services
- lays down metrics that will measure the quality of service, repercussions if metrics are not met

## Site Resiliency
**Hot Site** - essentially a *copy* of your datacenter infrastructure
**Warm Site** - in the middle, *Cold site + hardware*, but no software / data
**Cold Site** - a office / datacenter *space without any hardware*, only power & cooling

## RAID (Redundant Array of Independent Disks)
-> fault tolerance via redundant storage

### RAID 0
-> uses **disk striping** - distributing data over two hard disks
- no redundancy, 
- performance improvements for read/write

### RAID 1
-> disk mirroring, one backup disk (unused)
- redundancy
- least efficient, requires two identical copies

### RAID 5
-> disk striping w/ **parity** - a technique (similar to a checksum) to detect data corruption
! requires at least 3 disks, stores the sum of the values in two disks on the third
- Redundancy
- Slightly less efficient, b/c parity takes up a whole disk

### RAID 6
-> RAID 5 w/ two parity disks
= RAID 5 with parity in RAID 0
- even more Redundancy

### RAID 10 / 1+0
-> RAID 1 on top of RAID 0
- duplicated disks are striped

### RAID 01
-> RAID on top of RAID 1
- 2 x striped disks

## Backups
-> # 2-4 uses a Archive Bit, indicates if a file has been backed up
**Full Backup** - backs up everything
**Incremental Backup** - data changed since last backup is stored
**Differential Backup** - starts with full backup, stored data changed since first backup each time
**Copy Backup** - same as full backup, but does not update Archive Bit, used before software updates


# Business Continuity & Disaster Recovery
## **BCP** (Business Continuity Planning)
-> overarching term that details how a business will continue normal operations
- includes DRP, disaster *avoidance*

### 7 Phases of BCP
- **Project Initiation** - starting the project = securing funding, management approval, etc
- **Buisness Impact Analysis** - identifies *critical* processes to the business, defines metrics
	- criticality is all about TIME = processes that cause the most impact if down for a short time
	- **SLA** (Service Level Agreement) - legal contract detailing metrics for a service & financial penalties if breached, details SLO & SLI s
	- **SLO** (Service Level Objectives) - a target reliability level of a service
	- **SLI** (Service Level Indicators) - metrics that measure performance & reliability
		- **RPO** (Recovery Point Objective) / **MTD** (Maximum Tolerable Downtime) - maximum time until recovery from a disaster
		- **MOR** (Minimum Operating Requirements) - essentially minimum system requirements
- **Identify Recovery Strategies** - consider recovery plan, ex:  hot, warm & cold sites
- **Plan design & Development** - create recovery plan
	- **Implementation**
	- **Testing** - should happen either regularly or after major change, in order to *improve response*
		- **Checklist Test** - asking managers if they are aware of the BCP
		- **Table Top Test** - moving through phases of the test
		- **Simulation Test** - going through a actual scenario
			- **Parallel Test** - some operations moved to a hot site
			- **Full Interruption Test** - all operations moved to hot site
	- **Maintenance**

## **DRP** (Disaster Recovery Planning) 
-> minimising the effects of a disaster (from the perspective of post-disaster)
- Three key elements, prevention (pre-disaster) , continuity (during disaster) , recovery (after disaster)
