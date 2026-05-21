# TICKET 12 — MITRE Mapping Notes

---

## Detection 1 — Excessive Failed Login Attempts (Single User)

### Technique
Brute Force: ID T1110 

### Explanation
Multiple failed login attempts can be observed as a brute force attack, where multiple login attempts were made on a single user. 

### Linked Detection
Excessive Failed Login Attempts (Single User)

---

## Detection 2 — Successful Login After Multiple Failures

### Technique
Brute Force: ID T1110 

### Explanation:
A successful login attempt after multiple failed login attempts can be observed as a brute force attack, where multiple login attempts were made on a single user and finally a password attempt was successful. 

### Linked Detection
Successful Login After Multiple Failures

---

## Detection 3 — Multi-User per IP (Password Spray)

### Technique
Password Spray ID: T1110.003 Sub-technique of: T1110

### Explanation
Logging into multiple users from the same IP can indicate a possible password spray attack which itself a form of a brute force attack. 

### Linked Detection
Multi-User per IP (Password Spray)

---

## Detection 4 — Authentication Burst Activity (Login Spike)

### Technique
T1110 — Brute Force  
Possible automation / credential stuffing behavior 

### Explanation
Large authentication spikes over a short span of time can indicate automated credential attacks such as, credential stuffing, brute force, scripted authentication attempts. 

### Linked Detection
Authentication Burst Activity (Login Spike)

---

## Detection 5 — Account Lockout Behavior

### Technique
T1110 — Brute Force  
Attack progression indicator 

### Explanation
Trying multiple password entering attempts and failing each time on a short of span can cause account lockout, which can indicate a possible brute force attack, credential stuffing, and scripted authentication attempts. 

### Linked Detection
Account Lockout Behavior
