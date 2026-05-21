**WORKSTREAM 1 — TICKET 1**
🧾 **Authentication Baseline (FOUNDATION)**

**1. Normal user mistakes** 
Pattern of normal user mistakes is shown on 13 May around 2:20 PM where 2 unsuccessful attempts were made. Same pattern emerged on 7 May, 8 May, and on 13 May on different times. Nothing can be said with certainty but the frequency suggests these were normal user mistakes.

**2. Burst behavior**
Burst behavior is shown during different times on 13 May at 2:15PM, 2:25PM, 2:35PM. The number of unsuccessful attempts were 6 to be exact on all 3 times. It is burst pattern, but does not necessarily mean a malicious activity or any brute force attack. It can be an attempt to log into the account through physical means as after 6 attempts, Windows asks the user to wait for a few minutes to retry. These attempts were made on the same user account and from the same IP.
Biggest burst behavior was shown on 8 May around 10:35 AM where 11 consecutive attempts were made in a minute which indicates an abnormal activity. Further investigation will be held to understand the cause.

**3. Repeated Identity Attempts**
Same username and IP is involved in all the of failed attempts made on the account.

---

**BASELINE**
**Baseline Behavior Summary**

**1. Normal failed login rate:** 
Normal observed authentication failures were low and occasional, usually consisting of 1-2 failed attempts being made on a short span of time.

**2. Burst pattern behaviour:** 
Different spikes of 6, 8 and 11 failed attempts were discovered during the analysis. Which are more than usual attempts of 1 or 2.

**3. User behavior patterns:** 
Single or 2 failed attempts show normal behavior, which was seen on multiple different times and days. Repetition pattern only emerges on a few occasions where a burst like pattern emerges. No evidence yet of distributed attempts across multiple accounts or multiple source Ips.

**4. System / service behaviour:** 
No clear service-account or automated authentication noise was observed during this analysis. 

**Confidence level of baseline:**
Confidence level of baseline: Medium  
Some patterns were shown of suspicious login attempts, but the IP and username were always same which could indicate a physical login attempt being failed multiple times due to password not being known to the person making the attempt.
