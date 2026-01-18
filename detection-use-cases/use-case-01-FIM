## UC1 – File Integrity Monitoring (FIM) | Ubuntu Agent

### Objective
Detect unauthorized or unexpected modifications to critical system files on a Linux server using Wazuh File Integrity Monitoring (FIM). This use case simulates insider threats, privilege abuse, or persistence techniques commonly observed in real-world attacks.

---

### Environment
- **Monitored Host:** Ubuntu Linux (Wazuh Agent)
- **Detection Tool:** Wazuh File Integrity Monitoring (FIM)
- **Critical Files Monitored:**  
  `/etc/passwd`, `/etc/shadow`, `/etc/sudoers`, `/root`
- **Attack Source:** Local modification (simulated)

---

### Detection Setup
- Configured monitored files and directories in `ossec.conf`
- Verified FIM module was enabled on the agent


---

### Baseline Creation
Wazuh created a baseline of monitored files, capturing their initial state.  
All future changes are compared against this baseline to detect integrity violations.

---

### Attack Simulation
A critical system file was manually modified: sudo nano /etc/passwd
This simulates unauthorized administrative access or insider misuse.

---

### Detection & Alert
- Wazuh detected the file modification
- A FIM alert was generated and forwarded to the Wazuh Manager
- Alert details included:
  - File path
  - Type of change
  - Timestamp
  - Rule ID
  - Severity level

---

### SOC Investigation & Triage
The alert was analyzed to determine:
- **What changed:** Critical system file modified
- **Where:** Ubuntu Agent
- **When:** Timestamp from alert
- **Severity:** Medium
- **Validation:** Change reviewed to determine authorization

**Outcome:**  
Classified as a **True Positive** due to unauthorized modification.

---

### Evidence Collected
- Screenshot of FIM alert from Wazuh Dashboard
- Modified file name
- Timestamp of modification
- Wazuh Rule ID

---

### MITRE ATT&CK Mapping
- **T1565.001 – Stored Data Manipulation**

---

### Response (Simulated)
- Validate change with system owner
- Restore file to known-good state if unauthorized
- Escalate incident per SOC escalation procedures

---

### SOC Relevance
- Demonstrates real-time detection of system integrity violations
- Enables early identification of insider threats and privilege abuse
- Prevents attackers from escalating privileges or establishing persistence

---
