
# summary
> Threat Actors are **individuals** or *groups* that intentionally attempt to jeapordize the confidentiality, integrity, and avaliablility of assets in cyberspace
->TAs have varying motivations, capabilities, and opportunities that in turn influence their targeting and the Tactics, Techniques, and Procedures that they use
- Therefore, understanding the who, what and why of Threat Actors helps us understand how and what they will attack
> **Hobbyists** are

> **Cybercriminals** are

> **Hacktivists** are

> **Advanced Persistent Threats** are

# Threat Actors
- A cyberattack is orchestrated by a individual or group
- Threat Actors are motivated by some purpose
	- Many different types: curiosity, ego, reputation, $, nationalism
- Threat Actors has varying capabilities
	- ex: financial resources, skill level, 
- varying opportunities are available for threat actors
	- ex: Specific vulnerabilities, security posture
- Threat Actors use specific TTPs (Tactics, Techniques, and Procedures)
	- TTPs depend on intent, capability & opportunity - ex: intended effect, Skill level, Tools avaliable, financial resources, vulnerabilities in target system,

# Notable Cyberattacks
-> Cybercrime alone costs the world $6 trillion dollars
- 2015, Lazarus Group uses social engineering to infiltrate Bangladesh's central bank, nearly extracting $1 billion dollars
- 2005, Stuxnet was a highly advanced worm that targeted SCADA systems, destroying nearly 20% of Iran's nuclear centrifuges
	- IAV - physical insertion
	- Lateral Movement w/ 4! zero-days
	- Defense evasion through host identification & self-destruction
- 2016, all 3 billion of Yahoo user accounts were compromised in a spear-phishing attack against yahoo employees - Yahoo settled for 120 million in damages

# Hobbyists
## summary
-> Hobbyists / Script-Kiddies are Threat Actors that are motivated by impulsive emotions, lacks sophisticated capabilities, and targets indiscriminately based on available opportunities
-> As a result...
Tactics - unpredictable goals, recycles TTPs entirely
Techniques - cost-effective & unsophisticated 
Procedures - widely-distributed tools

## intent / motives
- Curiosity
- increasing their reputation / fulfilling their ego
- other impulsive, non-generalisable intents -> incredibly unpredictable

## capabilities
- Disorganised, lone actors
- Low skilled, little knowledge of defenses
- Lightly resourced

## opportunities
- attacks & targets depend on the presence of easily-exploitable vulnerabilities / poor security posture

## TTPs 
### tactics
- recycles T,T,and P wholesale to save costs
- unpredictable goals, often even unknown to the attacker 
- actions on objective tend to be **disruptive effects** that fuel ego

### techniques
- common, low-cost techniques across the kill chain (ex: phishing, DDOS, defacement, brute-forcing, searching for exposed services)
- unsophisticated techniques -> easily detected
	- lack of proper anonymisation can expose identities
	- does not care about evading detection or maintaining persistence on targets

### procedures
- off-the-shelf, widely distributed tools that may even be defective

# Cybercriminals
## intent
- primarily motivated by **Financial Gain**, either directly or through 3rd party buyers / funding (ex: initial access brokers)

## capabilities
- varies in size, skill & resources, based on size of organisation & profitability of operations
- at the low end, 
	- low-skilled, 
	- disorganised groups / no organisational hierarchy,
	- depends on immediate revenue to sustain operations
- at the high end,
	- high-skilled
	- organisational / management structure,
	- financial resources that can sustain operations even in downturns
	- may receive funding, training, assistance from governmental institutions

## opportunities
- targets organizations that can translate into the most profit
- ROI is a significant consideration--the presence of strong defenses in comparison to potential for financial gain will often dissuade them from launching costly attacks

## TTPs
### tactics
- strategic objectives are always connected to financial gain
	- ransomware
	- Access-as-a service
	- DDOS-as-a service
	- selling corporate secrets / user data
	- achieving objectives to secure Government funding
- End-Goals / actions on objective tactics depend on buisness model
- low end: achieve access on as much profitable systems as possible, recycling techniques and procedures unless completely defended
- high end: achieve access on specific, high-value systems, constantly changing techniques & procedures to avoid detection

### techniques
- low end: cost-effective techniques that sacrifice sophistication / defense penetration
- high end: costly, sophisticated techniques that provide evade detection & forensics 

### procedures
- low end: distributed tooling, purchased infrastructure, unpatched vulnerabilities
- high end: custom tooling, extensive botnet infrastructure that can sustain operations, zero-day usage, 
- tooling varies depending on org, but at the top of the spectrum, we see custom tooling & zero-day

## examples
- Fin7 - Russian  - targets retail & hospitality
- Cobalt Group - Russian - targets financial systems like ATM, SWIFT, banks
- Lazarus Group - DPRK - various targets

# Hacktivists
## Intent
-  motivated by political, economic, or social concerns
	- ex: concerns about enviornmental harm, infringements on privacy, against war, etc
- aims to draw as much public attention as possible to these issues & to their movement
- targets governments, organizations, and even specific individuals

## Capability
- Generally low-skilled, primarily relying on well-distributed tooling due to a lack of funding
- But, in some cases can possess significant capabilities

## Opportunities
- Due to their highly specific ideological motivations, hacktivists do not simply attack targets of opportunity,
- Hacktivists will pass on opportunities to exploit vulnerabilities if not aligned with their motives

## TTPs
### Tactics
- **Disruptive** actions on objective--defacement, exposure denial of service, deletion, etc
- 
### Techniques
- Not concerned with defense evasion, avoiding detection, or maintaining persistence

### Procedures
- uses off-the shelf tooling,  exploits unpatched vulerabilities, exposed credentials, etc

## Notable Groups
-  **Anonymous** 
-  **LulzSec**: LulzSec gained prominence in 2011 for its high-profile attacks on companies such as Sony, Nintendo, and media organizations like PBS. They often targeted entities for the "lulz" or laughs, but their actions also served to highlight security vulnerabilities in major systems.

# Advanced Persistent Threats
