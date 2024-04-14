# Summary
- This module explores why we should care about cyberattacks, why threat actors carry out attacks, and how cyberattcks are carried out


# Lesson 1 - Reasons Behind Cyberattacks
> A **Cyberattack** is a **deliberate** exploitation of a computer system using **malicious software** to **compromise data or disrupt operations**

## Why does this matter?
- Cyberattacks matter more than ever because more things utilise information technology than ever before
- ex: Given that most corporations have turned to digital access control systems, a cyberattack could potentially completely 
- ex: Though rarely directly connected to the internet, Industrial Control Systems--specialised information technology devices--drive the operations of critical infrastructure. Cyberattacks targeting ICS devices could cripple power grids, and take down communications networks, and even devastate nuclear power plants.


## Common Types of Attacks & Vulnerabilities
- Physical access
- Brute force attacks
- Misconfigurations
- Watering hole - when an attacker targets a website likely to be visited by victims
- Phishing
- SQL injection
- Denial of Service
- Malware


## Reasons for Cyberattacks
- National interests
- Hacktivism
- Espionage
- Legitamate Research--vulnerability scanners, penetration testers
- Hobbyists


## Impacts of Cyberattacks
> Cyberattacks are important not for the damange they do to devices, but for their destabilizing effect on organizations and societies

Potential Impacts include:
#### Secondary Effects
- **Reputational & Brand damage** -> lost sales,  opportunities, investor confidence -> lost $$$
- **Loss of intellectual property** -> loss of competitiveness, 
- Regulatory fines
- Costs of Recovery
- Direct financial theft


#### Second-Order Effects
- Disruption of critical services-- ex: internet connectivity, power, transportation
- Manipulation of elections
- Loss of Sensitive PII (Personally Identifiable Information) to malicious actors -> could enable further attacks, but in itself is a compromise of security


## What Needs to Change?
- fundamentally, effective defense comes down to a **faster response**. 
- The quicker each cybercriminal operation is detected, relevant information shared, and apropriate defenses enacted, the **less financially viable** cybercrime will be


# Lesson 2 - Global Threat Trends
- Decided to use IBM X-force's 2024 report, instead of the 2021 edition in the course
- Check out the report [here](https://www.ibm.com/account/reg/us-en/subscribe?formid=urx-52629)

## Context
- 2 major wars offer glimpses of modern cyberwarfare: Russia-Ukraine & Israel-Hamas
   - Both conflicts saw the use of cyberattacks, both as a compliment to military operations and 
   - Both conflicts saw the use of extensive cyber-enabled influence operations to target morale & international support.
- Generative AI explodes in popularity and promises revolutions in the cybersecurity field

## Top Attack Trends
- The most dramatic shift was the focus on targeting **Identity**. Likely due to the relative ease of acquiring valid credentials, threat actors began to *"log in instead of hack in"*
   - Stolen credentials were not only a popular infection vector, but also a popular means of lateral movement--X Force saw a 100% increase in **Kerberoasting** attacks (pass-the-ticket attack against kerberos, a authentication 
   protocol used for Windows AD)
   - Infostealing malware designed to steal credentials also saw a surge in usage
- Despite the **hype around Generative AI**, X-force has yet to see any evidence of cyberattacks enabled by GenAI or any significant attacks targeting LLMs. However, this likely does not indicate a lack of interest--
- **Ransomware attacks dropped** significantly, but extortion still remains the 2nd most popular end effect. This might be a limitation with IBM's visibility, because an analysis of global ransomware extortion sites indicate *increased activity*. However, the decrease in ransomware activity makes sense given the avaliability of other lucrative methods of extortion, like data theft.
- **Zero Day attacks declined 72%** from 2022, likely indicative of Threat Actors **continuously seeking *more resource-effective* infection vectors**

## Top Initial Access Vectors
1. Valid Accounts (up 71%)
2. Phishing (down 44%)
3. Exploit Public Facing Applications

- Threat actors have **revalued credentials as a reliable and preferred initial access vector**
- Credential Access likely preferred over Phishing due to effectiveness & time savings--IBM estimates that the average human-crafted phishing email takes 16 hours
- Linking this to the rise of generative AI, IBM asseses that phishing will be the first use cases of Generative AI
- Threat Actors continue to evolve TTPs across the attack chain to evade detection, ex: QR codes to deliver malware, fake browser updates, complex execution chains

## Top Actions on Objective
1. Ransomware
2. Credential Theft
3. Data exfiltration

## Unique Defensive Reccomendations for 2024
- Reduce risk of credential theft, using EDR solutions that can monitor & prevent credential  exfiltration
- Implement a IAM solution to manage identities & the privilidges associated with them
- Reduce the "blast radius" of intrusions using least privilidge, network segmentation, continuous monitoring
- Implement Dark web capabilities to scan for exposed credentials & session keys

# Lesson 3 - Trends by Industry & Geography