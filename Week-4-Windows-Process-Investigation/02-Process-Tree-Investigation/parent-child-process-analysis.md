# TICKET 3 — Parent-Child Process Analysis

explorer.exe → cmd.exe
    • Parent process 
explorer.exe is the parent process, which launched cmd.exe
    • Child process 
cmd.exe is the child process, which was launched by explorer.exe
    • Execution chain explanation 
The user of the system, opened command prompt through user interface. 
    • Normal or suspicious? 
Normal.
    • Unexpected Process Lineage?
No 
    • Why?
Because a user has intentionally opened command prompt through user interface.  

cmd.exe → powershell.exe
    • Parent process 
cmd.exe is the parent process, which triggered powershell.exe
    • Child process 
powershell.exe is the child process, which was launched by cmd.exe
    • Execution chain explanation
Command prompt triggered powershell.
    • Normal or suspicious? 
Can be suspicious. 
    • Unexpected Process Lineage? 
Yes
    • Why? 
Admins often launch powershell through cmd, but attackers also do that in order to deploy scripts and payloads. 

services.exe → svchost.exe 
    • Parent process 
services.exe is the parent, which triggered svchost.exe
    • Child process
svchost.exe is the child, which was triggered by services.exe 
    • Execution chain explanation
services.exe triggered svchost.exe
    • Normal or suspicious? 
Normal
    • Unexpected Process Lineage?
No
    • Why? 
svchost.exe is commonly launched by services.exe for legitimate Windows background services.
