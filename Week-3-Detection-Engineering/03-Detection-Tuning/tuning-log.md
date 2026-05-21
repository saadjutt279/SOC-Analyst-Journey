# TICKET 8 — Detection Tuning Log

---

## Detection 1 — Excessive Failed Login Attempts (Single User)

### What I changed
I changed the threshold to a very high number of 3-5 attempts per minute to a realistic 8 attempts per minute.

### Why
Because the previous threshold was too strict, and was catching even the normal instances of people just forgetting the capslock is on/off, entering the password in a hurry and missing a key.

### What improved
The number of false positives are reduced, less logs to look into. High confidence on the threshold to generate meaningful results. 

### What worsened
A slow brute force attack might go undetected. 

---

## Detection 2 — Successful Login After Multiple Failures

### What I changed
I changed the threshold to a very high number of 4 attempts per minute to realistic 10 attempts per minute.

### Why
Because the previous threshold was too sensitive, and after 3 to 4 attempts people usually gets their password in case, the caps lock was on/off, they were entering 1 key wrong in all those attempts, they were entering the old password from their memory.

### What improved
The number of false positives are reduced, less logs to look into. High confidence on the threshold to generate meaningful results.

### What worsened
A slow brute force attack might go undetected. 

---

## Detection 3 — Multi-User per IP (Password Spray Detection)

### What I changed
I changed the threshold from 3 multiple users on a targeted IP to 10 users per minute.

### Why
Because previously, the threshold was too sensitive, and during the early morning rush, and during clock-out time, there were a lot of false positive alerts being triggered.

### What improved
The number of false positives are reduced, less logs to look into. High confidence on the threshold to generate meaningful results.

### What worsened
Low and slow password spray attacks may go undetected.

---

## Detection 4 — Authentication Burst Activity

### What I changed
I replaced a static threshold with a baseline-based detection (Dynamic comparison to normal authentication volumes)

### Why
Static threshold failed in an environment with peak login attempts, combined clock out attempts at the same time.

### What improved
Better adaptability to the real world, and now less false positives during the peak hours.

### What worsened
Requires continuous adjustments of the parameters.

---

## Detection 5 — Account Lockout Behavior

### What I changed
Replaced simple correlation logic with a more strict time-bound correlation between failed logins (4625) and lockout events (4740), ensuring both occur within a defined short window.

### Why
Previous logic was too broad and was capturing unrelated lockouts that were not attack-related or happened long after failed attempts.

### What improved
Stronger attack correlation accuracy and improved detection confidence for real brute-force progression patterns.

### What worsened
Some delayed lockout scenarios may be missed if the time window is too strict.
