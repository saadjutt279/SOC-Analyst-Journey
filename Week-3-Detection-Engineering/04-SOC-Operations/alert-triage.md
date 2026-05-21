# Detection 1 — Excessive Failed Login Attempts (Single User)

---

## Is it actionable?
Yes, multiple failed login attempts within a short span of time is suspicious and should be investigated.

---

## What evidence matters most?
- Account Name  
- IP address  
- Time of the attempts  
- Physical or remote access  
- Number of attempts  
- Total span of time for these failed attempts  

---

## First analyst step:
To confirm with the person through phone, or message or in person meeting about these attempts, but before that to check any successful login attempt after that to check whether the user got the access or not.

---

# Detection 2 — Successful Login After Multiple Failures

---

## Is it actionable?
Yes, a successful login after multiple failures could indicate the person got access to the account though brute force, password spray or password guessing. So it should be investigated. 

---

## What evidence matters most?
- Internal or External IP  
- Time of the attempts  
- Account Name  
- Processes created after login  
- Regular activity for this specific account at this hour or not  
- Physical or remote access  
- Number of attempts and total time span of those attempts before success  

---

## First analyst step:
Analyze the IP address to check whether it is internal or external. Does this user often do this, is this a regular activity for this user, and check was it accessed physically or through remote access. Then the processes created after successful login will be checked to see if any suspicious activity was done for example powershell was accessed by the user.  

---

# Detection 3 — Multi-User per IP (Password Spray Detection)

---

## Is it actionable?
Yes, multiple users are being logged into the system on the same IP address in a short span of time, this could indicate a password spray attack.

---

## What evidence matters most?
- IP addresses  
- User accounts  
- Power outage issue check  
- Website/Service problem check  
- Time of the login attempts  
- VPN Gateways  
- Known trusted infrastructure  

---

## First analyst step:
First step is to check the time of all those attempts because it is pretty normal during early morning clock in rush and during clock out times. Then any power outage, or any service problem will be checked to see whether that would have caused any problem. Then to check whether known trusted infrastructure was involved like VPN gateways, or shared networks.  

---

# Detection 4 — Authentication Burst Activity (Login Spike Detection)

---

## Is it actionable?
Yes, multiple accounts being logged on at the same time which is different than usual, is a suspicious activity and should be investigated.

---

## What evidence matters most?
- IP addresses  
- Number of accounts  
- Accounts names  
- Comparison with the usual activity  
- Known trusted infrastructure  
- Power outage issue check  
- Website/Service problem check  
- Time of the spike  

---

## First analyst step:
First step is to compare this spike with normal usual activity, if it is abnormal, than check the time of spike, whether it was time of morning clocking in, or clocking out or shift change. Then check the IP addresses and compare against known trusted infrastructure. Then check was there a problem with power outage or the login system.  

---

# Detection 5 — Account Lockout Behavior

---

## Is it actionable?
Yes, because the account lockout behavior only occurs after successive failed attempts without success.

---

## What evidence matters most?
- IP address  
- User Account Name  
- Known trusted infrastructure  
- Time of the activity  
- Comparison with the usual behavior  
- Indication of successful login after lockout  
- Internal or External IP  

---

## First analyst step:
First step is to check whether the IP was internal or external. Then is to check whether it was known trusted infrastructure or not. Then to check the time of activity and whether it was a normal activity for this specific user. Then check whether the account was successful logged into, if so what processes were created after logging in.
