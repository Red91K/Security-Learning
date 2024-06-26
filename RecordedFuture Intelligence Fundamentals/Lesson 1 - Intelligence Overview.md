# Key Takeaways
> The **decision advantage** that intelligence provides is crucial to defending against today's threats that continue to evolve in volume and sophistication

> **Security** is the process of defending assets against *known threats*. **We cannot defend a system against a threat we do not understand.** Therefore, **Intelligence**--the collection, analysis, and dissemination of information that enables better decision-making and effective action--is a critical part of security.

> **Actionable intelligence** is intelligence that **points to a specific action**, and is **addressed to a specific audience.**

> **TTPs (Tactics, Techniques, and Procedures)** are higher-level descriptions of adversary behaviour. It provides a framework for categorising the behavior of threat actors, helping security professionals identify, analyze, and respond to cybersecurity threats effectively.

> `Risk = likelyhood x impact`. For risk to exist, there needs to be both a **vulnerability** (a flaw / lapse in defenses) and a **threat** (someone to exploit the vulnerability)

> Intelligence is often confused with data and information. **Data** is **collected** from a variety of sources like endpoints, firewalls, and threat feeds. **Information** is **processed** by enriching data with context. **Intelligence** is **analyzed** from information--by forming connections between information, evaluating reliability, and considering higher level trends. 

> Intelligence benefits a number of business functions, such as SecOps & IR teams, Risk teams, Vulnerability management teams, and executives.

# Introduction
Today, cyberattacks continue to increase in volume and sophistication. We need to approach security proactively instead of reactively. Such a proactive approach requires intelligence.
A proactive approach involves
- anticipating threats before they strike
- continuously monitoring assets & assessing risk against them
- learning from other organisations that have been breached

Fundamentally, intelligence provides a _decision advantage_. 




# Intro 2 Intelligence
**Security**: mitigating known threats
**Intelligence**: process of collecting, processing, analyzing, and disseminating information that enables better decisions and effective action
- *actionable* intelligence has two qualities
	- Points towards specific decisions or actions, ex: contains blockable IOCs, TTPS to defend against, defensive mitigation advice, etc
	- addressed and disseminated to a specific audience. 
- Machines provide the time-savings & context that allows human analysts to make *big picture, intuitive analyses*

**Threat**: potential to cause harm


## definitions
**Threat Intelligence**: knowledge that enables the mitigation of threats
**Security Intelligence**: an approach to risk management that relies on knowledge of threats, security trends, industry & world developments, etc

**Cybersecurity**: Protecting *digital assets* against threats to their confidentiality, availability, and integrity
**Information Security**: Protecting *information and information systems* against threats to their confidentiality, availability, and integrity

-> Although they are often used as interchangeable synonyms, Information Security and Cybersecurity refer to two distinct approaches to security.
-> Information Security is an umbrella term that covers the protection of information and any system that exchanges information, while Cybersecurity exclusively focuses on digital systems.


## Review of the CIA Triad
-> Framework describing the goals of information security

**C** - Confidentiality - Information is safe from unauthorized access
ex: Many protocols like HTTPS uses encryption to ensure the confidentiality of transmitted data

**I** - Integrity - Information is safe from tampering in rest & in transit
ex: Hashing algorithms like SHA256 and MD5 can be used to validate integrity of information

**A** - Avaliability - Information is safe from disruptions to its accessiblity
ex: Load balancers and Content Delivery Networks can protect against DDOS attacks that render services inaccessible

(**N**) - Non-Repudiation - the sender and the recipient cannot deny their participation in a transaction of information
ex: Digital signatures use asymmetric-key cryptography to undeniably prove the sender's identity




# Visibility into Threats
## Risk
- two ingredients make up risk: 
	- **vulnerability** - an exploitable flaw or a lapse in defenses
	- **threat** - a potential source of harm 
- Risk = likelihood of occurrence x impact 

