# TICKET 10 — Sysmon Process Telemetry Investigation

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

## Sysmon Investigation Summary

### Event Type
Process Creation (Sysmon Event ID 1)  
This event shows a new process being created on the system.

---

## Most Useful Investigation Fields

### 1. Image
C:\Windows\System32\svchost.exe  
It shows which executable was launched, and in this case it was svchost.exe, which is a legitimate windows system process.

### 2. CommandLine
C:\WINDOWS\System32\svchost.exe -k LocalSystemNetworkRestricted -p -s PrintDeviceConfigurationService  
It shows exactly how the process was executed. Important observations are it is running as a windows service using expected service arguments, and the behavior appears legitimate as well.

### 3. ParentImage
C:\Windows\System32\services.exe  
It shows which process launched svchost.exe. It is important because services.exe launching svchost.exe is very normal.

### 4. User
NT AUTHORITY\SYSTEM  
It shows which account executed the process, SYSTEM account is normal for many windows services.

### 5. Hashes
SHA256=44FD6F9347CEED5798A25C47167F335EF085AE4648A81F775DD4BDC6240D8189  
It is useful for malware identification, IOC Matching, and threat intelligence lookup.

### 6. CurrentDirectory
C:\WINDOWS\system32\  
It is useful because it shows execution location. This path is normal and expected for legitimate windows services.

---

## High-Value Telemetry

This Sysmon event provides:
    • process creation visibility  
    • command-line logging  
    • parent-child relationship visibility  
    • hash visibility  
    • user context  
    • execution path visibility  

Useful for:
    • malware investigations  
    • suspicious process detection  
    • PowerShell investigations  
    • process chain analysis  

---

## Investigation Assessment

Observed chain of services.exe to svchost.exe is a normal Windows background service behavior. It is expected execution path, SYSTEM context, legitimate windows directory and no obvious suspicious indicators were observed.

---

## Limitations / Gaps

Legitimate windows activity may still appear suspicious, because Sysmon alone can not confirm malicious intent, and analyst context is still required for accurate conclusions.
