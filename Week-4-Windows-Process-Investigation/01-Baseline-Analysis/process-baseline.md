# WORKSTREAM 1 — WINDOWS PROCESS BASELINING

## 🧾 TICKET 1 — Windows Process Behavior Baseline

---

# 1. explorer.exe

explorer.exe is commonly associated with interactive user activity and is usually launched after user logon. It frequently acts as a parent process for applications started manually by the user.

## Common normal child processes:
- explorer.exe → chrome.exe  
- explorer.exe → notepad.exe  
- explorer.exe → cmd.exe  
- explorer.exe → powershell.exe  
- explorer.exe → msedge.exe  

## Normal behaviour observations:
- Usually tied to active user sessions  
- Commonly launches GUI applications  
- Command-line arguments are usually simple or absent  
- Interactive execution is expected  

## Assessment:
Normal and expected for user-driven activity.

---

# 2. cmd.exe

## Process Create:
RuleName: technique_id=T1083,technique_name=File and Directory Discovery  
UtcTime: 2026-05-23 10:51:17.821  
ProcessGuid: {884d4bfa-86a5-6a11-6501-000000001800}  
ProcessId: 6304  
Image: C:\Windows\System32\cmd.exe  
FileVersion: 10.0.26100.8328 (WinBuild.160101.0800)  
Description: Windows Command Processor  
Product: Microsoft® Windows® Operating System  
Company: Microsoft Corporation  
OriginalFileName: Cmd.Exe  
CommandLine: C:\WINDOWS\system32\cmd.exe /c ""C:\Program Files\VMware\VMware Tools\resume-vm-default.bat""  
CurrentDirectory: C:\WINDOWS\system32\  
User: NT AUTHORITY\SYSTEM  
LogonGuid: {884d4bfa-8f65-6a0c-e703-000000000000}  
LogonId: 0x3E7  
TerminalSessionId: 0  
IntegrityLevel: System  
Hashes: SHA1=8EFFECCD068002141AEF22B095A52E1D41656C98,MD5=CED4AA0B4CBF72E2520E0A2CCFF79370,SHA256=D5697FEF6995E992B9232A2B19665A297743427316C7225A5B772F0032F20FCA,IMPHASH=B0F049C014592B156EB1FA857E99CEB9  
ParentProcessGuid: {884d4bfa-8f6d-6a0c-4e00-000000001800}  
ParentProcessId: 3612  
ParentImage: C:\Program Files\VMware\VMware Tools\vmtoolsd.exe  
ParentCommandLine: "C:\Program Files\VMware\VMware Tools\vmtoolsd.exe"  
ParentUser: NT AUTHORITY\SYSTEM  

## Description:
cmd.exe is a command line interpreter usually used for administrative tasks, manual command execution, scripts and troubleshooting.

## Common normal parent processes:
- explorer.exe  
- services.exe  
- task scheduler related processes  

## Common normal child processes:
- cmd.exe → ipconfig.exe  
- cmd.exe → ping.exe  
- cmd.exe → powershell.exe  
- cmd.exe → whoami.exe  

## Assessment:
Normal when launched interactively or through administrative scripts.

---

# 3. powershell.exe

