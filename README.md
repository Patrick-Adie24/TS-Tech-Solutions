<div align="center">

# TS TECH & SOLUTIONS
## CYBERSECURITY ASSIGNMENT — PHOENIX COHORT

### Security Operations (SOC) | Governance, Risk & Compliance (GRC)

<img src="https://img.shields.io/badge/Focus-Cybersecurity-blue?style=for-the-badge" alt="Cybersecurity">
<img src="https://img.shields.io/badge/Domain-SOC-red?style=for-the-badge" alt="SOC">
<img src="https://img.shields.io/badge/Domain-GRC-green?style=for-the-badge" alt="GRC">
<img src="https://img.shields.io/badge/Cohort-Phoenix-orange?style=for-the-badge" alt="Phoenix Cohort">

**Prepared by: Adie Patrick Betiang**

</div>

---

## 📌 Project Overview

This repository documents a cybersecurity assignment based on a simulated incident at **TS Tech & Solutions**. It demonstrates how a junior security analyst investigates suspicious activity, supports incident response, and recommends governance and risk-management controls.

The assignment covers two main areas:

1. **Security Operations Centre (SOC):** SIEM alert investigation, log correlation, threat intelligence, incident response, and post-incident reporting.
2. **Governance, Risk & Compliance (GRC):** risk identification, risk treatment, security policies, ISO 27001, and the NIST Cybersecurity Framework.

## 🚨 Incident Scenario

At **9:42 AM**, the SIEM system at TS Tech & Solutions headquarters raises a Priority-1 alert after detecting unusual outbound traffic from an internal workstation.

Within the hour, a second alert is generated: an employee account is attempting to log in from two different countries simultaneously.

As the junior analyst on call, the task is to investigate the alerts, determine whether the activity is malicious, support containment, and recommend improvements to the organisation's security controls.

### Incident indicators provided

| Indicator | Details |
|---|---|
| First alert | Unusual outbound traffic from an internal workstation |
| Second alert | Employee account login attempts from two countries |
| Locations identified | Lagos and London |
| Time difference | Approximately 3 minutes |
| Suspicious outbound IP | `45.33.32.156` |
| File hash | `d41d8cd98f00b204e9800998ecf8427e` |
| Suspicious domain | `update-service.ru` |

---

# PART A — SECURITY OPERATIONS (SOC)

## 1. SIEM Alert Investigation

When a SIEM alert is generated, the analyst should **investigate** it to determine whether it is a true positive or a false positive before taking further action.

For the unusual outbound traffic alert, the first step is to correlate the event with user login records and scheduled task activity. This provides context and helps determine whether the traffic is expected or suspicious.

## 2. Indicators of Compromise (IoCs)

The IP address, file hash, and suspicious domain supplied in the scenario are examples of **Indicators of Compromise (IoCs)**.

| Indicator | Example | Why it matters |
|---|---|---|
| IP address | `45.33.32.156` | Helps identify suspicious network communication and related activity |
| File hash | `d41d8cd98f00b204e9800998ecf8427e` | Can be searched to determine whether a file is associated with known malicious activity |
| Domain | `update-service.ru` | Can be investigated for reputation, registration details, and possible malicious associations |

IoCs help analysts connect events, investigate suspicious activity, and identify possible compromise.

## 3. NIST Incident Response Lifecycle

The assignment uses the following four phases in order:

<ol>
  <li><strong>Preparation:</strong> Establish incident response procedures, tools, roles, and readiness.</li>
  <li><strong>Detection and Analysis:</strong> Identify suspicious events, investigate alerts, and determine their significance.</li>
  <li><strong>Containment, Eradication and Recovery:</strong> Limit the incident, remove the threat, and restore affected systems.</li>
  <li><strong>Post-Incident Activity:</strong> Document lessons learned and improve security controls.</li>
</ol>

## 4. Impossible Travel Alert Analysis

The account compromise alert shows logins from Lagos and London within three minutes of each other.

This pattern suggests a possible **impossible travel** event, where the same account appears to access the system from geographically distant locations within an unusually short period.

