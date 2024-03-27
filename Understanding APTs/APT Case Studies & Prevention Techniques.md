# Case Studies & Prevention Techniques

## APT41
- APT41 is a **Chinese threat actor** that targets the **healthcare, telecom, and video game industries** (what a weird combo)

### case study 1: video game industry
#### context
- APT41 campaigns against the video game industry have primarily targeted companies in SouthEast and East Asia, and sometimes companies in the U.S.
- Campaigns include....
	- compromising video game companies to enable further operations--ex: by modifying source code and compromising digital certificates
	- financially-motivated campaigns--ex: stealing in-game currency

#### case study

| Kill Chain Stage     | APT41 Activity                                                                                                                                                                                                                                                                                                                                           |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reconnaissance       | APT41 has capabilities across OS environments. During the Reconnaissance stage, APT41 determines the appropriate tools to use based on the victim's OS enviornment.                                                                                                                                                                                      |
| Weaponization        | APT41 has developed a tool named PHOTO, a functional DLL backdoor. It will tune PHOTO based on the victim enviornment, prepare C2 infrastructure, and formulate an attack strategy during this phase. In this specific intrusion, APT41 prepared a linux version of PHOTO to target production machines used in the development of an online video game. |
| Delivery             | APT41 used leaked credentials to gain access to a production server.                                                                                                                                                                                                                                                                                     |
| Exploitation         | APT41 used leaked credentials to gain access to a production server.                                                                                                                                                                                                                                                                                     |
| Installation         | After gaining access to the production server, APT41 installed PHOTO. They also installed TeamViewer to facilitate lateral movement.                                                                                                                                                                                                                     |
| Command & Control    | Using PHOTO, APT41 relayed commands to compromised prod servers.                                                                                                                                                                                                                                                                                         |
| Lateral Movement     | APT41 used TeamViewer to gain access to additional hosts, on which they installed PHOTO to gain C2.                                                                                                                                                                                                                                                      |
| Actions on Objective | The specific intrusion seemed to be financially motivated--APT41 used their access to generate in-game money, which they then exchanged for real money.                                                                                                                                                                                                  |

### case study 2: healthcare
#### context
- APT41 primarily targets the healthcare industry to steal highly-valuable IP (Intellectual Property)
	- ! Such targeting was last observed in 2015
- This targeting indicates the prescence of APT41 stakeholders / backers with a stake in the healthcare industry

#### case study

| Kill Chain Stage     | APT41 Activity                                                                                                                                                  |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reconnaissance       | APT41 identified organizations that were nearing the end of their R&D phase for a new product.                                                                  |
| Weaponization        | APT41 has developed a memory-only dropper named GEARSHIFT that drops two keyloggers disguised as legitimate DLLs.                                               |
| Delivery             | APT41 delivered GEARSHIFT using brute force attacks and spoofed websites                                                                                        |
| Exploitation         | APT41 delivered GEARSHIFT using brute force attacks and spoofed websites. APT41 used GEARSHIFT to obtain a digital certificate, with which they signed malware. |
| Installation         | APT41 used GEARSHIFT to install the now-signed malware, which evaded EDR / antivirus detection due to the compromised digital certificate.                      |
| Command & Control    | APT41's C2 mechanism was unable to be determined, even in the presence of security defences & sensors. This speaks to APT41's defence evasion capabilities.     |
| Lateral Movement     | APT41 used GEARSHIFT and the compromised digital certificate to move laterally.                                                                                 |
| Actions on Objective | APT41 stole sensitive information including clinical trial data, academic findings, and R&D expenditure to establish a market advantage for its stakeholders.   |


### case study 3: citrix
- In 2020, citrix notified its users that APT41 had compromised one of its products
- This case study illustrates the concept of a supply chain attack--how compromising one organization (particularly one downstream of others) can lead to additional compromises upstream
	- The citrix case study is part of one of the largest campaigns Chinese threat actors carried out in recent years. APT41 exploited vulnerabilities in various IT appliances like Citrix Netscaler, Cisco Routers, and Zoho ManageEngine Desktop Central to target western-bloc nations around the world. APT41 targeted multiple sectors including IT, security, telecommunications, oil, gas, aviation, and government
