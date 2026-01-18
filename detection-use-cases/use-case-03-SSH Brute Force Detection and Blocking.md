## UC3 – SSH Brute Force Detection and Blocking (Ubuntu Agent)

### Objective
Detect and respond to SSH brute force attacks targeting a Linux server by monitoring repeated failed authentication attempts using Wazuh SIEM. This use case demonstrates how SOC teams identify credential access attempts and prevent unauthorized access.

---

### Environment
- **Monitored Host:** Ubuntu Server (Wazuh Agent)
- **SIEM Platform:** Wazuh
- **Attack Source:** Kali Linux (Attacker Simulation)
- **Detection Type:** Host-based (Authentication Logs)
- **Target Service:** SSH (Port 22)

---

### SOC Context
SSH brute force attacks are a common initial access technique used by attackers to compromise Linux systems. Early detection of repeated authentication failures allows SOC teams to block attackers before credentials are compromised.

---

### Step 1: SSH Log Monitoring Configuration
- SSH authentication logs are enabled on the Ubuntu server.
- Wazuh agent is configured to monitor `/var/log/auth.log`.
- Relevant Wazuh rules for SSH authentication failures are enabled.
- Agent connectivity with Wazuh Manager is verified.

---

### Step 2: Attack Simulation
- From the Kali Linux machine, repeated SSH login attempts are made against the Ubuntu server using invalid credentials.
- Multiple usernames and passwords are attempted within a short time frame.
- This simulates a real-world SSH brute force attack.

---

### Step 3: Detection and Alert Generation
- Wazuh detects multiple failed SSH authentication attempts.
- Brute force detection rules are triggered based on frequency thresholds.
- Alerts include:
  - Source IP address
  - Target username
  - Number of failed attempts
  - Timestamp
  - Rule ID and severity level

---

### Step 4: Alert Visibility
- SSH brute force alerts are displayed in the Wazuh Dashboard.
- Repeated alerts from the same source IP indicate a coordinated attack.
- Alerts are categorized as authentication abuse or credential access attempts.

---

### Step 5: SOC Investigation
The SOC analyst investigates:
- **Who is attacking:** Source IP address
- **What is targeted:** SSH service and user accounts
- **Attack pattern:** Frequency and duration of failed login attempts
- **Correlation:** Verification that no successful SSH login occurred during the attack window

---

### Response Actions (Simulated)
- Source IP address is blocked using host-based firewall controls.
- Targeted user account is monitored for further activity.
- Incident is documented according to SOC procedures.

---

### Evidence to Collect
- Screenshot of SSH brute force alert in Wazuh Dashboard
- Source IP address and targeted username
- Number of failed login attempts
- Timestamp and alert severity

---

### MITRE ATT&CK Mapping
- **TA0006 – Credential Access**
- **T1110 – Brute Force**

---

### SOC Relevance
This use case demonstrates the SOC’s ability to detect credential-based attacks, validate brute force activity through log analysis, and apply containment actions to prevent unauthorized system access.
