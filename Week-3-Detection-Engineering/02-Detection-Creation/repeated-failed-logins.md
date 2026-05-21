# TICKET 2 — Repeated Failed Logins (Brute Force Detection)

---

## 🎯 Detection Objective
Detect potential brute-force authentication attempts by identifying repeated failed login events occurring within a short time window against the same host or account.

---

## Detection Logic:
A threshold of 5 or more failed login attempts have to be made within 5 minutes time window and then grouped by the same host or account. 

---

## Detection Intent:
The intent is to differentiate between normal typo errors and attempted malicious login attempts.

---

## KQL Query:
```kql
Event
| where EventID == 4625
| summarize FailedAttempts = count()
    by Computer, bin(TimeGenerated, 5m)
| where FailedAttempts >= 5
| order by FailedAttempts desc
```

---

## Explanation:
The KQL query is divided into different parts. “Event” is the table where all the events are being stored. “where EventID == 4625” is the logic to get only those entries where login attempt was failed, “4625” is the failed login attempt code. In “summarize FailedAttempts = count()”, all those entries in the Event table which has EventID as 4625 are being counted and that count is being stored in a variable named as “FailedAttempts”. Which is then grouped in a 5 minutes window, so all those attempts which happened in a certain period of time (5 Minutes) like a burst will be grouped together. Now from that, as the intent was to differentiate malicious attempt, all the groups with number of failed attempts being 5 or more than 5 will be shown and in a descending manner.

---

## Attacker Scenario:
This detection logic can be used to where a suspicious element is trying to get into a system physically or through remote access, using password spraying, brute force or password guessing techniques. For example, a malicious person is trying to get into a locked system and he has physical access of the system as well. First he tries to guess the password as he has some knowledge of system’s owner. Then he tries password spraying. Finally he tries brute force technique which results in a lot of bursts of failed login attempts in a very short span of time. Which can be detected through the above mentioned logic and KQL query.