## Process Create:
RuleName: technique_id=T1059.001,technique_name=PowerShell  
UtcTime: 2026-05-23 10:53:45.981  
ProcessGuid: {884d4bfa-8739-6a11-c701-000000001800}  
ProcessId: 12280  
Image: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe  
FileVersion: 10.0.26100.5074 (WinBuild.160101.0800)  
Description: Windows PowerShell  
Product: Microsoft® Windows® Operating System  
Company: Microsoft Corporation  
OriginalFileName: PowerShell.EXE  
CommandLine: "C:\WINDOWS\System32\WindowsPowershell\v1.0\powershell.exe" -noninteractive -outputFormat xml -NonInteractive -encodedCommand IABbAEUAbgB2AGkAcgBvAG4AbQBlAG4AdABdADoAOgBPAFMAVgBlAHIAcwBpAG8AbgAuAFYAZQByAHMAaQBvAG4AIAA= -inputFormat xml  
CurrentDirectory: C:\Windows\System32\  
User: NT AUTHORITY\SYSTEM  
LogonGuid: {884d4bfa-8f65-6a0c-e703-000000000000}  
LogonId: 0x3E7  
TerminalSessionId: 0  
IntegrityLevel: System  
Hashes: SHA1=EB42621654E02FAF2DE940442B6DEB1A77864E5B,MD5=A97E6573B97B44C96122BFA543A82EA1,SHA256=0FF6F2C94BC7E2833A5F7E16DE1622E5DBA70396F31C7D5F56381870317E8C46,IMPHASH=AFACF6DC9041114B198160AAB4D0AE77  
ParentProcessGuid: {884d4bfa-8729-6a11-c301-000000001800}  
ParentProcessId: 12160  
ParentImage: C:\Program Files\AzureConnectedMachineAgent\GCArcService2\GC\gc_worker.exe  
ParentCommandLine: "C:\Program Files\AzureConnectedMachineAgent\GCArcService2\GC\..\GC\gc_worker.exe" -a WindowsDefenderExploitGuard -c NonCompliant -s inguest -g https://uksouth-gas.guestconfiguration.azure.com/virtualMachines/6376422f-f69a-41fc-ac59-7ed978b9bbc9  
ParentUser: NT AUTHORITY\SYSTEM  

## Description:
powershell.exe is commonly used for administration, automation, and scripting.

## Common normal parent processes:
- explorer.exe  
- cmd.exe  
- Windows Terminal  
- administrative tools  

## Common normal behaviours:
- Running administrative commands  
- Script execution for automation  
- Local system configuration checks  

## Assessment:
Normal for administration and automation activity.

---

# 4. services.exe

services.exe is a core Windows system process responsible for managing Windows services.

## Common normal child processes:
- services.exe → svchost.exe  
- services.exe → service-related executables  

## Normal behaviour observations:
- Typically runs in the background  
- Associated with system startup and service management  
- Usually operates under SYSTEM context  

## Assessment:
Highly common and expected Windows service-management behaviour.

---

# 5. svchost.exe

## Process Create:
RuleName: technique_id=T1083,technique_name=File and Directory Discovery  
UtcTime: 2026-05-23 10:57:31.009  
ProcessGuid: {884d4bfa-881b-6a11-1402-000000001800}  
ProcessId: 11168  
Image: C:\Windows\System32\svchost.exe  
FileVersion: 10.0.26100.7705 (WinBuild.160101.0800)  
Description: Host Process for Windows Services  
Product: Microsoft® Windows® Operating System  
Company: Microsoft Corporation  
OriginalFileName: svchost.exe  
CommandLine: C:\WINDOWS\system32\svchost.exe -k LocalServiceNetworkRestricted -p  
CurrentDirectory: C:\WINDOWS\system32\  
User: NT AUTHORITY\LOCAL SERVICE  
LogonGuid: {884d4bfa-8f67-6a0c-e503-000000000000}  
LogonId: 0x3E5  
TerminalSessionId: 0  
IntegrityLevel: System  
Hashes: SHA1=D87367D5078C476B109DC3312B62781513330055,MD5=B1C5636EC08026FD0F8CCBFF49ED7E59,SHA256=44FD6F9347CEED5798A25C47167F335EF085AE4648A81F775DD4BDC6240D8189,IMPHASH=DE43BD45CC98C143357416C7519ECCFD  
ParentProcessGuid: {884d4bfa-8f65-6a0c-0b00-000000001800}  
ParentProcessId: 808  
ParentImage: C:\Windows\System32\services.exe  
ParentCommandLine: C:\WINDOWS\system32\services.exe  
ParentUser: NT AUTHORITY\SYSTEM  

## Description:
svchost.exe is used to host Windows services.

## Common normal behaviour:
- Multiple svchost.exe instances running simultaneously  
- Often launched by services.exe  
- Typically runs from:  
  C:\Windows\System32\svchost.exe  

## Normal behaviour observations:
- Background execution is expected  
- Usually associated with legitimate Windows services  
- Network communication may occur depending on hosted service  

## Assessment:
Normal Windows background service behaviour.