**FAIR Model**
-> Framework to assess operational risk
- divides likelihood into...
	- the likelihood of a threat actor taking action
	- the threat actor's capability in comparison with existing defenses
- impact is calculated recursively, considering both primary impact and secondary risk
![](https://www.fairinstitute.org/hubfs/FAIR-Flowchart.png)

**IOC**: artifacts (ip addresses, file hashes, domains, unusual traffic) that *indicates an intrusion* with high confidence

**TTPs**: high level descriptions of adversary behavior
- **Tactics** - the adversary's general approach
	- ex: UNC5325 aims to gain Initial Access by first compromising the victim's intranet
- **Techniques** - specific step that advances towards the completion of a tactic
	- ex: UNC5325 exploits public facing victim infrastructure
- **Procedures** - detailed description
	- ex: UNC5325 exploits CVE-2023-46805 and CVE-2024-21887,  authentication bypass and command injection vulnerabilities in Ivanti Secure VPN gateways




# Actionable Factors
## Data? Information? Intelligence?
**Environment** --(Collection)--> **Data** --(Processing)--> **Information** --(**Analysis**)--> **Intelligence**

**Data** - a fact, a piece of information
- ex: `218.56.58.196`, TCP, `20000`, China Unicom, `2024-03-09`

**Information** - data enriched with context
- ex: `218.56.58.196` is an ip address managed by China Unicom, that established and rapidly dropped `20000` connections to our public facing infrastructure over `TCP/22` between `2024-03-09` and `2024-03-10`

**Intelligence** - information analysed in order to answer questions
-> forming connections between information, evaluating reliability, addressing biases, etc in order to **answer a specific question**
- ex: Intelligence Requirement - **What are the most pressing threats facing our organization?**
-> Although ssh bruteforce attempts like the one originating from `218.56.58.196` have frequently targeted our organization, due to the **limited use of ssh** across our organization and the **presence of defenses** against ssh bruteforcing and similar brute-force attacks, we **assess with high confidence that this malicious activity is not a pressing threat** to our organisation

*4 Qualities of a succesful intelligence program*
1. **collaborative, integrated across departments** - intelligence shouldnt be siloed into departments, instead used holistically across the organization
2. **360 degree visibility** - intelligence should be collected from a variety of internal and external sources
3. **leverages automation** - to enable analysts to focus on big picture, intuitive analysis
4. **aligned with specific goals** - intelligence programs should have well-defined, specific goals with respect to each stakeholder

# Who benefits from Intelligence?
-> A wide range of business functions benefit from intelligence

## 1. SecOps & IR teams
- The context that Intelligence provides acclerates and strengthens security operations and incident response
- **SecOps:** 
	- contextualized alerts allow faster triage
	- operational intelligence about adversary TTPs leads to effective detections
	-  context can eliminate false-positives that contribute to burnout
- **IR:** 
	-  understanding the adversary is crucial to properly responding to an intrusion
	- intelligence about actions the adversary previously took to gain persistence & move laterally enable effective incident remediation
	- intelligence gives a clearer picture of the overall intrusion and the root causes of the incident

## 2. Risk Teams
- Intelligence allows **better prioritisation** of risks & informs us of **effective mitigations** by giving us a better understanding of the threat

## 3. Vulnerability Management Teams
- intelligence about the severity, risk of exploitation, and about the potential impact of each vulnerability helps vulnerability management teams better prioritise and remediate vulnerabilities

## 4. Fraud, Brand protection, IAM Teams
- Each of these functions are impossible without actionable intelligence
	- **Fraud** - identification of fraudulent transactions, emerging techniques, etc
	- **Brand Protection** - identifying impersonations, typosquatting, misinformation, etc
	- **Identity** - searching for leaked credentials in breach forums, identifying identity theft attack vectors, etc
	
## 5. Security Leaders & Business Executives
- For high level decision makers, intelligence delivers a powerful **decision advantage**
- Intelligence informs better business strategy, allows better allocation of funding, and helps executives deal with risk.
