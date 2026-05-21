# TICKET 4 — Login Spike Detection (Baseline Deviation)

---

## Detection Objective  
Detect abnormal spikes in failed login attempts by comparing current authentication failure activity against historical baseline behavior.

---

## Detection Intent  
Identify unusual authentication activity that may indicate brute-force attempts, credential abuse, or anomalous login behavior that deviates from normal system patterns.

---

## KQL Query:
```kql
let baseline =
SecurityEvent
| where EventID == 4625
| where TimeGenerated between (ago(7d) .. ago(1d))
| summarize avgFailures = count()
| project avgFailures;

SecurityEvent
| where EventID == 4625
| where TimeGenerated > startofday(now())
| summarize currentFailures = count()
| where currentFailures > (toscalar(baseline) * 2)
```

## Explanation:
This KQL query is divided into 2 parts, first part is where an object/variable is being created to store the average failures from the past 6 days. The second part is where current day’s failures are being counted and compared with the average of the previous 6 days.

## Attacker Scenario:
A system that normally experiences low failed login activity suddenly generates a significantly higher number of failed login attempts within a short period of time. This may occur during a brute-force attack, automated credential guessing, or repeated authentication retries caused by misconfigured services or scripts.