The analyst should:

- Correlate login records with IP addresses, device information, and account activity.
- Verify the login attempts with the legitimate account owner through an appropriate channel.
- Review related authentication and endpoint logs.
- Initiate containment where compromise is suspected, including securing the account and resetting credentials.
- Enforce Multi-Factor Authentication (MFA).

## 5. Threat Intelligence and OSINT

The assignment identifies two OSINT sources for researching `update-service.ru`.

| OSINT Source | Purpose |
|---|---|
| VirusTotal | Check domain and file reputation, security-vendor detections, and related indicators |
| WHOIS Lookup | Review domain registration information, registrar details, registration dates, and available ownership information |

The assignment also asks about looking up a suspicious file hash using VirusTotal. This activity involves collecting and analysing threat intelligence; the precise lifecycle classification can depend on the intelligence process being followed.

## 6. Post-Incident Report Summary

> The SIEM alert identified suspicious account activity showing logins from Lagos and London within three minutes of each other, indicating a likely account compromise. Investigation and log correlation identified the activity as unauthorised access, which was facilitated by the lack of enforced Multi-Factor Authentication (MFA). The incident was contained by securing the affected account, and recommendations were made to implement MFA, strengthen monitoring, and improve security controls to ensure risk management.

---

# PART B — GOVERNANCE, RISK & COMPLIANCE (GRC)

## 7. Risk Management Process

The risk management process presented in the assignment is:

<div align="center">

**IDENTIFY RISK**  
⬇️  
**ASSESS RISK**  
⬇️  
**IMPLEMENT CONTROLS**  
⬇️  
**MONITOR & REVIEW**

</div>

| Stage | Description |
|---|---|
| Identify Risk | Identify security gaps, threats, vulnerabilities, and affected assets |
| Assess Risk | Evaluate the likelihood and potential impact of identified risks |
| Implement Controls | Apply appropriate safeguards to reduce or manage risks |
| Monitor & Review | Continuously evaluate controls and review changes in the risk environment |

The first step is **Identify Risk**.

## 8. NIST Cybersecurity Framework (CSF)

| NIST CSF Function | Description |
|---|---|
| Identify | Understand assets, risks, and vulnerabilities |
| Protect | Put safeguards and controls in place to prevent attacks |
| Detect | Continuously monitor for anomalies and suspicious events |
| Respond | Limit the impact once an attack is confirmed |
| Recover | Return to normal operations and improve after an incident |

## 9. Information Security Management System (ISMS)

An **Information Security Management System (ISMS)** is a structured set of policies, procedures, processes, and controls used by an organisation to manage and protect information security risks.

One example of a control TS Tech & Solutions should have implemented before the incident is **Multi-Factor Authentication (MFA)** for user accounts. MFA provides an additional layer of authentication and helps reduce the risk of unauthorised account access when passwords are compromised.

## 10. Applying the Risk Management Process to MFA

The absence of enforced MFA contributed to the account compromise risk. TS Tech & Solutions should address this gap through the following steps:

| Step | Action |
|---|---|
| Identify | Identify the absence of MFA as a security gap that increases the risk of unauthorised account access. |
| Treat | Implement MFA across user accounts and update access-control policies to make MFA mandatory. |
| Monitor | Continuously monitor authentication logs and security alerts to ensure MFA is being used correctly. |

## 11. ISO 27001 vs NIST Cybersecurity Framework

| ISO/IEC 27001 | NIST Cybersecurity Framework |
|---|---|
| An international standard for establishing, implementing, maintaining, and continually improving an ISMS | A flexible framework for understanding, assessing, prioritising, and managing cybersecurity risk |
| Includes requirements for an ISMS and can be used for certification | Provides cybersecurity outcomes and guidance that organisations can adapt |
| Focuses on a systematic information security management approach | Organises cybersecurity activities around Identify, Protect, Detect, Respond, and Recover |

**Key distinction:** ISO 27001 is a certifiable international standard focused on building an ISMS, while the NIST CSF is a flexible framework focused on managing cybersecurity risk.

