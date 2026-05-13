# SOC Investigation Summary – Attack Detection and Analysis

### End-to-End Security Monitoring using Splunk Enterprise

---

# 1. Overview

This project demonstrates a complete
Security Operations Center (SOC)
investigation workflow
using Splunk Enterprise,
Windows Security telemetry,
PowerShell logging,
and Sysmon monitoring.

The environment was designed to simulate
real-world attack behavior
within an isolated cyber defense lab.

The project focused on:

- Authentication attack detection
- Privilege escalation monitoring
- Suspicious PowerShell execution
- SIEM alert engineering
- Incident investigation workflows

---

# 2. Lab Environment

The SOC lab environment consisted of:

| Role | System |
|---|---|
| Attacker System | Kali Linux |
| Victim Endpoint | Windows 10 |
| SIEM Platform | Splunk Enterprise |
| Log Forwarding | Splunk Universal Forwarder |
| Endpoint Monitoring | Sysmon |

---

# 3. Attack Simulation Workflow

The simulated attack followed a realistic
multi-stage intrusion workflow.

### Attack Stages

1. Multiple failed login attempts
2. Successful authentication
3. Privilege escalation
4. Suspicious PowerShell execution
5. SIEM alert generation
6. Incident investigation

---

# 4. Detection Engineering

The project included multiple detections
developed using Splunk SPL.

| Detection | Event Source |
|---|---|
| Brute Force Detection | Event ID 4625 |
| Successful Login Detection | Event ID 4624 |
| Privilege Escalation Detection | Event ID 4732 |
| PowerShell Detection | PowerShell Logs |
| Correlation Detection | 4624 + 4625 |

---

# 5. Alert Engineering

Scheduled alerts were developed
to automate threat detection workflows.

The alerting system enabled:

- Real-time authentication monitoring
- Privilege escalation visibility
- Suspicious PowerShell detection
- Correlated compromise identification

---

# 6. Dashboard Engineering

A centralized Splunk dashboard
was created to visualize:

- Failed login activity
- Successful authentication
- Privilege escalation behavior
- PowerShell execution activity
- Correlated attack patterns

The dashboard improved:
- SOC visibility
- investigation speed
- threat monitoring workflows

---

# 7. Investigation Findings

The investigation identified:

- Repeated failed authentication attempts
- Successful login activity
- Administrative privilege assignment
- Encoded PowerShell execution

The telemetry indicated
a simulated post-compromise intrusion workflow.

All malicious activity was successfully detected
within Splunk Enterprise.

---

# 8. Indicators of Compromise (IOCs)

| IOC Type | Value |
|---|---|
| Username | socadmin |
| Event ID | 4625 |
| Event ID | 4624 |
| Event ID | 4732 |
| PowerShell Indicator | -enc |
| Host | Windows 10 Endpoint |

---

# 9. MITRE ATT&CK Coverage

| Technique | ATT&CK ID |
|---|---|
| Brute Force | T1110 |
| Valid Accounts | T1078 |
| Account Manipulation | T1098 |
| PowerShell | T1059.001 |

---

# 10. Key Skills Demonstrated

This project demonstrates practical experience with:

- Splunk Enterprise
- SIEM monitoring
- Detection engineering
- Windows event analysis
- PowerShell logging
- Sysmon telemetry
- SOC alert engineering
- Incident investigation
- MITRE ATT&CK mapping
- Threat analysis workflows

---

# 11. Supporting Evidence

### SOC Dashboard Overview

```markdown
![Dashboard Overview](../soc_dashboard_overview.png)
```

### Authentication Monitoring Panel

```markdown
![Authentication Monitoring](../authentication_dashboard_panel.png)
```

### Privilege Escalation Monitoring

```markdown
![Privilege Escalation Monitoring](../privilege_dashboard_panel.png)
```

### PowerShell Monitoring

```markdown
![PowerShell Monitoring](../powershell_dashboard_panel.png)
```


---

# 12. Lessons Learned

This project provided hands-on experience with:

- Windows event telemetry analysis
- SIEM investigation workflows
- Authentication monitoring
- Threat detection engineering
- Incident response methodologies
- Security visualization techniques

The implementation improved understanding of:
- SOC operational workflows
- detection lifecycle management
- attack correlation analysis

---

# 13. Future Improvements

Future enhancements for this project include:

- Advanced Sysmon detections
- Threat hunting dashboards
- Sigma rule integration
- Automated response workflows
- Wazuh integration
- Threat intelligence enrichment
- Multi-endpoint monitoring
- SOAR automation

---

# 14. Conclusion

This project demonstrates an end-to-end
SOC monitoring and investigation workflow
using Splunk Enterprise and Windows telemetry.

The implementation successfully simulated
real-world attack behavior,
validated detection engineering capabilities,
and demonstrated practical SOC analyst investigation skills.

The project provides a strong foundation for:
- SOC analyst roles
- blue team operations
- detection engineering
- incident response workflows