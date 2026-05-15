# Failed Login Attempts:

Event  
| where EventID == 4625  
| summarize count() by Computer, bin(TimeGenerated, 5m)  
| order by TimeGenerated desc  

WinVM01  
5/13/2026, 2:35:00.000 PM  
6  
WinVM01  
5/13/2026, 2:25:00.000 PM  
6  
WinVM01  
5/13/2026, 2:20:00.000 PM  
2  
WinVM01  
5/13/2026, 2:15:00.000 PM  
6  
WinVM01  
5/13/2026, 12:30:00.000 PM  
1  
WinVM01  
5/8/2026, 10:45:00.000 AM  
4  
WinVM01  
5/8/2026, 10:35:00.000 AM  
11  
WinVM01  
5/7/2026, 9:50:00.000 AM  
2  

## 1. What exactly happened?
Most chances of a brute force attack on an already working system.

## 2. Is this normal or abnormal?
Some logins attempts were abnormal.

## 3. What could this mean?
This means someone is trying to login through malicious action like brute force, password spraying, password guessing or dictionary attack.

## 4. What should happen next?
This should be analyzed further with the analysis of 4624 after these continuous 4625 attempts, and if they were successful, further investigation should be done by analyzing 4688 to check which processes were started, were they suspicious like word is starting powershell, etc. If so, this will be urgently escalated to SOC Level 2.

## Report:
I analyzed the logs for failed login attempts for the past 7 weeks, which shows some burst patterns our different days with 6 attempts being constantly made and 11 is the spike for these attempts. There are some single or two attempts shown which usually is a normal behavior of someone entering the wrong password accidentally. All of these attempts were made on the same machine and they are not random as on the 13th several attempts were made in burst pattern in a short span of time which indicate a suspicious activity being done. Before escilating to the higher level, 4624 logs will be checked against these dates and times to check if the login attempts were successful during these attempts. If so the threat level will be increased to medium and, 4688 logs will be checked to check what the user was doing after logging in, if any abnormal activity is detected, the threat level will increase from low to high and SOC level 2 will be informed immidiately for further action.

## MITRE ATT&CK Mapping:
T1110 – Brute Force

## Successful Login Attempts:
Repeated unsuccessful attempts (4625) were observed within a short span of time, and some successful ones were also observed just after that, which could indicate to a suspicious activity like brute force and password spray attacks. Upon further investigation of those (4624) logs, it was found that the logins were a normal activity based on the logon type, SYSTEM account usage, services.exe being started and others. Because of this, it can not said with certainty that those login attempts were malicious, for that 4688 logs have to be examined.

5/13/2026, 2:40:30.867 PM

TimeGenerated [UTC]
2026-05-13T14:40:30.8679152Z
Computer
WinVM01
RenderedDescription
An account was successfully logged on. Subject: Security ID: S-1-5-18 Account Name: WINVM01$ Account Domain: WORKGROUP Logon ID: 0x3E7 Logon Information: Logon Type: 5 Restricted Admin Mode: - Remote Credential Guard: - Virtual Account: No Elevated Token: Yes Impersonation Level: Impersonation New Logon: Security ID: S-1-5-18 Account Name: SYSTEM Account Domain: NT AUTHORITY Logon ID: 0x3E7 Linked Logon ID: 0x0 Network Account Name: - Network Account Domain: - Logon GUID: {00000000-0000-0000-0000-000000000000} Process Information: Process ID: 0x330 Process Name: C:\Windows\System32\services.exe Network Information: Workstation Name: - Source Network Address: - Source Port: - Detailed Authentication Information: Logon Process: Advapi Authentication Package: Negotiate Transited Services: - Package Name (NTLM only): - Key Length: 0 This event is generated when a logon session is created. It is generated on the computer that was accessed. The subject fields indicate the account on the local system which requested the logon. This is most commonly a service such as the Server service, or a local process such as Winlogon.exe or Services.exe. The logon type field indicates the kind of logon that occurred. The most common types are 2 (interactive) and 3 (network). The New Logon fields indicate the account for whom the new logon was created, i.e. the account that was logged on. The network fields indicate where a remote logon request originated. Workstation name is not always available and may be left blank in some cases. The impersonation level field indicates the extent to which a process in the logon session can impersonate. The authentication information fields provide detailed information about this specific logon request. - Logon GUID is a unique identifier that can be used to correlate this event with a KDC event. - Transited services indicate which intermediate services have participated in this logon request. - Package name indicates which sub-protocol was used among the NTLM protocols. - Key length indicates the length of the generated session key. This will be 0 if no session key was requested.

## Process Creation:
Event  
| where EventID == 4688  
| where TimeGenerated between (datetime(2026-05-13 14:15:00) .. datetime(2026-05-13 15:00:00))  
| project TimeGenerated, Computer, RenderedDescription  
| order by TimeGenerated desc  

After the successful login attempts, 4688 logs were reviewed for process creation examination. Most of the processes were consistent with normal windows and powershell activities, like services.exe, svchost.exe. At this stage, no clear evidence of malicious activity was found, which means this attempt will not be escalated.

## IOC List:
IOC TYPE	VALUE 	REASON  
Targeted Account	Administrator	Repeated Login Failures  
Host	WINVM01	System receiving the auth attempts  
EventID	4625	Filed auth activity  
Timestamp Range	2026-05-13 14:15–14:35 	Burst Attack Window  
Failed Attempt Count	11	Abnormal Auth Frequency
