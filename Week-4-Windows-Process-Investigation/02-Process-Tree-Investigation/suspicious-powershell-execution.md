# TICKET 4 — Suspicious PowerShell Execution

Powershell Investigation:

Image: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe  
CommandLine: powershell.exe -nop -w hidden -enc SQBFAFgA…  
User: WINVM01\WindowsVictim  
ParentImage: C:\Windows\explorer.exe  
IntegrityLevel: Medium  

---

## 1. Parent Process Analysis

Windows explorer is the parent process here, which means someone manually opened and executed the powershell command. This can be both normal and suspicious based on further investigation.

---

## 2. Command-line arguments

The commad line arguments include the following:

- -nop: No Profile which is used to avoid user settings  
- -w hidden: Windows Hidden which means stealth, no open windows  
- -enc: Base64 Encoding Powershell command is encoded to obfuscation.

---

## 3. Interactive vs scripted execution

Its origin is interactive as it was executed manually using the powershell but its work is scripted. Which is a malicious pattern.

---

## 4. Encoded command behavior

Yes, the command is encoded with base64 to hide payload, or avoid detection.

---

## 5. Suspicious Indicators List

- -nop: No Profile  
- -w hidden: Windows Hidden  
- -enc: Base64 Encoding  
- Explorer triggering powershell  
- User account logged in  
- IntegrityLevel: Medium  

---

## 6. Attacker Scenario

Normal user opens a file or a website and a hidden malware triggers powershell in the background and runs to command. Executes the command silently and payload runs in the memory.

---

## 7. Classification

Final classification highly suspicious powershell execution, with strong obfuscation techniques and chances of being triggered with user interaction.
