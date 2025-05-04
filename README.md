# SOC338 - Lumma Stealer - DLL Side-Loading via Click Fix Phishing

This repository presents the investigation of a Lumma Stealer malware attack through DLL Side-Loading from a phishing email disguised as a “Click Fix” tool.

## Summary

- **Attack Type:** Malware via DLL Side-Loading
- **Initial Vector:** Phishing Email
- **Malware:** Lumma Stealer
- **Detection Method:** User reported suspicious behavior + EDR telemetry

## Key Findings

- A fake utility tricked a user into executing a malicious DLL
- Stealer collected browser credentials and system info
- Exfiltration via HTTP POST requests

## Screenshots

![Phishing Email](images/phishing_email.png)

## Log Samples

See [`logs/edr_logs.txt`](logs/edr_logs.txt)

## Analysis Report

See [`analysis_report.md`](analysis_report.md)

## Remediation

- Block the domain
- Train users on phishing awareness
- Deploy DLL protection mechanisms
