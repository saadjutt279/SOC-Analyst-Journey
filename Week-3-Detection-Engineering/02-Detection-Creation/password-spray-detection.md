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

---

## Explanation:

The KQL query is divided into different parts. “Event” is the table where all the events are being stored. “where EventID == 4625” is the logic to get only those entries where login attempt was failed, “4625” is the failed login attempt code.  In “summarize FailedAttempts = count()”, all those entries in the Event table which has EventID as 4625 are being counted and that count is being stored in a variable named as “FailedAttempts”. Which is then grouped in a 5 minutes window and by difference of IP addresses, so all those attempts which happened in a certain period of time (5 Minutes) like a burst will be grouped together. Now from that, as the intent was to differentiate malicious attempt, all the groups with number of failed attempts being 5 or more than 5 will be shown and in a descending manner.

---

## Attacker Scenario:
This detection logic can be used when a malicious actor tries to access the account through a remote access (RDP) and has a different IP address than the actual system which is being hacked.


