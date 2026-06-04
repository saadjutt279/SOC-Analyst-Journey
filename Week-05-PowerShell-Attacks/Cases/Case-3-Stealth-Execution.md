# CASE 3 — STEALTH EXECUTION

## PowerShell Command:
powershell.exe -ExecutionPolicy Bypass -WindowStyle Hidden -Command "Start-Sleep 10"

---

## Important Findings

### UtcTime:
2026-06-02 22:59:50.873  

### Image:
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe  

### CommandLine:
"C:\WINDOWS\System32\WindowsPowerShell\v1.0\powershell.exe" -ExecutionPolicy Bypass -WindowStyle Hidden -Command "Start-Sleep 10"  

### User:
WINVM01\WindowsVictim  

### IntegrityLevel:
High  

### ParentImage:
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe  

---

## Initial SOC Assessment

### Why would an attacker use ExecutionPolicy Bypass?
An attacker would use ExecutionPolicy bypass because it prevents the system from performing the normal policy checks which are part of PowerShell execution policy settings, which helps prevent accidental script execution, script signing enforcement and other controls. Using ExecutionPolicy bypass disables these checks for that session.

---

### Why would an attacker use -WindowStyle Hidden?
An attacker would use WindowStyle Hidden to hide the execution window and prevent it from appearing on the screen. This allows scripts to run in the background without user visibility, reducing chances of detection.

---

### Which looks more suspicious to you: EncodedCommand or -ExecutionPolicy Bypass -WindowStyle Hidden, and why?
Both are suspicious, but -ExecutionPolicy Bypass -WindowStyle Hidden is more suspicious because it is strongly associated with stealth and evasion techniques.

---

### Would you: Close / Investigate / Escalate and what evidence would influence that decision?

I would investigate it before escalating or closing it. I would first check the timing and the user, if this is the regular time for this user. Then I would check the integrity level. Then I would check the image and parent image to understand how the process was started. The process parent-child chain is one of the most important indicators, so I would assess if anything looks suspicious. Then I would analyze the command in detail and review other processes created around the same time to determine whether any suspicious activity followed. Finally, I would make a decision: if everything appears normal, I would close it; if I find suspicious processes, abnormal parent-child relationships, or other indicators of malicious activity, I would escalate it. Any evidence of suspicious activity during or after execution would influence this decision.
```

