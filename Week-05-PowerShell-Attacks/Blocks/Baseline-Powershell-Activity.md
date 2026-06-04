# BASELINE POWERSHELL ACTIVITY

## Summary
A powershell process was launched with the interaction of the user, through windows terminal. No suspicious commands were found. No indication of suspicious powershell activity like obfuscation, stealth, or encoded commands were found. 

## Evidence
UtcTime:  
2026-06-03 10:17:34.703  

Image:  
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe  

CommandLine:  
C:\WINDOWS\System32\WindowsPowerShell\v1.0\powershell.exe  

User:  
WINVM01\WindowsVictim  

IntegrityLevel:  
High  

ParentImage:  
C:\Program Files\WindowsApps\Microsoft.WindowsTerminal_1.24.11321.0_x64__8wekyb3d8bbwe\WindowsTerminal.exe  

## Baseline Characteristics
• Interactive execution  
• No obfuscation  
• No Stealth  
• No encoded commands  
• User initiated process  
• Standard powershell execution path  
• Normal Parent Child process  
• Expected user behavior  
• Visible execution  
• No defense evasion indicators  

## Findings
• User-initiated launch  
• Windows Terminal as parent process  
• No suspicious command-line arguments  
• No encoded commands  
• No execution policy bypass  
• No hidden execution flags  
• No evidence of obfuscation  
• No unusual parent-child relationship  
• Interactive PowerShell session  

## Assessment
Activity consistent with legitimate user-initiated PowerShell execution.  

## Classification
Benign  

## Confidence
High  

## Reasoning
This is an interactive powershell activity with no obfuscation, no command encoding, no stealth, no hidden windows, visible execution, parent-child process is normal. All indicators indicate towards a normal benign activity.
