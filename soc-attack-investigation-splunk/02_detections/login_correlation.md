# Login Correlation Detection – Splunk Detection Engineering

### Failed and Successful Authentication Correlation using Windows Security Logs

---

## 1. Overview

This detection correlates multiple failed authentication attempts
followed by a successful login against the same user account.

The detection was developed in Splunk Enterprise using SPL
(Search Processing Language) to identify potential
successful brute force compromise activity.

This detection provides visibility into:

- Successful brute force attacks
- Credential compromise attempts
- Suspicious authentication patterns
- Account takeover behavior

---

## 2. Detection Logic

The detection monitors:

- Failed authentication events
- Successful authentication events

If multiple failed logins are followed
by a successful login for the same account,
the activity is flagged as suspicious.

### Detection Conditions

- Windows Event ID `4625` → Failed Login
- Windows Event ID `4624` → Successful Login
- Failed login threshold ≥ 5
- Successful login detected

---

## 3. Log Source

| Source | Description |
|---|---|
| Windows Security Logs | Authentication activity monitoring |

---

## 4. SPL Detection Query

```spl
index=wineventlog (EventCode=4624 OR EventCode=4625)
| stats count(eval(EventCode=4625)) as failed count(eval(EventCode=4624)) as success by Account_Name
| where failed >=5 AND success >=1
```

---

## 5. Investigation Workflow

The investigation process includes:

1. Identify targeted accounts
2. Review failed authentication volume
3. Verify successful login activity
4. Analyze authentication timestamps
5. Investigate source systems
6. Correlate with privilege escalation or PowerShell activity

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
| Brute Force | Credential Access | T1110 |
| Valid Accounts | Defense Evasion | T1078 |

---

## 8. Detection Validation

The detection was validated by generating:

- Multiple failed login attempts
- Followed by a successful login

within the Windows lab environment.

The correlation query successfully identified
suspicious authentication behavior.

---

## 9. Supporting Evidence

### Login Correlation Detection Query


![Login Correlation Query](../login_correlation_query_results.png)


### Failed and Successful Login Events


![Authentication Logs](../authentication_correlation_logs.png)


### Triggered Alert


![Correlation Alert](../login_correlation_alert.png)


### Dashboard Visualization


![Correlation Dashboard](../login_correlation_dashboard.png)


---

## 10. Conclusion

This detection demonstrates practical SOC correlation analysis
using Splunk Enterprise and Windows authentication telemetry.

The workflow improves visibility into
potential successful brute force compromise activity.
