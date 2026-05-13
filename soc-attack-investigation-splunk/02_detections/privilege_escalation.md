# Privilege Escalation Detection – Splunk Detection Engineering

### Administrative Group Monitoring using Windows Security Logs

---

## 1. Overview

This detection identifies users added to privileged Windows groups
using Windows Security Event Logs.

The detection was developed in Splunk Enterprise using SPL
(Search Processing Language) to monitor suspicious administrative
privilege escalation activity.

This detection provides visibility into:

- Unauthorized administrative access
- Privileged account abuse
- Persistence techniques
- Post-compromise privilege escalation

---

## 2. Detection Logic

The detection monitors Windows group membership modification events.

If a user is added to a privileged group such as:

- Administrators
- Remote Desktop Users
- Backup Operators

the activity is flagged for investigation.

### Detection Conditions

- Windows Event ID: `4732`
- Administrative group modification detected

---

## 3. Log Source

| Source | Description |
|---|---|
| Windows Security Logs | Group membership monitoring |

---

## 4. SPL Detection Query

```spl
index=wineventlog EventCode=4732
```

---

## 5. Investigation Workflow

The investigation process includes:

1. Identify modified privileged groups
2. Review affected usernames
3. Verify account legitimacy
4. Analyze authentication activity
5. Correlate with suspicious logins
6. Investigate persistence behavior

---

## 6. Alert Configuration

| Setting | Value |
|---|---|
| Alert Type | Scheduled |
| Schedule | Every 5 minutes |
| Trigger Condition | Results greater than 0 |
| Throttling | 10 minutes |

---

## 7. MITRE ATT&CK Mapping

| Technique | Tactic | ATT&CK ID |
|---|---|---|
| Account Manipulation | Persistence | T1098 |
| Valid Accounts | Defense Evasion | T1078 |

---

## 8. Detection Validation

The detection was validated by adding
a user account to the local Administrators group
within the Windows lab environment.

The detection successfully identified
privileged group modification activity.

---

## 9. Supporting Evidence

### Privilege Escalation Detection Query

```markdown
![Privilege Escalation Query](../privilege_escalation_query_results.png)


![Privilege Escalation Query](../privilege_escalation_query_results2.png)
```

### Raw Administrative Group Events

```markdown
![Privilege Escalation Logs](../privilege_escalation_raw_logs.png)
```

### Triggered Alert

```markdown
![Privilege Escalation Alert](../privilege_escalation_alert.png)
```

### Dashboard Visualization

```markdown
![Privilege Escalation Dashboard](../privilege_escalation_dashboard.png)

![Privilege Escalation Dashboard](../privilege_escalation_dashboard1.png)
```

---

## 10. Conclusion

This detection demonstrates practical SOC monitoring
for privileged account modification activity using
Windows Security telemetry and Splunk Enterprise.

The workflow improves visibility into
potential attacker persistence and privilege escalation behavior.