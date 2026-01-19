## UC5 – Malicious Command Execution Detection (Ubuntu Agent)

### Objective
Detect suspicious or potentially malicious command execution on an Ubuntu Linux system using Wazuh log analysis and audit monitoring. This use case demonstrates how SOC teams identify attacker activity such as reconnaissance, privilege abuse, or post-compromise actions through command execution monitoring.

---

### Environment
- **Monitored Host:** Ubuntu Linux (Wazuh Agent)
- **SIEM Platform:** Wazuh
- **Detection Type:** Host-based (Audit Logs / Command Monitoring)
- **Log Source:** auditd / system logs
- **Attack Source:** Local execution (Lab Simulation)

---

### SOC Context
After gaining access to a system, attackers often execute commands to enumerate the environment, escalate privileges, or establish persistence. Monitoring command execution enables SOC teams to detect suspicious behavior early and respond before further damage occurs.

---

### Step 1: Command Monitoring Configuration
- The `auditd` service is installed and running on the Ubuntu system.
- Audit rules are configured to log command execution activity.
- Wazuh agent is configured to collect audit logs.
- Communication between the agent and Wazuh manager is verified.

---

### Step 2: Attack Simulation (Controlled Lab Scenario)
- Suspicious commands are executed locally on the Ubuntu system for testing purposes.
- Examples include:
  - User and system enumeration commands
  - Privilege-related commands
  - Access to sensitive system files
- These actions simulate post-compromise attacker behavior in a controlled environment.

---

### Step 3: Detection and Alert Generation
- Audit logs capture command execution events.
- Wazuh analyzes the logs and matches them against detection rules.
- Alerts are generated containing:
  - Executed command
  - Executing user
  - Timestamp
  - Hostname
  - Rule ID and severity level

---

### Step 4: Alert Visibility
- Command execution alerts are visible in the Wazuh Dashboard.
- Alerts are categorized as suspicious command execution or policy violations.
- High-risk commands are prioritized for investigation.

---

### Step 5: SOC Investigation
The SOC analyst investigates:
- **What command was executed:** Command name and arguments
- **Who executed the command:** User account
- **When it occurred:** Timestamp
- **Context:** Whether the command aligns with normal administrative activity
- **Correlation:** Presence of other indicators such as SSH login alerts or file changes

---

### Response Actions (Simulated)
- Command execution is reviewed and validated.
- User activity is audited for additional suspicious behavior.
- System integrity is verified.
- Incident is documented according to SOC procedures.

---

### Evidence to Collect
- Screenshot of command execution alert in Wazuh Dashboard
- Command name and execution details
- User account involved
- Timestamp and alert severity

---

### MITRE ATT&CK Mapping
- **TA0002 – Execution**
- **T1059 – Command and Scripting Interpreter**
- **T1087 – Account Discovery** (if enumeration observed)

---

### SOC Relevance
This use case demonstrates the SOC’s ability to detect post-access attacker activity through command execution monitoring, analyze audit logs, and correlate events to identify potential system compromise.
