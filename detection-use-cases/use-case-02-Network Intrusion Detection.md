## UC2 – Network Intrusion Detection (Suricata IDS + Wazuh)

### Objective
Detect network-based attacks such as reconnaissance and intrusion attempts using Suricata IDS and analyze those alerts centrally in Wazuh SIEM. This use case simulates how SOC teams identify early-stage attacker behavior before host-level compromise occurs.

---

### Environment
- **Network Sensor:** Ubuntu Agent with Suricata installed  
- **SIEM Platform:** Wazuh  
- **Attack Source:** Kali Linux (Attacker Simulation)  
- **Detection Type:** Network-based (IDS)  
- **Example Attacks:** Port scanning, suspicious TCP connections  

---

### SOC Context
Many attacks begin with network reconnaissance before exploitation. Detecting scanning and probing activity allows SOC teams to identify attackers early and take preventive action before systems are compromised.

---

### Step 1: Suricata as Network IDS
- Suricata is configured on the Ubuntu agent to inspect live network traffic.
- Network traffic is matched against IDS signatures to detect suspicious behavior.
- Suricata generates alerts and writes them to the `eve.json` log file.
- Wazuh collects and analyzes Suricata IDS alerts centrally.

---

### Step 2: Attack Simulation
- A network scan is performed from the Kali Linux machine against the Ubuntu agent.
- Multiple ports and services are targeted to simulate attacker reconnaissance.
- This activity represents an attacker enumerating services prior to exploitation.

---

### Step 3: Detection and Alert Generation
- Suricata detects abnormal traffic patterns associated with scanning behavior.
- IDS rules are triggered and alerts are generated.
- Alerts include:
  - Source IP address
  - Destination IP address
  - Protocol
  - Alert signature
  - Severity level
- Wazuh ingests these alerts and displays them in the dashboard.

---

### Step 4: Alert Visibility
- The SOC analyst observes Suricata IDS alerts in the Wazuh Dashboard.
- Multiple alerts originating from the same source IP indicate reconnaissance activity.
- Alerts are categorized as network intrusion or suspicious traffic events.

---

### Step 5: SOC Investigation
The SOC analyst investigates:
- **Who is attacking:** Source IP address
- **What is the behavior:** Port scanning or suspicious network connections
- **Which system is targeted:** Ubuntu Agent
- **Correlation:** Verification of any host-level activity by correlating with SSH or FIM alerts

---

### Evidence to Collect
- Screenshot of Suricata alert displayed in the Wazuh Dashboard
- Alert signature or message
- Source and destination IP addresses
- Timestamp and alert severity

---

### MITRE ATT&CK Mapping
- **TA0043 – Reconnaissance**
- **T1046 – Network Service Scanning**

---

### SOC Relevance
This use case demonstrates the SOC’s ability to detect early-stage network threats, correlate IDS alerts with endpoint activity, and identify attacker intent before system compromise occurs.
