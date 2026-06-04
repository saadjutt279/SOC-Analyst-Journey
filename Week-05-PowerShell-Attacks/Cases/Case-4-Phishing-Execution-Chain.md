# CASE 4 — PHISHING → OFFICE → POWERSHELL ATTACK CHAIN

## Scenario:
Assume the following alert arrives in your SIEM:  
winword.exe  
    ↓  
cmd.exe  
    ↓  
powershell.exe  

---

## Timeline:
09:15:00 User receives email  
↓  
09:16:00 User opens Word document  
↓  
09:16:05 winword.exe launches cmd.exe  
↓  
09:16:06 cmd.exe launches powershell.exe  
↓  
09:16:08 PowerShell executes command  

---

## Initial SOC Assessment

### Why is the chain suspicious?
This chain is suspicious because normal powershell execution chains start from user starting it from the GUI, or similar path. In this case, it is being started from email to word, to cmd and then to powershell. It is not a normal process chain.

---

## Possible attacker objective:
• Malicious script execution  
• Payload deployment  
• Data Exfiltration  
• Create a back door to access later  
• Credentials hijacking through keylogging  

---

## Additional evidence required:
• PowerShell command line  
• Network connections  
• Email metadata  
• Child processes  

---

## Potential Email Security Controls:

• Email filtering / anti-phishing systems  
  - Blocks malicious emails before delivery  

• Attachment sandboxing  
  - Executes attachments in isolated environment to detect malicious behavior  

• Safe Links / URL protection  
  - Inspects and blocks malicious URLs at click time  

• Office macro and script execution controls  
  - Prevents Word/Excel from executing PowerShell via macros  

• User awareness training  
  - Reduces likelihood of opening phishing attachments  

---

## Initial SOC Assessment

### Decision:
Escalate  

---

### Reasoning:
The Office → cmd → PowerShell chain is a common phishing execution pattern and requires immediate investigation.
