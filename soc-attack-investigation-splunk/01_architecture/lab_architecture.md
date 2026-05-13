# Lab Architecture

## Overview

This lab simulates a real-world SOC investigation environment
using Splunk Enterprise, Windows telemetry, PowerShell logging,
and Sysmon endpoint monitoring.

The environment was designed to emulate enterprise-level
security monitoring and incident investigation workflows.

---

# Lab Components

| Component | Purpose |
|---|---|
| Windows 10 | Victim machine |
| Kali Linux | Attacker machine |
| Splunk Enterprise | SIEM platform |
| Splunk Universal Forwarder | Log forwarding |
| Sysmon | Endpoint telemetry |
| PowerShell Logging | Command execution visibility |

---

# Architecture Flow

```text
Kali Linux
     ↓
Windows 10 + Sysmon
     ↓
Splunk Universal Forwarder
     ↓
Splunk Enterprise SIEM
```

---

# Data Collection Workflow

## Windows Security Logs

The Windows Security Event Log was used to collect:

- Failed logins
- Successful logins
- Account creation events
- Privilege escalation events

Important Event IDs:

| Event ID | Description |
|---|---|
| 4625 | Failed login |
| 4624 | Successful login |
| 4720 | User account creation |
| 4732 | User added to privileged group |

---

# Sysmon Integration

Sysmon was deployed to improve endpoint visibility.

Telemetry collected included:

- Process creation
- Command-line activity
- PowerShell execution
- Parent-child process relationships

---

# Splunk Universal Forwarder

The Splunk Universal Forwarder was installed on the Windows system
to collect and forward logs into Splunk Enterprise.

Configured log sources included:

- Windows Security Logs
- PowerShell Logs
- Sysmon Operational Logs

---

# SIEM Platform

Splunk Enterprise was used as the centralized SIEM platform for:

- Log ingestion
- Detection engineering
- Alert creation
- Dashboard monitoring
- Timeline reconstruction
- IOC extraction

---

# Security Monitoring Goals

The lab was designed to simulate and investigate:

- Brute force attacks
- Account compromise
- Privilege escalation
- Persistence techniques
- PowerShell abuse
- Suspicious administrative activity

---

# Conclusion

This architecture provides centralized visibility into Windows
security telemetry and supports realistic SOC investigation workflows
using enterprise SIEM monitoring techniques.