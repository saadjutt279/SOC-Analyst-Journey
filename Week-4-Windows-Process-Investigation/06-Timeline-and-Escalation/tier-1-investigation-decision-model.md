# TICKET 13 — Tier 1 Investigation Decision Model

Process Create:
RuleName: technique_id=T1083,technique_name=File and Directory Discovery  
UtcTime: 2026-05-25 17:41:50.007  
ProcessGuid: {884d4bfa-89de-6a14-1600-000000001a00}  
ProcessId: 1220  
Image: C:\Windows\System32\svchost.exe  
FileVersion: 10.0.26100.7705 (WinBuild.160101.0800)  
Description: Host Process for Windows Services  
Product: Microsoft® Windows® Operating System  
Company: Microsoft Corporation  
OriginalFileName: svchost.exe  
CommandLine: C:\WINDOWS\System32\svchost.exe -k LocalSystemNetworkRestricted -p -s PrintDeviceConfigurationService  
CurrentDirectory: C:\WINDOWS\system32\  
User: NT AUTHORITY\SYSTEM  
LogonGuid: {884d4bfa-89dc-6a14-e703-000000000000}  
LogonId: 0x3E7  
TerminalSessionId: 0  
IntegrityLevel: System  
Hashes: SHA1=D87367D5078C476B109DC3312B62781513330055,MD5=B1C5636EC08026FD0F8CCBFF49ED7E59,SHA256=44FD6F9347CEED5798A25C47167F335EF085AE4648A81F775DD4BDC6240D8189,IMPHASH=DE43BD45CC98C143357416C7519ECCFD  
ParentProcessGuid: {884d4bfa-89db-6a14-0b00-000000001a00}  
ParentProcessId: 812  
ParentImage: C:\Windows\System32\services.exe  
ParentCommandLine: C:\WINDOWS\system32\services.exe  
ParentUser: NT AUTHORITY\SYSTEM  

---

## Step 1 — Is it actionable?

No it is not actionable because there is not indication of any suspicious or malicious activity. There is no user driven activity and no abnormal execution chain.

---

## Step 2 — Evidence check

Strong benign indicators:
    • Parent: services.exe (Trusted system process)  
    • Child: svchost.exe (Microsoft Signed)  
    • Path: System32  
    • User: SYSTEM  
    • Coomand-line: normal service parameters  

---

## Step 3 — Tier decision

Tier 1 decision is to close this ticket as Benign. Because it is expected windows behavior, there are no indicators of compromise, and no abnormal execution patterns.

---

## Final SOC Escalation Model

Condition | Decision  
No suspicious behaviour | Close  
Slight anomalies | Monitor  
Obfuscated / unusual chain | Escalate to Tier 2
