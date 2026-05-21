# TICKET 6 — False Positive Classification (ALL DETECTIONS)

---

## Detection 1 — Excessive Failed Login Attempts (Single User)

### User Behavior False Positives
- Trying to enter the password in a hurry, making spelling mistakes  
- Forgot the recently changed password  
- Entering the password with capslock turned on or off  
- Using the old password saved in the system or google account  

### System Behavior False Positives
- Applications using the old credentials for automated tasks  
- Scheduled processes using expired credentials  

### Security / Noise False Positives
- Internal vulnerability scans  
- Red Team finding vulnerabilities  

### Noise Impact
Medium Noise  

### Reasoning
It happens regularly due to the human errors, admins testing the security, regular password change policy etc.  

---

## Detection 2 — Successful Login After Multiple Failures

### User Behavior False Positives
- User finally entering the correct password after missing a key  
- User forgot the new password and tried the old password multiple times before finally entering the current one  

### System Behaviour False Positives
- Automated authentication connection problem  
- Pause after multiple attempts of failed logins  

### Security / Noise False Positives
- Red team doing the investigations  

### Noise Impact
High  

### Reasoning
The behavior is really common during daily corporate life.  

---

## Detection 3 — Multi-User per IP (Password Spray Detection)

### User Behavior False Positives
- Shared office network  
- Different people using same system  
- One system different accounts  

### System Behavior False Positives
- VPN gateway  
- Proxy Server  

### Security / Noise False Positives
- Internal testing and audit  
- Red Team testing  

### Noise Impact
Medium  

### Reasoning
It is very common in offices where shared networks or shared computers are being used.  

---

## Detection 4 — Authentication Burst Activity

### User Behavior False Positives
- Morning login surge  
- Clockout time  
- Entering into the system to check the results of a test  
- Power outage error  

### System Behavior False Positives
- Connection error and restore after quite a while  
- The clock in/clock out system being fixed after some time  
- Website being down and then comes back up  

### Security / Noise False Positives
- Red team doing the testing  
- Load testing  
- Authentication health checks  

### Noise Impact
High  

### Reasoning
It can happen during system failure, power outage, authentication problem.  

---

## Detection 5 — Account Lockout Behavior

### User Behavior False Positives
- Entering the wrong password multiple times  
- Entering the old password multiple times  
- CapsLock being turned on/off during all the login attempts  
- Mobile devices continuously trying old saved passwords  

### System Behavior False Positives
- Mobile devices continuously trying old saved passwords  
- Authentication apps trying multiple login attempts automatically  
- Hidden process trying the old credentials continuously  

### Security / Noise False Positives
- Security assessment tools  
- Red Team testing  

### Noise Impact
Medium  

### Reasoning
Account lockouts are mainly caused by human error where a person tries to enter an outdated password from his memory.
