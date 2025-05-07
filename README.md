# SOC338 - Lumma Stealer - DLL Side-Loading via Click Fix Phishing

This project documents my investigation into a simulated security incident on the LetsDefend platform, where a user was targeted by a phishing campaign masquerading as a Windows 11 upgrade offer. The attack led to the deployment of the Lumma Stealer malware, emphasizing the importance of vigilance against social engineering tactics.

## 🧠 Key Takeaways

- **Identified** a phishing email impersonating a legitimate Windows 11 upgrade offer.
- **Analyzed** the deployment and behavior of the Lumma Stealer malware.
- **Investigated** endpoint activities to trace the infection chain.
- **Utilized** threat intelligence tools to gather Indicators of Compromise (IOCs).
- **Implemented** containment and remediation strategies to mitigate the threat.

---

## 🛡️ Incident Overview

- **Alert Name:** SOC338 - Fake Windows 11 Upgrade
- **Detection Time:** April 5, 2025
- **Affected User:** Dylan
- **Severity Level:** High
- **MITRE ATT&CK Techniques:**
  - T1566.002 – Spearphishing Link
  - T1204.002 – User Execution: Malicious File
  - T1059.001 – Command and Scripting Interpreter: PowerShell
  - T1055 – Process Injection
  - T1005 – Data from Local System

---

## 🔍 Investigation Steps

### 1. Dissecting the Phishing Email

The user received an email from `update@windows-update.com` with the subject "Upgrade to Windows 11 for Free." The email contained multiple "Update Now" buttons linking to a domain mimicking Microsoft's official site. Email header analysis revealed discrepancies in the sender's domain and SMTP origin, confirming the phishing attempt.

### 2. Payload Delivery and Execution Behavior

Upon clicking the link, the user downloaded an executable disguised as a Windows 11 installer. Execution of this file triggered the `mshta.exe` process,

