# Incident Reporting
Security incident reporting serves as a conduit between the identification and remediation of threats. It facilitates the archival of past incidents, thereby providing an invaluable repository for lessons learned from previous mistakes. This repository can be seamlessly integrated into a broader strategy for preempting and mitigating future threats. Given the perpetually evolving threat landscape, a comprehensive and consistent incident reporting framework is indispensable for ensuring that organizations and their workforce are optimally prepared for any contingencies.
# Identifying Security Incidents
Security incidents can emanate from a diverse array of sources and often manifest as detections, anomalies, or deviations from established baselines. There are primarily three key sources for incident identification:

- Security Systems/Tooling - in Place	There is a wide variety of security systems and tools likely in place within your organization. Some excellent sources for identification include IDS/IPS, EDR/XDR, SIEM tools, or even basic anti-virus alerts and NetFlow data.
- Human Observations -	Users may notice and report suspicious activities, unusual emails, or systems behaving abnormally.
- Third Party Notifications -	Partners, vendors, or even customers might inform organizations about any vulnerabilities or breaches they are experiencing.

## Categorising Security Incidents
Upon identification of an incident, it is imperative to categorize it to facilitate the prioritization and allocation of resources for an effective response. This categorization also aids in comprehending the nature of the incident, thereby informing subsequent briefings to stakeholders.

Examples of Incident Types:
- Malware: Malicious software encompassing viruses, worms, and ransomware.
- Phishing: Fraudulent endeavors to exfiltrate sensitive information, predominantly via email.
- DDoS Attacks: Deliberate attempts to inundate a system or network, thereby disrupting its regular functionality.
- Unauthorised Access: Incidents where unauthorized entities gain access to systems or data repositories.
- Data Leakage: Inadvertent exposure of confidential data, both within and outside the organizational perimeter.
- Physical Breach: Unauthorized physical access to secure locations.

## Incident Severity Levels:
- Critical (P1): Imminent threats that jeopardize core business functionalities or sensitive data, necessitating immediate intervention.
- High (P2): Latent threats to business operations that, while not immediately detrimental, are of elevated priority.
- Medium (P3): Incidents that, although not posing an immediate threat to business operations, warrant timely attention.
- Low (P4): Trivial incidents or routine anomalies that can be managed within standard operational workflows.

# The Incident Reporting Process
The reporting process serves as the cohesive framework that binds all elements of security incident reporting. An effective, overarching reporting mechanism delivers not just clarity and direction, but also highly actionable insights. In this section, we'll dissect the requisite steps within this process.

- Initial Detection & Acknowledgemen
- Preliminary Analysis
- Incident Logging
- Notification of Relevant Parties
- Detailed Investigation & Reporting
- Final Report Creation
- Feedback Loop!

# Elements of a Proper Incident Report
## Executive Summary
### Let's consider the Executive Summary as the gateway to our report, designed to cater to a broad audience, including non-technical stakeholders. This section should furnish the reader with a succinct overview, key findings, immediate actions executed, and the impact on stakeholders. Since many stakeholders may only peruse the Executive Summary, it's imperative to nail this section. Here's a more granular breakdown of what should be encapsulated in the Executive Summary:

- Incident ID	Unique identifier for the incident.
- Incident Overview	Provide a concise summary of the incident's events (including initial detection) and explicitly state its type. Was it a ransomware attack, a large-scale data breach, or both? This should also encompass the estimated time and date of the incident, as well as its duration, the affected systems/data, and the status (ongoing, resolved, or escalated)
- Key Findings	Enumerate any salient findings that emerged from the incident. What was the root cause? Was a specific CVE exploited? What data, if any, was compromised, exfiltrated, or jeopardized?
- Immediate Actions Taken	Outline the immediate response measures taken. Were the affected systems promptly isolated? Was the root cause identified? Did we engage any third-party services, and if so, who were they?
- Stakeholder Impact	Assess the potential impact on various stakeholders. For instance, did any customers experience downtime, and what are the financial ramifications? Was employee data compromised? Was proprietary information at risk, and what are the potential repercussions?

## Technical Timeline
- Reconnaissance
- Initial Compromise
- C2 Communications
- Enumeration
- Lateral Movement
- Data Access & Exfiltration
- Malware Deployment or Activity (including Process Injection and Persistence)
- Containment Times
- Eradication Times
- Recovery Times
