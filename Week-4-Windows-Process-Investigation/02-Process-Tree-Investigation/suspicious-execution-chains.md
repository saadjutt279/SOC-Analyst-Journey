# TICKET 5 — Suspicious Execution Chains

## Normal Process Chain

explorer.exe → chrome.exe

### Why is this chain normal or suspicious?
This chain is normal because there is no activity visible which can result in being malicious. It is just google chrome being started up through user interface.

### What might the attacker be trying to do?
This does apply in this scenario, but it seems the user of the system is trying to boot up the google chrome though user interface.

### What evidence matters most?
Apparently, this chain does not look suspicious and most chances are it is a normal process chain so no evidence needed. But for the sake of argument, other processes can be checked in the same time frame to investigate further. But as an opinion of a SOC analyst, this is not an event worth escalating.

---

## Suspicious Process Chain

winword.exe → cmd.exe → powershell.exe

### Why is this chain normal or suspicious?
This is chain looks very suspicious, because a normal application Word is triggering command prompt cmd and then cmd is triggering powershell which is a stronger version of itself and is used to run scripts on system level.

### What might the attacker be trying to do?
Attacker had a malicious link or text or picture in the word document, which upon clicking or opening triggered a chain of multiple background processes which first started command prompt which eventually triggered powershell and most probably running a malicious script using powershell will be the next step by the attacker.

### What evidence matters most?
- The time of the processes being triggered  
- Did the attacker run any script using powershell, if so, what was its content.  
- Other processes started at the same time period.  
- Whether “SYSTEM” was logged on or a regular user logged in.  
- The contents of the script matter the most here, any encryption used, any obfuscation techniques being used.
