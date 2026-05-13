
# Brute Force Alert – Splunk Alert Engineering

### Scheduled Authentication Monitoring using Splunk Enterprise

---

## 1. Overview

This alert was created to identify repeated failed
Windows authentication attempts associated with
potential brute force activity.

The alert was developed in Splunk Enterprise
using SPL (Search Processing Language)
and scheduled monitoring.

The alert provides visibility into:

- Unauthorized login attempts
- Password spraying activity
- Credential guessing attacks
- Suspicious authentication behavior

---

## 2. Detection Query

```spl
index=wineventlog EventCode=4625 earliest=-5m latest=now
| stats count by Account_Name, host
| where count >= 5
| sort - count
```

---

## 3. Alert Configuration

| Setting | Value |
|---|---|
| Alert Type | Scheduled |
| Schedule | Every 5 minutes |
| Time Range | Last 5 minutes |
| Trigger Condition | Results greater than 0 |
| Trigger | Once |
| Throttling | 10 minutes |

---

## 4. Alert Workflow

The alert continuously monitors
Windows authentication failures.

If 5 or more failed login attempts
are detected against the same account
within a 5-minute window,
the alert triggers automatically.

The workflow enables rapid detection
of suspicious authentication behavior.

---

## 5. Alert Actions

The following alert actions were configured:

- Add to Triggered Alerts
- Display within Splunk monitoring workflow

---

## 6. Investigation Process

After alert generation, the investigation includes:

1. Review targeted usernames
2. Analyze failed login volume
3. Verify source systems
4. Correlate with successful logins
5. Investigate suspicious behavior patterns

---

## 7. MITRE ATT&CK Mapping

| Technique | Tactic | ATT&CK ID |
|---|---|---|
| Brute Force | Credential Access | T1110 |

---

## 8. Alert Validation

The alert was validated by generating
multiple failed authentication attempts
within the Windows lab environment.

The alert successfully triggered
after the configured threshold was reached.

---

## 9. Supporting Evidence

### Alert Configuration

```markdown
![Brute Force Query](../brute_force_query_results.png)
```

### Failed Login Events

```markdown
![Failed Login Logs](../failed_login_raw_logs.png)
```

### Triggered Alert

```markdown
![Triggered Alert](../brute_force_triggered_alert.png)
```

### Dashboard Visualization

```markdown
![Dashboard Panel](../brute_force_dashboard_panel.png)
```


---

## 10. Conclusion

This alert demonstrates practical SOC alert engineering
using Splunk Enterprise and Windows authentication telemetry.

The implementation provides automated monitoring
for suspicious brute force authentication activity.