# CASE 2 — ENCODED POWERSHELL

## Simple Payload:
Write-Host "SOC Week 5 Test"

---

## Encoding:
[Convert]::ToBase64String([Text.Encoding]::Unicode.GetBytes('Write-Host "SOC Week 5 Test"'))

---

## Encoded Message:
VwByAGkAdABlAC0ASABvAHMAdAAgACIAUwBPAEMAIABXAGUAZQBrACAANQAgAFQAZQBzAHQAIgA=

---

## Execute the Encoded Command:
powershell.exe -EncodedCommand VwByAGkAdABlAC0ASABvAHMAdAAgACIAUwBPAEMAIABXAGUAZQBrACAANQAgAFQAZQBzAHQAIgA=

---

## Important Findings

### UtcTime:
2026-06-02 22:25:24.185  

### Image:
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe  

### CommandLine:
"C:\WINDOWS\System32\WindowsPowerShell\v1.0\powershell.exe" -EncodedCommand VwByAGkAdABlAC0ASABvAHMAdAAgACIAUwBPAEMAIABXAGUAZQBrACAANQAgAFQAZQBzAHQAIgA=  

### IntegrityLevel:
High  

### User:
WINVM01\WindowsVictim  

### ParentImage:
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe  

---

## Initial SOC Assessment

### What immediately makes this command more suspicious than Case 1?
Case 1 had just the powershell being triggered in the command line, whereas in case 2, it can be clearly seen powershell was executed with an encoded command. Encoded commands can be used to bypass the detection policies.

---

### What information is hidden from an analyst who only sees the command line?
The actual command which was encoded through Base64 encoding is hidden from the analyst, plus the important findings like time, integrity level, command line, image and parent image are also hidden from the analyst if the person chooses to see just the command line.

---

### What information remains visible despite the encoding?
Important findings like time, integrity level, command line, image and parent image can be seen despite the encoding which are important to make an assessment.

---

### Would you: Close / Investigate / Escalate and why?

I would investigate it before escalating or closing it. I would first check the timing and the user, if this is the regular time for this user. Then I would check the integrity level. Then I would check the image and parent image to check how the process was started. The process parent-child chain is one of the most important information at this point, so I would see if there is something suspicious about it. Then I will decode the command to finally check what is happening, and follow up on other processes which were started at the same time, to see what was going on after this command was executed, whether any new suspicious process was started or just routine activity. Then I will make my decision: if everything is normal, I will close it; if I find any suspicious activity like suspicious processes, suspicious parent-child process chain, or any other suspicious indicators, I will escalate it.
```

