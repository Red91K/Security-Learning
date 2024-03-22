# Information Security Risk Management
-> process of managing risks associated with IT

## Key Definitions
**Asset** - Anything with value to a organisation (ex: data, hardware, reputation)
**Vulnerability** - A weakness, absence of a safeguard
**Threat** - Something that could damage a *asset*
**Threat Actor** - Someone who causes a threat
**Exploit** - When a vulnerability is exploited to damage a asset
**Risk** - Probability of a threat materialising & it's impact
**Controls** - Ways of mitigating *Risk*
- *Safeguards* - deterrence / prevention
- *Countermeasures* - detectives / correction

**Total Risk** - Risk without any controls
**Residual Risk** - Leftover risk after controls
! Risk *"Removal"* is impossible, there will always be some amount of residual risk
-> ultimate goal of Risk Management is reducing residual risk to a amount that is acceptable to senior management

**Secondary Risk** - A risk event triggering another risk
**Incident** - a Exploit that has happened / A risk that has materialised

# Risk Management Lifecycle
## identification
-> identifying our assets, possible vulnerabilities, and threats
- only *identifying* risks, no controls, no risk value, etc

**Risk Register** - a database listing identified risks, their probability, impact, etc
-> begin populating **Risk Register** with possible risks

## assesment
-> identify a *risk value* - probability of risk x impact of risk

### Quantitative Analysis - more subjective 
-> using words like *"low, medium, high"* , no numerical *risk value*
-> a instinctual assessment (often by subject matter experts)
-> calculation = *probablity x impact*, a *heat map* is often used
may use **Delphi Technique** - method of forecasting events based on the consensus of experts

### Quantitative Analysis - more objective
-> providing a *numerical (often dollar) value* to each risk
-> complex calculation required
! buisness decisions are made w/ Quantitative, used for *cost/benefit* analysis
! Quantitative depends on Qualitative

**AV** (Asset Value) - how much a asset is worth in $
**EF** (Exposure Factor) - percentage of a asset loss in a risk event
**SLE** (Single Loss Expectancy) - (AV x EF) expected loss in $ during a risk event
**ARO** (Annual Rate of Occurance) - probability of risk appearing per annum
**ALE** (Annual Loss Expectancy) - (SLE x ARO) cost per annum because of a threat
**TCO** (Total Cost of Ownership) - total cost of implementing a *control*
**ROI** (Return on Investment) - $ saved by implementing *controls*
ROI = ALE before *controls* - ALE after *controls* - TCO
TCO / ROI = cost/benefit

1. Analysis (Probability x Impact = Risk Value)
2. Evaluation (Risk Value vs TCO of Control)

## mitigation
-> based on the *risk value* & our risk [[#assesment]], devise **Controls** to lower the risk value to a acceptable level
 
-> Reduce, Transfer, and Accept
**Reduction / Avoidance** - lowering the probability / impact of a risk (ex: security policies)
! Avoidance is reducing probablity / impact to *zero*

**Transfer** - reducing loss by *sharing the risk* with another entity (ex: insurance, SLAs)
! you cannot transfer liability

**Acceptance** - *"ignoring"* residual risk, often as a result of a negative cost/benefit analysis
! when the TCO > ALE or when the cost of Controls > risk value

## monitoring
-> monitor the effect of **Controls**, effectiveness of mitigation, and continue [[#assesment]]
-> due to the ever changing threat landscape, continuous monitoring is essential
-> that is why Risk Management is a *lifecycle*

# Virtualisation
## VDI (Virtual Desktop Infrastructure)
- *Thin clients* run the most basic OS, hardware, software, etc
- User connects to a VM (hosted on a network) using RDP
- User loads a *golden image* each time, User data is saved as part of a *user profile* on the server
- All processing is performed by the server

! However, single point of failure

## Application Virtualisation
- More limited than VDI
- Applications are run on a remote server, delivered to client via a web browser

## Container Virtualisation (Containerisation)
- partitioning a system into different instances that are isolated from each other

## VM Escape
- when Malware manages to 'escape' from the instance it is running on, and affect other instances / the host system
- A exploit of *hypervisor vulnerabilities*

# Cloud Security
![](https://www.leanix.net/hs-fs/hubfs/IaaS-vs-PaaS-vs-SaaS-Diagram.png?width=564&name=IaaS-vs-PaaS-vs-SaaS-Diagram.png)

## Cloud Security Considerations
**Endpoint Protection** - securing connections to end users
**Hypervisor Security** - continuous patching of the hypervisor
**Traffic Filtering**
**API Security**
**IAM** (Identity and Access Management)

## APIs
-> Application Programming Interface, code that governs *how a web service can request information or services*
! APIs are important because they are the vendor, OS, software neutral messengers of the internet
- Governs three main aspects:
**Access** - who should have access to the information
**Request** - what data or services can be asked for (**methods** - ex: GET, **parameters**)
**Response** - the data sent in response

# 5G
-> main difference is a increase in speed (up to 1GB/s, theoretically 10Gb/s)
- Lower latency
- Less power, 5G enables low energy mode
- Higher uptime
