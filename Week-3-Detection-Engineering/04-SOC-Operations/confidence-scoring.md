# TICKET 11 — Confidence Scoring

---

## Detection 1 — Excessive Failed Login Attempts (Single User)

### 1. High Confidence Attack
- External IP  
- Suspicious Time and Location  
- User unaware of the attempts  
- New device fingerprint  
- Unknown non trusted infrastructure  

### 2. Medium Confidence
- Confirmation of mistyped password by the user  
- Confirmation of old password entry by the user  
- Internal IP  
- Regular time and location  
- Known trusted infrastructure  

### 3. Low Confidence / Noise
- Red team testing  
- Regular network problem  

---

## Detection 2 — Successful Login After Multiple Failures

### 1. High Confidence Attack
- External IP  
- Suspicious Time and Location  
- User unaware of the attempts  
- New device fingerprint  
- Suspicious activity after login  
- Unknown non trusted infrastructure  

### 2. Medium Confidence
- Confirmation of mistyped password by the user  
- Confirmation of old password entry by the user  
- Internal IP  
- Regular time and location  
- Known trusted infrastructure  
- Successful login after multiple attempts  
- Normal process activity after login  

### 3. Low Confidence / Noise
- Red team testing  
- Regular network problem  

---

## Detection 3 — Multi-User per IP (Password Spray)

### 1. High Confidence Attack
- Irregular Time  
- Irregular IP and location  
- Unknown non trusted infrastructure  
- Rapid attempts  

### 2. Medium Confidence
- Regular Morning clock-in Rush  
- Shift change and clock-out time  
- Single system, multiple users  
- Same shared network  
- Known trusted infrastructure  
- VPN required and used  
- Regular IP and location  

### 3. Low Confidence / Noise
- Red Team testing  

---

## Detection 4 — Authentication Burst Activity (Login Spike)

### 1. High Confidence Attack
- Irregular time (Late night, middle of the shift)  
- Unknown non trusted infrastructure  
- Suspicious behavior  
- External IP  
- Success after multiple attempts  

### 2. Medium Confidence
- Known Trusted Infrastructure  
- Regular Time (Morning Rush, Shift change, Clock-out time)  
- Normal Behavior  
- Regular IP and location  
- Power Outage or System Failure  

### 3. Low Confidence / Noise
- Red Team Testing  
- System Glitch  
- Normal regular activity  

---

## Detection 5 — Account Lockout Behavior

### 1. High Confidence Attack
- Irregular behavior  
- Suspicious time and location  
- External IP  
- Success after multiple failed attempts  
- Unknown non trusted infrastructure  

### 2. Medium Confidence
- Normal behavior for the user  
- Service running in the background tried entering the old password multiple times  
- User confirmed they tried the wrong password multiple times  
- User confirmed they tried the old password multiple times  
- Known trusted infrastructure  
- Internal IP  
- Regular time and location  

### 3. Low Confidence / Noise
- Red team testing  
- Regular system behavior
