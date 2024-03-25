
# Key Takeaways

# Lesson 2 - Types & Sources

## The 2 Types of Intelligence
> "Operational Intelligence tells us what to do in the moment.
> 
> Strategic Intelligence can prevent these moments from happening."

We previously defined intelligence as "the process of collectiong, analyzing, and disseminating information that enables **informed decisionmaking** and **effective action**"

**Operational** Intelligence informs decisionmaking in daily operations.
- "hands on" intelligenece that must be immediately acted upon
- in the context of cybersecurity, operational intelligence
  - contextualizes alerts, identifies immediate lapses in defense, and accelerates SecOps & IR.
  - involves indicators of compromise, zero-day vulnerabilities, and emerging Threat Actor TTPs

**Strategic** Intelligence informs high-level decision-making in anticipation of future trends.
- intelligence that drives action in anticipation of future developments, typically sourcing information collected over a long period of time
- in the context of cybersecurity, strategic intelligence
  - directs business expenditure, drives long-term strategy, informs risk assesments
  - involves emerging trends in attacker TTPs, common motivations, changes ini the threat landscape

## Threats & Attack Vectors
### 4 Main Types of Threats
1. **Natural** - threats posed by natural disasters
2. **Intentional** Human - threats posed by a malicious actor
3. **Unintentional** Human - threats posed by unintentional actors
4. **Technical** - threats posed by malfunctions in technology

### "Big Four" Attack Surfaces & Attack Vectors
1. **Email** - Email is a lucrative attack surface due to its ubiquitous use and importance to business operations
	1. Phishing
2. **Software** - As businesses integrate software across various departments and functions, the attack surface posed by vulnerable software continues to increase
	1. Software Vulnerabilities--both 0-day and n-day vulnerabilities
3. **Cloud** - Organizations increasingly adopt cloud computing while ignorant of its unique attack surface
	1. Adversaries have caught up with this trend, and have begun increasingly targeting cloud assets
4. **Trust** - 
	1. Insider Threats are a unique attack vector because of difficulties in prevention and detection. However, certain technologies & processes **can** protect against this attack vector--like UBA solutions, user training, and least privilege 

## Sources of Intelligence
> The Role of Data Feeds, Private Channels, and the Dark Web

### Threat Data Feeds
- Fundamentally, data feeds are consistently updated repositories of **structured information**
- However, Threat Data Feeds alone **cannot provide intelligence**, only data or information at best that needs to be processed and analyzed into intelligence

4 Criteria for evaluating the quality of threat data feeds
1. **Source Variety** - What sources does the data feed collect from? Are there any gaps in visibility? Is data collected from a range of internal and external sources?
2. **Source Transparency** - How is the data collected? What sensors are used, with what kind of configurations? Are there any gaps in collection?
3. **% Unique Data** - How much overlap exists between each collection sources?
4. **Timeliness** - How recently has the data been collected? How often is the feed updated?
### Private Channels & the Dark Web
The internet can be divided into 3 "layers"
- **Surface Web** - readily accessible, indexed by search engines
	- ex: blogs, news articles, public vendor reports
- **Deep Web** - protected by some form of authentication, not indexed by search engines
	- ex: TLP AMBER reports, internal threat data feeds, internal databases, legal records, etc
- **Dark Web** - requires specialised software (the TOR browser) to access
	- ex: illegal marketplaces, dark web forums, etc

! The surface web is estimated to only comprise **4%**!! of the entire internet
### Challenges in Using Private Channels
1. **Gaining Access** - By definition, private channels are guarded by some form of authentication to prevent unauthorized access of communications. Organizations looking to collect from private channels will often have to defeat some kind of authentication scheme to even gain access to these channels.
2. **Language Barriers** - Organizations are frequently targeted by foreign threat actors. Language barriers, further exacerbated by the use of jargon, can create difficulties in understanding the collected data.
3. **Obfuscation** - Many private channels are aware of the threat of infiltration & the practice of intelligence collection against them. Threat Actors will use jargon, encrypted or encoded messages, or other techniques like tokenaization to preserve the confidentiality of their communications
4. **Business & Legal policy restrictions** - restrictions against dark web intelligence collection may exist at both the organization and legal level.
