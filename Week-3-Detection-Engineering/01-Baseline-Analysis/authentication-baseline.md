# WORKSTREAM 1 — TICKET 1
## 🧾 Authentication Baseline (FOUNDATION)

---

## 1. Normal User Mistakes

The pattern of normal user mistakes is observed on **13 May around 2:20 PM**, where **2 unsuccessful login attempts** were made.

Similar patterns were also seen on:
- 7 May  
- 8 May  
- 13 May (different times)

These events appear occasionally and are low in frequency.

**Conclusion:**  
Nothing can be stated with certainty, but the low and inconsistent frequency suggests these are likely normal user mistakes.

---

## 2. Burst Behavior

Burst behavior is observed at different times on **13 May**:
- 2:15 PM → 6 failed attempts  
- 2:25 PM → 6 failed attempts  
- 2:35 PM → 6 failed attempts  

Each burst contains exactly **6 unsuccessful attempts**, all targeting the same user account from the same IP address.

While this is a burst pattern, it does not necessarily indicate malicious activity or a brute force attack. It could also be explained by repeated manual login attempts, where Windows enforces a short lockout or delay after multiple failures.

### Higher Severity Burst
A more significant anomaly was observed on **8 May around 10:35 AM**, where:
- 11 consecutive failed login attempts occurred within approximately one minute

This pattern is abnormal and requires further investigation to determine intent and origin.

---

## 3. Repeated Identity Attempts

All failed login attempts share the same:
- Username  
- Source IP address  

This indicates repeated attempts against a single identity rather than distributed or multi-account targeting.

---

# BASELINE BEHAVIOR SUMMARY

## 1. Normal Failed Login Rate
- Typical authentication failures are low and occasional  
- Usually consist of **1–2 failed attempts within a short time window**

---

## 2. Burst Pattern Behaviour
- Multiple spikes detected:
  - 6 attempts
  - 8 attempts
  - 11 attempts  
- These exceed the normal baseline of 1–2 attempts

---

## 3. User Behavior Patterns
- Single or double failed attempts are considered normal and observed frequently  
- Burst patterns appear only occasionally across different days  
- No evidence of:
  - Distributed attacks across multiple accounts  
  - Multiple source IP addresses  

---

## 4. System / Service Behaviour
- No indication of service-account activity  
- No signs of automated authentication noise detected  

---

## Confidence Level of Baseline
**Medium Confidence**

Some patterns suggest suspicious login activity, but:
- Same IP address is consistently used  
- Same username is targeted repeatedly  

This could indicate:
- A physical user repeatedly attempting login with incorrect credentials  
- Rather than an external brute force attack
