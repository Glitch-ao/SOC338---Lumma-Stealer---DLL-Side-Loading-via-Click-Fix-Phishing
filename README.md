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

- **Alert Name:** SOC338 - Lumma Stealer - DLL Side-Loading via Click Fix Phishing
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

Upon clicking the link, the user downloaded an executable disguised as a Windows 11 installer. Execution of this file triggered the `mshta.exe` process, which is often exploited to run malicious scripts. This behavior indicated the deployment of the Lumma Stealer malware, designed to harvest sensitive user data and communicate with a Command and Control (C2) server.

### 3. Investigating Endpoint Activity

Using LetsDefend's Endpoint Security module, I examined the process tree and identified the malicious process spawned by `mshta.exe`. Further analysis of browser history and DNS logs corroborated the timeline of the infection. Although the phishing site was inactive during the investigation, threat intelligence tools provided historical data confirming its malicious nature.

### 4. Containment and Host Remediation

Immediate actions included isolating the affected host from the network, terminating malicious processes, and deleting the downloaded executable. A full system scan was conducted to ensure no residual threats remained. User credentials were reset, and security policies were reviewed to prevent future incidents.

---

## 🧰 Tools & Techniques Used

- **LetsDefend Platform:** For alert monitoring and endpoint analysis.
- **VirusTotal & Hybrid Analysis:** To assess the malicious payload.
- **MITRE ATT&CK Framework:** For mapping adversary techniques.
- **PowerShell & Command Line Analysis:** To trace execution paths.
- **Threat Intelligence Platforms:** For gathering IOCs and historical data.

---

## 📝 Recommendations

- **User Education:** Regular training on identifying phishing attempts.
- **Email Filtering:** Implement advanced email security solutions to detect and block malicious content.
- **Application Whitelisting:** Restrict execution of unauthorized applications.
- **Regular Updates:** Ensure all systems and applications are up-to-date with the latest security patches.
- **Incident Response Plan:** Develop and regularly update an incident response plan to handle potential threats effectively.

---

## 📸 Screenshots & Artifacts

*(Include relevant screenshots such as email headers, process trees, and analysis reports.)*

---
