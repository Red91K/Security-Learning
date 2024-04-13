# Summary
- Although we often hyper-fixate on the end effects of hacking, we should keep in mind that hacking is a **extended, complicated** process that begins far before the final impact is realized
- By *dividing the Hacking process* into generalized stages, Frameworks like the Cyber Kill Chain and MITRE ATT&CK help us better understand how each action fits into the larger context of the entire process.
- Although both frameworks feature a linear ordering of stages, it is important to understand that *cyberattacks do not always follow the linear, chronological order prescribed by these models* and that single cyberattacks often *feature multiple iterations of the framework*
- **The Cyber Kill Chain** divides the hacking process into the following stages:
	- Reconnaissance
	- Weaponization
	- Delivery
	- Exploitation
	- Installation
	- Command & Control
	- Actions on Objective

# Hacking as a **Process**
- Popular culture often depicts hacking incorrectly as
	- a single event with immediate consequences
	- conducted by a lone actor
	- enjoying universal success

- In reality, hacking is a complex **process**. 
- Fundamentally, hacking is **the activities conducted by a threat actor aimed at achieving a particular goal**
- We can use **frameworks** to group these actions into stages that allow us to better understand how each action fits into a larger context

# The Cyber Kill Chain

| Stage                | Description                                                                                                                                                                                                                                                                | Examples                                                                                                                                                                                                              |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reconnaissance       | Obtaining valuable information about a target's **technologies, people, processes, and relationships** that will inform each proceeding stage of the kill chain.                                                                                                           | Discovering internet-facing infrastructure & services with network scans. <br>Using social media to identify employees & their personal information.<br>Identifying business partners using the victim's website      |
| Weaponization        | Preparing a **plan of attack** as well as developing, acquiring, and staging the required exploits, tools, and infrastructure.<br>Fundamentally, threat actors will prepare an **exploit** that takes advantage of a **vulnerability**.                                    | Purchasing domains<br>Compromising SOHO devices to use as C2 infrastructure<br>Developing malware                                                                                                                     |
| Delivery             | Delivering the exploit                                                                                                                                                                                                                                                     | Sending malicious macro-enabled Word Documents using spearphishing<br>Hosting a trojanized application on a domain<br>Sending shellcode packaged in a RCE exploit over TCP<br>Removal media                           |
| Exploitation         | Exploiting a vulnerability                                                                                                                                                                                                                                                 | Command injection in PDF reader<br>Exploiting human vulnerabilities using lure files<br>RCE vulnerability in VPN software                                                                                             |
| Installation         | Installing some form of malicious software, often with mechanisms to evade detection and maintain persistence.                                                                                                                                                             | Hooking into existing processes (injecting code into memory space of legitamate processes)<br>Creating accounts<br>Adding themselves to scheduled tasks / auto-launch items<br>loading malicious DLL files            |
| Command and Control  | Connecting to the installed software in order to relay commands<br>Often, threat actors will attempt to evade detection by obfuscating / encrypting transmissions, using legitimate & common applications, using proxies, and using legitimate-looking recipient addresses | C2 over social media platforms like discord, slack, twitter<br>C2 over a specific instagram comments section using obfuscated commands<br>C2 over https to a legitimate-looking domain hosted on cloud infrastructure |
| Actions on Objective | Conducting actions to generate an end effect<br>Often, threat actors will restart the kill chain with their newly-obtained access                                                                                                                                          | Exfiltrating intellectual property<br>Wiping devices<br>Encrypting data & asking for a ransom<br>Causing physical destruction to ICS systems                                                                          |

! Keep in mind that the Cyber Kill Chain is not perfect--attacks like fileless attacks, insider threats, and supply-chain attacks do not necessarily go through every stage nor traverse them in a linear fashion
