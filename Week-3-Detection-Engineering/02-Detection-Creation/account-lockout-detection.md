**TICKET 5 — Account Lockout Behavior Detection**

---

**Detection Objective**  
Detect situations where repeated failed login attempts eventually lead to an account lockout, which may indicate brute-force or password guessing activity against a user account. 

---

**Detection Intent:**  
The purpose of this detection is to identify authentication activity that escalates from repeated login failures into an account lockout. This helps analysts spot possible brute-force attempts, password guessing attacks, or automated login abuse before further compromise occurs.

---

**Detection Logic**  
This detection looks for failed login attempts (Event ID 4625) along with account lockout events (Event ID 4740) in Windows Security logs. The idea is to observe the progression from multiple failed authentication attempts to a locked account. When both events occur for the same user account within a short period of time, it may indicate suspicious login activity rather than normal user behavior.

---

**KQL Query:**
```kql
SecurityEvent
| where EventID in (4625, 4740)
| project TimeGenerated, EventID, TargetUserName, Computer
| order by TimeGenerated desc