- 


| Kill Chain Stage     | APT41 Activity                                                                                                                                                                                                                                                                         |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reconnaissance       | APT41 conducted reconnaissance to identify citrix as a downstream service provider, by attacking which they could gain access to its upstream customers                                                                                                                                |
| Weaponization        | APT41 used password-spraying attacks to gain credentials to employee accounts, and developed CVE-2019-19781, an arbitrary code execution vulnerability in citrix vpn products                                                                                                          |
| Delivery             | APT41 delivered a malicious payload exploiting CVE-2019-19781 to companies using citrix VPN products.                                                                                                                                                                                  |
| Exploitation         | The malicious payload exploited CVE-2019-19781, and executed the embedded malicious code.                                                                                                                                                                                              |
| Installation         | The malicious code used the compromised credentials developed in the weaponization phase to install malware onto victim endpoints. The malware is a java program that installs a trial version of Cobalt Strike BEACON, a lightweight backdoor that uses a hard-to-detect c2 protocol. |
| Command & Control    | AP41 used Cobalt Strike BEACON to conduct c2. Cobalt Strike is a offensive security tool that has been frequently abused by threat actors due to its versatility and advanced capabilities.                                                                                            |
| Lateral Movement     | APT41 moved laterally (in perspective to their original exploitation of the citrix vpn) to repeat the same attack agains multiple other organizations using citrix                                                                                                                     |
| Actions on Objective | APT41 stole sensitive information including employee PII and company financial data.                                                                                                                                                                                                   |


## APT28
- APT28 conducts espionage primarily against government, military, and defense organizations in Georgia and Eastern Europe. Additionally, APT28 has been observed targeting global security organizations and U.S. defense contractors 
- Given the alignment of APT28's targeting to Russian national interests, and the alignment of its working hours to Moscow time, APT28 is attributed to the Russian government

| Kill Chain Stage     | APT28 Activity                                                                                                                                                                                                                                                              |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reconnaissance       | APT28 conducts reconnaissance to identify targets that would provide intelligence into the security of Eastern European nations. Once identified, they launched spearphishing and watering hole attacks to identify specific targets of interest within these organizations |
| Weaponization        | AP28 embeds an exploit in a document.                                                                                                                                                                                                                                       |
| Delivery             | APT41 delivered the malicious document through spearphishing and watering hole attacks.                                                                                                                                                                                     |
| Exploitation         | The exploit executes once the victim downloads and presumably interacts with the document.                                                                                                                                                                                  |
| Installation         | The exploit installs SOURFACE, a multi-purpose downloader, which then installs custom malware.                                                                                                                                                                              |
| Command & Control    | The installed malware conducts C2.                                                                                                                                                                                                                                          |
| Lateral Movement     | Due to the work done during the reconnaissance phase, APT28 has already compromised the victims it intended to by this stage. It does not conduct any additional lateral movement.                                                                                          |
| Actions on Objective | APT28 collects and exfiltrates sensitive information about Middle Eastern and Eastern European governments and militaries, as well as global security organizations.                                                                                                        |

## APT Prevention Principles
- **Detect** - determine the presence of an attacker
- **Deny** - preemptively excluding a capability from the attacker
	- ex: applying a firewall rule to block c2 communciations, patching a vulnerability
- **Disrupt** - actively excludes a capability
	- ex: cutting off a c2 channel mid use, interrupting active exfiltration
- **Degrade** - marginal reduction in attacker resources
	- ex: throttling network bandwidth
- **Deceive** - deliberately feeding false information
	- ex: honeypots, honeytokens, false documents
- **Contain** - isolate compromised systems
	- ex: take compromised networks offline, revoke privileges from compromised accounts
