# TICKET 10 — ESCALATION DECISION MODEL

---

## Detection 1 — Excessive Failed Login Attempts (Single User)

### Tier 1 handle (monitor/close)
- User confirms they mistyped password  
- User confirms they entered the old password  
- Attempts were made from a normal IP  
- Normal behavior for this user  
- Timing was regular  
- IP address was internal  

### Tier 2 escalate (investigate deeper)
- External IP detected  
- Timing was irregular  
- User was not aware of this  
- Unknown non trusted infrastructure  
- New device fingerprint  

### Ignore (noise)
- Multi-Factor authentication  
- Regular occurrence of error  

---

## Detection 2 — Successful Login After Multiple Failures

### Tier 1 handle (monitor/close)
- User confirmation of wrong password entry  
- User confirmation of capslock being on/off  
- User confirmation of old password entry  
- Internal Normal IP  
- Regular timing  
- User’s normal behavior  

### Tier 2 escalate (investigate deeper)
- External IP  
- Irregular location and time  
- User denies these attempts  
- Successful login after multiple failed attempts  
- Suspicious activity after login  

### Ignore (noise)
- Multi-Factor authentication  
- A process trying old passwords on a regular time intervals  

---

## Detection 3 — Multi-User per IP (Password Spray)

### Tier 1 handle (monitor/close)
- Regular Morning clock-in Rush  
- Shift change and clock-out time  
- Single system, multiple users  
- Same shared network  
- Known trusted infrastructure  
- VPN required and used  
- Regular IP and location  

### Tier 2 escalate (investigate deeper)
- Irregular Time  
- Irregular IP and location  
- Unknown non trusted infrastructure  
- Rapid attempts  

### Ignore (noise)
- Red Team testing  

---

## Detection 4 — Authentication Burst Activity (Login Spike)

### Tier 1 handle (monitor/close)
- Known Trusted Infrastructure  
- Regular Time (Morning Rush, Shift change, Clock-out time)  
- Normal Behavior  
- Regular IP and location  
- Power Outage or System Failure  

### Tier 2 escalate (investigate deeper)
- Irregular time (Late night, middle of the shift)  
- Unknown non trusted infrastructure  
- Suspicious behavior  
- External IP  
- Success after multiple attempts  

### Ignore (noise)
- Red Team Testing  
- System Glitch  
- Normal regular activity  

---

## Detection 5 — Account Lockout Behavior

### Tier 1 handle (monitor/close)
- Normal behavior for the user  
- Service running in the background tried entering the old password multiple times  
- User confirmed they tried the wrong password multiple times  
- User confirmed they tried the old password multiple times  
- Known trusted infrastructure  
- Internal IP  
- Regular time and location  

### Tier 2 escalate (investigate deeper)
- Irregular behavior  
- Suspicious time and location  
- External IP  
- Success after multiple failed attempts  
- Unknown non trusted infrastructure  

### Ignore (noise)
- Red team testing  
- Regular system behavior
