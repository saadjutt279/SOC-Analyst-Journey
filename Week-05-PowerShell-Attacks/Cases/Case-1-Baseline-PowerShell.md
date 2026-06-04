# Case 1 Analysis

## What happened?
A powershell was launched:

Image:  
powershell.exe  

by:  
ParentImage: WindowsTerminal.exe  

under:  
WINVM01\WindowsVictim  

at:  
2026-06-02 14:34:06 UTC  

---

## Important Findings

### 1. Parent Process
Expected:  
explorer.exe  

Reality:  
WindowsTerminal.exe  

Which is normal  

---

### 2. Command Line
C:\WINDOWS\System32\WindowsPowerShell\v1.0\powershell.exe  

No suspicious activity here. No Encoded commands, no execution policy bypass, no WindowsStyle Hidden.  

---

### 3. User Context
WINVM01\WindowsVictim  

---

### 4. Integrity Level
High  

---

### 5. MITRE ATT&CK Tag
T1059.001  
PowerShell  

---

## Initial SOC Assessment

### Classification:
Benign  

---

### Reasoning:
Interactive powershell session launched manually from windows terminal.  
No obfuscation detected.  
No suspicious arguments found.  
No trace of stealth, bypass or encoded arguments.  
Activity consistent with legitimate windows administrative usage.