## 12. Why Cybersecurity Is Also a Governance and Compliance Issue

Cybersecurity is not only a technical responsibility. It also requires management oversight, risk management, policies, accountability, and compliance with applicable standards and regulations.

In this scenario, the lack of enforced MFA represents both a technical weakness and a governance gap because the organisation did not adequately manage an important security control.

If GRC is ignored, an organisation may experience:

- Repeated security incidents and data breaches.
- Regulatory penalties and compliance failures.
- Financial losses and operational disruption.
- Damage to customer confidence and organisational reputation.

---

# RECOMMENDED SECURITY IMPROVEMENTS

| Priority Area | Recommended Improvement | Expected Benefit |
|---|---|---|
| Identity and Access Management | Enforce MFA for all user accounts | Reduces the risk of account compromise |
| SIEM Monitoring | Improve alert correlation and log monitoring | Supports earlier detection and investigation |
| Incident Response | Maintain and test an incident response procedure | Improves containment and recovery |
| Threat Intelligence | Use reputable OSINT sources to investigate IoCs | Supports threat identification and analysis |
| Risk Management | Conduct regular risk assessments | Helps identify and address security gaps |
| Security Governance | Establish and review security policies | Improves accountability and control management |

## Tools and Concepts Referenced

| Tool / Concept | Use in the Assignment |
|---|---|
| SIEM | Detecting and correlating security events |
| VirusTotal | Investigating suspicious file hashes and domains |
| WHOIS Lookup | Researching domain registration information |
| NIST Incident Response Lifecycle | Structuring incident response activities |
| NIST CSF | Organising cybersecurity risk-management activities |
| ISO 27001 | Establishing an Information Security Management System |
| MFA | Strengthening user authentication |

## Conclusion

This assignment demonstrates the relationship between Security Operations (SOC) and Governance, Risk & Compliance (GRC) in responding to a cybersecurity incident.

The unusual outbound traffic and simultaneous login activity from Lagos and London highlight the importance of SIEM monitoring, log correlation, threat intelligence, and effective incident response.

The absence of enforced Multi-Factor Authentication also demonstrates that technical security controls must be supported by organisational policies, risk management, and management oversight.

TS Tech & Solutions should strengthen authentication controls, improve security monitoring, maintain incident response procedures, and continuously review its security policies to reduce the likelihood and impact of future incidents.

---

## 📁 Suggested Repository Structure

```text
TS-TECH-SOLUTIONS-CYBERSECURITY-ASSIGNMENT/
│
├── README.md
│
├── evidence/
│   ├── siem-alert.png
│   ├── suspicious-login-activity.png
│   ├── virustotal-investigation.png
│   └── whois-domain-lookup.png
│
└── report/
    └── TS-Tech-Cybersecurity-Assignment.pdf
```

*The evidence filenames above are suggested placeholders. Add your actual screenshots and report before using the corresponding links.*

<details>
<summary><strong>View project learning objectives</strong></summary>

- Investigate and interpret SIEM alerts.
- Recognise and use Indicators of Compromise.
- Apply the incident response lifecycle.
- Explain the role of OSINT and threat intelligence.
- Identify and treat organisational cybersecurity risks.
- Explain the relationship between ISO 27001 and NIST CSF.
- Recommend security controls such as Multi-Factor Authentication.

</details>

<details>
<summary><strong>View author and assignment information</strong></summary>

| Field | Details |
|---|---|
| Organisation | TS Tech & Solutions |
| Programme | Cybersecurity Assignment |
| Cohort | Phoenix Cohort |
| Student | Adie Patrick Betiang |
| Main Domains | SOC and GRC |
| Scenario | Suspicious outbound traffic and possible account compromise |

</details>

---

<div align="center">

**TS TECH & SOLUTIONS | CYBERSECURITY ASSIGNMENT**  
**PHOENIX COHORT — ADIE PATRICK BETIANG**

*Prepared for educational and cybersecurity learning purposes.*

</div>
