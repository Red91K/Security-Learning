# Virtualisation
-> the creation of a virtual, simulated computing enviornment
- perfect for testing software, reversing malware, etc
- we can use *snapshots* for quick backups
- Relies on secure *Hypervisor* - software that manages VMs

## VDI (Virtual Desktop Infrastructure)
-> process of separating the virtual machine from the physical machine
- a *'golden image'* stored in the physical machine acts as the baseline for each VM instance, ex: desktop files, security configs

## Application Virtualisation
-> separation of an installation of a application from the client computer accessing it
- software is installed and run on a server, client accesses it

## Hypervisor
-> software that creates and runs hypervisors

### Type 1
-> "bare metal", runs directly on the hardware
- better performance, more secure
- does not need a operating system
! used for data center computing, ex: cloud

### Type 2
-> runs on a host OS, software based
- less secure 
! used for end user systems, ex: VMWare workstation

## VM Security Concerns
- **VM Escape** - a program or a process breaking out of a VM and affecting the host OS
- Single point of failure for multiple processes
- Anti-malware & monitoring needed for each VM

# Cloud Computing
-> model for enabling convenient, on-demand network access to a pool of configurable computing resources
- *convenient, on-demand* - 'pay as you go' model, distributed servers for faster access
- *configurable* - multiple services, ex: cloud compute, AI training, etc

## Why Cloud
- Scalability & Agility
	- Can be scaled easily
	- Can be repurposed easily
- Convenient
	- Easy to set up, no need of maintenance
- Transparent & Flexible Cost
	- Pay as you go model makes costs easy to calculate, no additional variables to consider (ex: maintenance, attacks, etc)
	- Cost scales with usage, no $ wasted
- Fault Tolerance
	- Can easily fire up more VMs if one goes down
	- Because of distributed servers, often resistant to disturbances


## SaaS (Software)
-> software hosted on the cloud is licensed to a client 
ex: Apple Music, Gmail, CRM
- mainly used by end users

### Advantanges
- convenient setup & deployment
- acssesible, often only requires browser or lightweight app
- new releases & upgrades -> security & future proof

### Disadvantages
- lack of flexibility (everyone uses same software, can't customise)
- Performance (compared to on-prem)
- risk of vendor lock in


## PaaS (Platform)
-> provides a environment where the client can deploy their applications onto cloud 
infrastructure, with the support of preinstalled languages, libraries, tools, etc
- mainly used by developers

### Advantanges
- future proof (because of constant datacenter upgrades)
- convenient deployment
- customisable

### Disadvantages
- security risks (buisnesses are responsible for securing)
- vendor lock in

## IaaS (Infrastructure)
-> providing *computing infrastructure*, that customers can manage and use in the same way as on-prem hardware
- used by corporations & sysadmins

### Advantanges
- flexible cost
- easy scalability

### Disadvantages
- security risks
- performance dependent on broadband

## Deployment Models
### Public Cloud
-> computing services offered by third parties over the public internet
- typically not used for sensitive or imperative info
- cheapest, most common
- less customisable

### Community Cloud
-> in between public & private, cloud providers targeting a specific industry or common goal

### Private Cloud
-> aka internal cloud, cloud dedicated to a single organisation
- used for buisness critical or top secret information or organizations, ex: governments, fintech
- can be on prem or hosted by third party
- more customisable

### Hybrid Cloud
-> using a combination of on-prem (private cloud) and public cloud
-  public cloud is often used for...
	- unexpected high demand  (**Cloud Bursting**)
	- disaster recovery (to keep services operational)
	- lower security / less imperative services & info
- private cloud is often used for...
	- sensitive info
	- buisness critical operations

# IoT
-> physical object with sensors, processing power, software that exchange data

