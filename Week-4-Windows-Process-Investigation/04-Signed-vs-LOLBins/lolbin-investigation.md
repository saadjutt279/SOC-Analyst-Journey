# TICKET 9 — LOLBin Investigation

LOLBins are the living off the land binaries, which are the legitimate windows tools that attackers abuse for malicious purposes. As these binaries are already trusted by the system, they are loved by the attackers. Because the attackers don’t have to write obfuscation techniques, brilliant malwares to avoid detection, they can simply use manipulate of these LOLBins which are already trusted by the system  according to their advantage.  Following are some famous LOLBins. 

---

## 1. powershell.exe 

### Why attackers abuse it?
Powershell is LOLBin which is used for automation and scripting.  

why attackers abuse it
Attackers abuse powershell.exe because it is extremely powerful. It can scripts, download malwares, run directly in the memory without any trace and execute encoded commands.

how execution may appear suspicious
Execution may appear suspicious, when there are signs of command encoding, command obfuscation, policy bypassing techniques.

what evidence increases confidence
Evidence of a malicious activity regarding powershell can be found with encoded commands, execution policy bypass, long obfuscated commands, starting from word/chrome, and hidden windows. 

---

## 2. cmd.exe 

cmd.exe is a classic command line shell which is used for basic scripting, commands and troubleshooting. 

### why attackers abuse it
Attackers abuse it because it can launch powershell, execute scripts quietly, chain commands and launch different tools.

### how execution may appear suspicious
Execution of cmd.exe may appear suspicious when it is launching powershell, launching other tools, running chained commands, and running weird scripts.

### what evidence increases confidence
Suspicious batch files, unusual parent processes, network related commands, and execution from temp folders increase suspicion.

---

## 3. rundll32.exe 

rundll32.exe is a windows tool which is used to run .DLL files. It is normally used by windows internally.

### Why attackers abuse it
Attackers abuse it because it can run malicious DLL files while looking legitimate. This helps attackers in gaining stealth, evasion, and proxy execution.

### How execution may appear suspicious
Execution may appear suspicious when it is running unknown DLL files, DLLs are from the strange folders, and unusual command-line arguments.

### What evidence increases confidence
DLL from AppData/Temp, unsigned DLL, network activity and spawned by suspicious process can increase confidence.

---

## 4. mshta.exe 

mshta.exe is a windows tool used to run HTA applications (HTML Applications). Basically it is an internet explorer style scripting execution tool.

### Why attackers abuse it
Attackers abuse it because it can run malicious scripts, execute remote payloads, and bypass some protection.

### How execution may appear suspicious
Execution may appear suspicious when it is running scripts from the URLs, launching powershell, or executing HTA from temp folders.

### What evidence increases confidence
Presence of external URLs, obfuscated scripts, child Powershell process, and suspicious download behavior can increase confidence. 

---

## 5. certutil.exe 

certutil.exe is a windows certificate utility which is normally used for certificate management, and encoding and decoding files.

### Why attackers abuse it
Attackers abuse certutil.exe because it can download files from the internet, encode/decode payloads, and transfer malware.

### How execution may appear suspicious
Execution may appear suspicious when it is downloading files, decoding payloads, and unusual command-line arguments.

### What evidence increases confidence
External domain or IP, payload download, execution from temp files, and suspicious parent processes can increase confidence of this being used maliciously.
