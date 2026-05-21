# Step 1 — What happens if threshold is LOW?

## Would normal people trigger this?
Yes, if the threshold is low, normal people can trigger it as well. For example. If the threshold for a physical password guessing attack is 10 attempts per minutes, a person who is in a hurry, or drunk, or not in his sense, or a child just pressing random keys on a keyboard can trigger it. 

## Would systems trigger this?
Yes, if the threshold is low, system can trigger it as well. For example, a process in the system requires to access an account through automated login and has an outdated password saved in the memory. It can trigger the threshold every time the process runs.

## Would the SOC drown in alerts?
Yes, both False Positives and True Positives. Mainly with the huge number of false positives, due to the threshold being so low, anything can trigger it.

---

# Step 2 — What happens if threshold is HIGH?

## Could attackers avoid detection?
Yes, if the threshold is too high for a certain situation, attackers can avoid the detection. For example, in a small office with 10 employees, each tries to login at the same time in the morning, the threshold should be around 15 to 20 attempts in total, or 2 to 3 attempts per each employee. If the threshold is 100 or 500 failed attempts in a short span of time, that may be too high to detect a brute force, password guess or a password spray attack.

## Would stealthy behavior bypass the rule?
Yes, there is a big chance of stealthy behavior bypassing the rules. For example, in the office of 10 employees, if the threshold is 500 attempts per minute, a stealthy brute force attack with less attempts per minute, would definitely bypass it. 

## Would we miss early attack signals?
Yes, there is a chance of that as well. If the threshold is so high, it might take a huge number of attempts to trigger the threshold. Early symptoms of attack may show less number than the threshold.

---

# Step 3 — What feels realistic?

It mainly depends upon the environment for which the threshold being set. Size of the company, human computer interaction, familiarity with the interface, internet stability, previous record etc, all of these and others need to be considered before setting up a threshold in a certain situation. For example, a company in a backward area, and a company in a technical hub of the city will not have same internet stability thus different thresholds.

---

# Example Walkthrough

## Password Spray Detection
The detection idea to detect password spray attack is to check multiple accounts being used on same singular IP.

- If the threshold is too low, you will get constant notifications due to the shared network, office NAT, VPN gateway. For example 2 usernames per 10 minutes.

- If the threshold is too high, attackers can spray is slowly and spread the attack over many hours, now the system will miss the attack or atleast early indications of it. For example 50 username per 10 minutes.

- If the threshold is balanced, it can leave normal failed attempts caused by human or system error, and will only focus on the high number of attempts than usual. For example 10 username per 10 minutes.
