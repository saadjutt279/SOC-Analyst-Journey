```md id="ir92ks"
# Investigation Reports

---

## Case 1 — Baseline Admin PowerShell

### Summary
A powershell process was launched interactively by the user through Windows Terminal. Analysis of process creation event identified no suspicious command line arguments, no obfuscation techniques, no stealth techniques, or encoded commands. The activity appears consistent with the normal user behavior.

### Evidence
Timestamp:  
2026-06-02 14:34:06 UTC  

User:  
WINVM01\WindowsVictim  

Parent Process:  
WindowsTerminal.exe  

Process:  
powershell.exe  

Command Line:  
C:\WINDOWS\System32\WindowsPowerShell\v1.0\powershell.exe  

Integrity Level:  
High  

MITRE ATT&CK:  
T1059.001 – PowerShell  

### Findings
• User-initiated launch  
• Windows Terminal as parent process  
• No suspicious command-line arguments  
• No encoded commands  
• No execution policy bypass  
• No hidden execution flags  
• No evidence of obfuscation  
• No unusual parent-child relationship  
• Interactive PowerShell session  

### Analyst Conclusion
The observed powershell activity is consistent with the normal user behavior. The process execution chain is expected, the command line shows no indication of obfuscation techniques, command encoding, and stealth or any other malicious behavior.  

### Classification
Benign  

### Confidence
High  

---

## Case 2 — Encoded PowerShell

### Summary
A powershell was launched interactively by the user through windows terminal. Analysis of process creation shows somewhat suspicious behavior as the command encoding was found during the inspection.

### Evidence
UtcTime:  
2026-06-02 22:25:24.185  

Image:  
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe  

CommandLine:  
"C:\WINDOWS\System32\WindowsPowerShell\v1.0\powershell.exe" -EncodedCommand VwByAGkAdABlAC0ASABvAHMAdAAgACIAUwBPAEMAIABXAGUAZQBrACAANQAgAFQAZQBzAHQAIgA=  

IntegrityLevel:  
High  

User:  
WINVM01\WindowsVictim  

ParentImage:  
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe  

### Findings
• Suspicious powershell activity  
• Command encoding  
• No obfuscation  
• No stealth  
• No execution policy bypass  
• No hidden windows  
• Normal Parent-Child chain  
• User initiated launch  

### Analyst Conclusion
The observed activity was found suspicious, though the parent-child process chain is expected, and no obfuscation techniques, and no stealth was found, command encoding was found which does not identify it as a malicious activity, further investigation is required.  

### Classification
Suspicious  

### Confidence
Medium  

---

## Case 3 — Stealth Execution

### Summary
A powershell activity was launched interactively through windows terminal. Analysis of process creation showed suspicious activity with the presence of command encoding, stealth techniques, and obfuscation methods.

### Evidence
UtcTime:  
2026-06-02 22:59:50.873  

Image:  
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe  

CommandLine:  
"C:\WINDOWS\System32\WindowsPowerShell\v1.0\powershell.exe" -ExecutionPolicy Bypass -WindowStyle Hidden -Command "Start-Sleep 10"  

User:  
WINVM01\WindowsVictim  

IntegrityLevel:  
High  

ParentImage:  
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe  

### Findings
• Suspicious powershell activity  
• Command encoding  
• Obfuscation techniques present  
• Stealth methods present  
• Execution policy bypass present  
• Hidden windows present  
• Normal Parent-Child chain  
• User initiated launch  

### Analyst Conclusion
This is highly suspicious and malicious powershell activity launched interactively through windows terminal. Malicious indicators were found such as command encoding, obfuscation techniques, stealth methods through hidden windows, and execution policy bypass.  

### Classification
Malicious  

### Confidence
High  

---

## Case 4 — Phishing to PowerShell

### Summary
An interactive powershell activity was launched through multiple phases like email content, to a word document, to command prompt to finally powershell. Analysis of process creation depicts suspicious activity due to the suspicious parent-child process chain.

### Evidence
Timeline:  
09:15:00 User receives email  
↓  
09:16:00 User opens Word document  
↓  
09:16:05 winword.exe launches cmd.exe  
↓  
09:16:06 cmd.exe launches powershell.exe  
↓  
09:16:08 PowerShell executes command  

### Possible attacker objective:
• Malicious script execution  
• Payload deployment  
• Data Exfiltration  
• Create a back door to access later  
• Credentials hijacking through keylogging  

### Additional evidence required:
• PowerShell command line  
• Network connections  
• Email metadata  
• Child processes  

### Findings
• User initiated process  
• Suspicious parent-child process chain  

### Analyst Conclusion
This is highly suspicious and malicious parent-child process chain, where the user interactively starts a chain with opening a malicious email, and its malicious contents into a word document, which included command prompt commands, which finally lands to the powershell activity. This whole chain is abnormal and should be further investigated.  

### Classification
Malicious  

### Confidence
High  
```

