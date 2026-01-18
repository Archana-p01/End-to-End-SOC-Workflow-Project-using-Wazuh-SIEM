## UC4 – Successful RDP Brute Force Attack (Windows Agent)

### Objective
Detect and investigate a successful RDP brute force attack resulting in unauthorized access to a Windows system by correlating repeated failed authentication attempts followed by a successful logon using Wazuh SIEM.

---

### Environment
- **Monitored Host:** Windows System (Wazuh Agent)
- **SIEM Platform:** Wazuh
- **Attack Source:** External Host (Lab Simulation)
- **Detection Type:** Host-based (Windows Security Event Logs)
- **Target Service:** RDP (Port 3389)

---

### SOC Context
RDP brute force attacks are frequently used by attackers to gain initial access to Windows systems. A successful brute force attack represents a high-severity security incident, as it confirms credential compromise and unauthorized system access. Early detection and response are critical to limit attacker movement and impact.

---

### Step 1: Authentication Monitoring Setup
- Windows Security Event Logging is enabled.
- Wazuh agent is configured to collect authentication-related event logs.
- RDP-related logon and logoff events are monitored.
- Brute force detection rules and correlation logic are active.

---

### Step 2: Attack Simulation (Controlled Lab Scenario)
- Multiple failed RDP authentication attempts are generated against the Windows system using invalid credentials.
- After repeated failures, a successful RDP login occurs using compromised or weak credentials.
- This simulates a real-world scenario where brute force activity leads to successful access.

---

### Step 3: Detection and Alert Generation
- Wazuh detects repeated failed RDP authentication attempts from the same source IP.
- A successful RDP logon event is detected shortly after the failures.
- Correlation identifies a transition from failed attempts to successful authentication.
- Alerts include:
  - Source IP address
  - Target username
  - Failed and successful logon events
  - Timestamps
  - Rule ID and severity level

---

### Step 4: Alert Visibility
- Brute force and successful logon alerts are visible in the Wazuh Dashboard.
- Alerts are escalated due to confirmed unauthorized access.
- The incident is classified as a confirmed compromise.

---

### Step 5: SOC Investigation
The SOC analyst investigates:
- **Who accessed the system:** Username and source IP
- **How access was gained:** Repeated failed RDP logons followed by success
- **When compromise occurred:** Timestamp of successful logon
- **What followed:** Review of post-login activity, including process execution and file access
- **Scope:** Verification of lateral movement or additional compromised accounts

---

### Response Actions (Simulated)
- Affected system is isolated from the network.
- Compromised user account is disabled and credentials are reset.
- Source IP address is blocked at the firewall level.
- Additional monitoring is enabled for related accounts and systems.
- Incident is escalated according to SOC procedures.

---

### Evidence to Collect
- Screenshots of failed and successful RDP authentication alerts
- Windows Security Event IDs related to RDP logons
- Source IP address and compromised username
- Timeline showing failed attempts followed by successful access

---

### MITRE ATT&CK Mapping
- **TA0001 – Initial Access**
- **TA0006 – Credential Access**
- **T1110 – Brute Force**
- **T1078 – Valid Accounts**

---

### SOC Relevance
This use case demonstrates the SOC’s ability to detect credential compromise, correlate authentication failures with successful access, confirm system compromise, and initiate containment actions to prevent further attacker activity.
