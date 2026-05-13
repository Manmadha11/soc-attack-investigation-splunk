# SOC Attack Investigation using Splunk Enterprise

### Detection Engineering, Alerting, Dashboard Monitoring, and Incident Investigation

---

# Project Overview

This project demonstrates a complete
Security Operations Center (SOC)
attack investigation workflow
using Splunk Enterprise,
Windows telemetry,
PowerShell logging,
and Sysmon monitoring.

The lab simulates realistic attacker behavior
within an isolated environment
to validate:

- Detection engineering
- SIEM monitoring
- Alert generation
- Dashboard visualization
- Incident investigation
- MITRE ATT&CK mapping

---

# Project Objectives

The primary objectives of this project were to:

- Simulate real-world attack scenarios
- Collect and analyze Windows telemetry
- Develop Splunk detections and alerts
- Build SOC investigation workflows
- Create centralized monitoring dashboards
- Perform incident investigation and IOC extraction

---

# Technologies Used

| Technology | Purpose |
|---|---|
| Splunk Enterprise | SIEM platform |
| Splunk Universal Forwarder | Log forwarding |
| Windows 10 | Monitored endpoint |
| Sysmon | Advanced endpoint telemetry |
| PowerShell Logging | Script execution monitoring |
| Kali Linux | Attack simulation |
| SPL (Search Processing Language) | Detection engineering |

---

# Attack Scenario

The simulated attack chain included:

1. Multiple failed login attempts
2. Successful authentication
3. Privilege escalation
4. Encoded PowerShell execution
5. SIEM alert generation
6. SOC investigation workflow

---

# Architecture Workflow

```text
Kali Linux
     ↓ Attack Activity
Windows 10 + Sysmon
     ↓ Telemetry
Splunk Universal Forwarder
     ↓ Log Forwarding
Splunk Enterprise
     ↓
Dashboards + Alerts + Investigation
```

---

# Key Features

### Detection Engineering

- Brute force detection
- Login correlation detection
- Privilege escalation monitoring
- PowerShell execution monitoring

### Alert Engineering

- Scheduled SIEM alerts
- Authentication monitoring
- Correlated compromise detection
- Threat visibility automation

### Dashboard Engineering

- Authentication monitoring dashboard
- Privilege escalation visualization
- PowerShell monitoring panels
- Attack correlation visibility

### Incident Investigation

- Attack timeline reconstruction
- IOC extraction
- Windows event analysis
- MITRE ATT&CK mapping

---

# Detection Coverage

| Detection | Event Source |
|---|---|
| Brute Force Detection | Event ID 4625 |
| Successful Login Detection | Event ID 4624 |
| Privilege Escalation Detection | Event ID 4732 |
| PowerShell Detection | PowerShell Logs |
| Authentication Correlation | 4624 + 4625 |

---

# MITRE ATT&CK Mapping

| Technique | ATT&CK ID |
|---|---|
| Brute Force | T1110 |
| Valid Accounts | T1078 |
| Account Manipulation | T1098 |
| PowerShell | T1059.001 |

---

# Dashboard Overview

![SOC Dashboard](./soc_dashboard_overview.png)

---

# Project Structure

```text
soc-attack-investigation-splunk/
│
├── README.md
│
├── architecture/
│   ├── lab_architecture.md
│   └── network_flow.png
│
├── detections/
│   ├── brute_force_detection.md
│   ├── privilege_escalation.md
│   ├── account_creation.md
│   ├── powershell_detection.md
│   └── login_correlation.md
│
├── alerts/
│   ├── brute_force_alert.md
│   ├── privilege_escalation_alert.md
│   ├── powershell_alert.md
│   └── correlation_alert.md
│
├── dashboard/
│   ├── dashboard_overview.md
│   └── dashboard_panels.md
│
├── reports/
│   ├── incident_report.md
│   └── investigation_summary.md
│
├── mitre/
│   └── mitre_mapping.md
```

---

# Investigation Workflow

The SOC workflow included:

1. Attack simulation
2. Windows telemetry generation
3. Log forwarding
4. SIEM ingestion
5. Detection triggering
6. Alert generation
7. Dashboard monitoring
8. Incident investigation
9. IOC extraction
10. MITRE ATT&CK mapping

---

# Indicators of Compromise (IOCs)

| IOC Type | Value |
|---|---|
| Event ID | 4625 |
| Event ID | 4624 |
| Event ID | 4732 |
| PowerShell Indicator | -enc |
| Host | Windows 10 Endpoint |

---

# Skills Demonstrated

This project demonstrates practical experience with:

- SIEM engineering
- Splunk SPL
- Detection engineering
- Windows event analysis
- PowerShell monitoring
- Sysmon telemetry
- Alert engineering
- Dashboard visualization
- Incident investigation
- MITRE ATT&CK mapping

---

# Future Improvements

Planned future enhancements include:

- Advanced Sysmon detections
- Threat hunting dashboards
- Sigma rule integration
- Automated response workflows
- Multi-endpoint monitoring
- Threat intelligence enrichment
- SOAR integration

---

# Conclusion

This project demonstrates an end-to-end
SOC monitoring and investigation workflow
using Splunk Enterprise and Windows telemetry.

The implementation successfully simulated:
- authentication attacks
- privilege escalation
- suspicious PowerShell execution
- SIEM alert engineering
- SOC investigation workflows

The project provides practical experience
with real-world blue team operations
and detection engineering methodologies.
