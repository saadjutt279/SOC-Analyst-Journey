# Brute Force Attempt Detection (IP-based burst activity)

---

## 🎯 Detection Objective
Detect repeated failed authentication attempts from a single IP address within a short time window, indicating potential brute-force activity against a user account.

---

## Detection Logic:
A threshold of 5 or more failed login attempts have to be made within 5 minutes time window and then grouped by the same host or account. 

---

## Detection Intent:
The intent is to differentiate between normal typo errors and attempted malicious login attempts.

---

## KQL Query:
```kql
SecurityEvent
| where EventID == 4625
| summarize 
    FailedAttempts = count()
    by IpAddress, bin(TimeGenerated, 5m)
| where FailedAttempts >= 5
| order by FailedAttempts desc
```
## Explanation:

---

##
---
