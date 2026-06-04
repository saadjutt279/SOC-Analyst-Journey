# KQL Detections

## Encoded PowerShell
Detect PowerShell processes using encoded commands.  
Logic:  
Identify PowerShell command lines containing "-EncodedCommand"

---

## Hidden Execution
Detect attempts to hide the execution of powershell commands.  
Logic:  
Identify PowerShell command lines containing "-Windows Hidden"

---

## Execution Policy Bypass
Detect attempts to bypass execution policy to evade detection.  
Logic:  
Identify PowerShell command lines containing "-ExecutionPolicy bypass"

---

## Office → PowerShell Chain
Detect office applications spawning powershell.  
Logic:  
ParentProcess: WindWord.exe  
ChildProcess: powershell.exe
```

