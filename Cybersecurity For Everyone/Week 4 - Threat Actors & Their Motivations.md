# L1 - Threat Actors: Who are the hackers?

## summary
-> Threat Actors are **individuals** or *groups* that intentionally attempt to jeapordize the C,I,A of assets in cyberspace
-> TAs have varying intentions, capabilities, and opportunities that affect their targets and TTPs
-> Notable cyberattacks: 2015 Lazarus group steals 81 million from Bangladeshi bank, 2005 stuxnet destroys 20% of iran's nuclear centrifuges, 2016 3 billion yahoo accounts leaked by russian TA


## Threat Actors
- A cyberattack is orchestrated by a individual or group
- Threat Actors are motivated by some purpose
	- Many different types: curiosity, ego, reputation, $, nationalism
- Threat Actors has varying capabilities
	- ex: financial resources, skill level, 
- varying opportunities are available for threat actors
	- ex: Specific vulnerabilities, security posture
- Threat Actors use specific TTPs (Tactics, Techniques, and Procedures)
	- TTPs depend on intent, capability & opportunity - ex: intended effect, Skill level, Tools avaliable, financial resources, vulnerabilities in target system,

## Notable Cyberattacks
-> Cybercrime alone costs the world $6 trillion dollars
- 2015, Lazarus Group uses social engineering to infiltrate Bangladesh's central bank, nearly extracting $1 billion dollars
- 2005, Stuxnet was a highly advanced worm that targeted SCADA systems, destroying nearly 20% of Iran's nuclear centrifuges
	- IAV - physical insertion
	- Lateral Movement w/ 4! zero-days
	- Defense evasion through host identification & self-destruction
- 2016, all 3 billion of Yahoo user accounts were compromised in a spear-phishing attack against yahoo employees - Yahoo settled for 120 million in damages

# TAs: Hobbyists / Skiddies
## summary
-> Hobbyists / Script-Kiddies are Threat Actors that are motivated by impulsive emotions, lacks sophisticated capabilities, and targets indiscriminately based on available opportunities
-> As a result...
Tactics - unpredictable goals, recycles TTPs entirely
Techniques - cost-effective & unsophisticated 
Procedures - widely-distributed tools

## intent / motives
- Curiosity
- increasing their reputation / fulfilling their ego
- other impulsive, non-generalisable intents ! -> unpredictable

## capabilities
- Disorganised, lone actors
- Low skilled, little knowledge of defenses
- Lightly resourced

## opportunities
- attacks & targets depend on the presence of easily-exploitable vulnerabilities / poor security posture

## TTPs 
### tactics
-> recycles T,T,and P wholesale
-> unpredictable goals, often even unknown to the attacker 

### techniques
-> common, low-cost techniques (ex: phishing, DDOS, defacement, brute-forcing, searching for exposed services)
-> unsophisticated techniques -> easily detected
	-> lack of proper anonymisation
	-> does not care about defense evasion, persistence, anti-analysis, etc

### procedures
-> off-the-shelf, distributed tools that may not even work

# TAs: Cybercriminals
## intent
- Financial Gain, either directly or through 3rd party buyers / funding

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
- targeting depends on opportunities for profit
- ROI is a significant consideration

## TTPs
### tactics
- strategic objectives are always connected to financial gain
	- ransomware
	- Access-as-a service
	- DDOS-as-a service
	- selling corporate secrets / user data
	- goals to secure Government funding
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
- Fin7 - Russian APT - targets retail & hospitality
- Cobalt Group - Russian APT - targets financial systems like ATM, SWIFT, banks
- Lazarus Group - DPRK APT - various targets
