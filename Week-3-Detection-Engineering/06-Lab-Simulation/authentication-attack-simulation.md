# TICKET 13 — Authentication Attack Simulation

---

## 1. Human Error (Benign)


- Slow, random typos  
- Caps Lock turned on/off  
- Old depreciated passwords being used  
- Kids playing with the locked system  

### Pattern Characteristics
- Random intervals  
- Regular time and location  
- Low number of attempts  
- User confirms activity  

### Classification:
Benign/Noise  

---

## 2. Slow Wrong Password Attempts (Low-and-Slow Attack)


- 1 attempt per 30-60 seconds  
- 10-20 attempts in total  

### Pattern Characteristics
- Consistent Timing  
- Consistent intervals  
- External IP and location  
- User unaware of the activity  
- Same user  

### Classification:
Medium / Suspicious  

---

## 3. Brute Force (Rapid Single-Account Failures)


- 10-15 failures per minute  
- Bursts of login attempts during different intervals  
- Same User  
- Same IP  

### Pattern Characteristics
- High Speed  
- High Volume  
- Short time window  

### Classification:
High confidence attack  

---

## 4. Password Spray (Multiple Users, Same IP)


- Same IP  
- Many users  
- Same password  
- 1 attempt per user  

### Pattern Characteristics
- Wide user spread  
- Low attempts per user  
- High number per IP  

### Classification:
High confidence attack  

---

## 5. System Noise (Background / Service Logins)


- Service accounts retrying  
- Mobile devices retry loops  
- applications/Processes using old depreciated credentials  

### Pattern Characteristics
- Predictable timing  
- Trusted internal IP and location  
- Repeating pattern  

### Classification:
Low confidence / Benign / Noise  

---

## Pattern Comparison Table

| Pattern | Benign Example | Malicious Example | Key Difference |
|--------|----------------|------------------|----------------|
| Human Error | Typos, old password | None | Random, slow, user-confirmed |
| Slow Wrong Passwords | User struggling | Low-and-slow attacker | Intent + consistency |
| Brute Force | None | Rapid failures | Speed + volume |
| Password Spray | None | 1 password → many users | User spread |
| System Noise | Service account retries | None | Predictable + repetitive |
