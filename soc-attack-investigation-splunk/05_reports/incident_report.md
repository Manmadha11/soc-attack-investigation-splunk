# Security Incident Report – SOC Attack Investigation

### Brute Force, Privilege Escalation, and PowerShell Execution Investigation

---

# 1. Executive Summary

A simulated cyber attack was conducted
within the SOC lab environment
to validate detection engineering,
security monitoring,
and incident investigation workflows.

The investigation identified:

- Multiple failed authentication attempts
- Successful account compromise
- Privileged group modification activity
- Suspicious PowerShell execution

The attack chain simulated a realistic
post-compromise intrusion scenario.

All malicious activity was successfully detected
using Splunk Enterprise and Windows telemetry.

---

# 2. Incident Overview

| Field | Details |
|---|---|
| Incident Type | Credential Access / Privilege Escalation |
| Severity | High |
| Environment | Windows 10 SOC Lab |
| SIEM Platform | Splunk Enterprise |
| Log Sources | Windows Security Logs, PowerShell Logs, Sysmon |
| Detection Status | Successful |
| Investigation Status | Completed |

---

# 3. Attack Scenario

The attack simulation followed a multi-stage intrusion workflow.

The attacker performed:

1. Brute force authentication attempts
2. Successful account login
3. Privilege escalation
4. Suspicious PowerShell execution

The activity generated telemetry
that was collected and analyzed
within Splunk Enterprise.

---

# 4. Attack Timeline

| Time | Activity |
|---|---|
| 09:10 | Multiple failed login attempts detected |
| 09:12 | Successful authentication observed |
| 09:15 | User added to Administrators group |
| 09:18 | Encoded PowerShell command executed |
| 09:20 | Alerts triggered within Splunk |

---

# 5. Detection Summary

| Detection | Status |
|---|---|
| Brute Force Detection | Triggered |
| Login Correlation Detection | Triggered |
| Privilege Escalation Detection | Triggered |
| PowerShell Detection | Triggered |

---

# 6. Investigation Findings

The investigation confirmed suspicious authentication behavior
followed by privilege escalation activity.

The following behaviors were identified:

- Repeated failed logins
- Successful authentication after brute force attempts
- Administrative privilege modification
- Encoded PowerShell execution

The attack chain demonstrated
potential attacker persistence
and post-compromise execution behavior.

---

# 7. Indicators of Compromise (IOCs)

| IOC Type | Value |
|---|---|
| Username | socadmin |
| Event ID | 4625 |
| Event ID | 4624 |
| Event ID | 4732 |
| PowerShell Indicator | -enc |
| Host | Windows 10 Endpoint |

---

# 8. Log Analysis

## Failed Authentication Events

```spl
index=wineventlog EventCode=4625
```

---

## Successful Authentication Events

```spl
index=wineventlog EventCode=4624
```

---

## Privilege Escalation Events

```spl
index=wineventlog EventCode=4732
```

---

## PowerShell Execution Events

```spl
index=powershell ("*-enc*" OR "*-encodedcommand*")
```

---

# 9. MITRE ATT&CK Mapping

| Technique | Tactic | ATT&CK ID |
|---|---|---|
| Brute Force | Credential Access | T1110 |
| Valid Accounts | Defense Evasion | T1078 |
| Account Manipulation | Persistence | T1098 |
| PowerShell | Execution | T1059.001 |

---

# 10. Supporting Evidence

### SOC Dashboard Overview


![Dashboard Overview](../soc_dashboard_overview.png)


### Authentication Monitoring Panel


![Authentication Monitoring](../authentication_dashboard_panel.png)


### Privilege Escalation Monitoring


![Privilege Escalation Monitoring](../privilege_dashboard_panel.png)


### PowerShell Monitoring


![PowerShell Monitoring](../powershell_dashboard_panel.png)


---

---

# 11. Root Cause Analysis

The simulated intrusion was initiated
through repeated failed authentication attempts
against a Windows account.

Following successful authentication,
administrative privileges were assigned,
allowing elevated access within the environment.

Suspicious PowerShell execution activity
was then observed,
indicating potential malware execution behavior.

---

# 12. Recommendations

The following security improvements are recommended:

- Implement account lockout policies
- Monitor privileged group changes
- Enable centralized PowerShell logging
- Deploy enhanced endpoint monitoring
- Implement multi-factor authentication
- Conduct continuous SIEM monitoring

---

# 13. Conclusion

This investigation demonstrates practical SOC analyst workflows
using Splunk Enterprise and Windows telemetry.

The project successfully simulated:

- Authentication attacks
- Privilege escalation
- Suspicious PowerShell execution
- SIEM-based detection engineering
- Incident investigation workflows

The implementation provides hands-on experience
with real-world SOC monitoring and analysis techniques.
