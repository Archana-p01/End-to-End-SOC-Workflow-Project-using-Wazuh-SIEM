# End-to-End-SOC-Workflow-Project-using-Wazuh-SIEM
End-to-end SOC lab implementing real-world detection use cases using Wazuh SIEM, Suricata IDS, and VirusTotal integration, covering log analysis, threat detection, investigation, and incident reporting.

## Project Overview
This project demonstrates a *real-world, end-to-end Security Operations Center (SOC) workflow* using *Wazuh SIEM*.  
It focuses on detecting, investigating, and responding to common cyber attacks across *Linux and Windows environments*, combining host-based monitoring, network intrusion detection, threat intelligence, and structured incident reporting.

The project is designed to reflect how SOC analysts operate in an enterprise environment — from alert generation to investigation and documentation.

---

## Project Objectives
- Build a centralized SOC monitoring environment using Wazuh SIEM  
- Detect real-world attacks such as brute force, reconnaissance, and malicious activity  
- Correlate host-based and network-based security events  
- Perform alert triage and investigation following SOC best practices  
- Document incidents using professional SOC incident report formats  

---

## SOC Architecture Overview
The project follows a *centralized SOC architecture*:

- *Wazuh Manager & Dashboard (Ubuntu Server)*  
  Central SIEM for log ingestion, analysis, correlation, and visualization  

- *Ubuntu Agent*  
  Host-based monitoring with network intrusion detection  

- *Windows Agent*  
  Endpoint monitoring for authentication abuse, malware, and suspicious activity  

- *Kali Linux*  
  Attacker simulation for generating real-world attack scenarios  

> Network-based alerts are generated using *Suricata IDS* and centralized in Wazuh for correlation.

---

## Tools & Technologies
- *Wazuh SIEM* (Manager, Agents, Dashboard)  
- *Suricata IDS* (Network intrusion detection)  
- *Ubuntu Linux & Windows OS*  
- *Kali Linux* (Attack simulation)  
- *VirusTotal Threat Intelligence Integration*  
- *MITRE ATT&CK Framework*  

---

## Detection Use Cases Implemented

| Use Case | Description | Platform |
|--------|-------------|----------|
| UC1 | File Integrity Monitoring (Critical system files) | Ubuntu |
| UC2 | Network Intrusion Detection (Reconnaissance & Scanning) | Ubuntu |
| UC3 | SSH Brute Force Detection & Blocking | Ubuntu | 
| UC4 | RDP Brute Force Detection | Windows |
| UC5 | Malicious Command Execution Detection | Ubuntu |
| UC6 | Vulnerability Detection | Linux / Windows |
| UC7 | Malware Detection using VirusTotal | Linux / Windows |

Each use case includes:
- Attack simulation  
- Alert detection  
- SOC investigation steps  
- Evidence collection  
- Incident reporting  

---

## Incident Response & Reporting
All detected incidents are documented using *SOC-grade incident report formats*, including:
- Incident summary  
- Detection details  
- Investigation and analysis  
- Impact assessment  
- Response actions (simulated)  
- Lessons learned  
- MITRE ATT&CK mapping  

Incident reports are available in the incident-reports/ directory.

---

## SOC Dashboard & Visibility
The Wazuh Dashboard provides:
- Real-time security alerts  
- Authentication abuse visibility  
- Network intrusion alerts  
- File integrity violations  
- Endpoint and host-based threat monitoring  

Screenshots of alerts and dashboards are included in this repository.

---

## Learning Outcomes
- Hands-on experience with *SOC operations*  
- Practical exposure to *SIEM alerting and investigation*  
- Understanding of *attack techniques and detection logic*  
- Experience correlating network and endpoint security events  
- Professional incident documentation aligned with SOC workflows  

---
