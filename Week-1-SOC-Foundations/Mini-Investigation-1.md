Scenario:
A review was conducted on authentication and process creation logs to identify suspicious activity within the Windows environment.

Events Observed:
Following are the events observed during the investigation.

4624
EventID 4624 which shows the successful logins was used to check the successful login attempts on the system. Successful authentication activity appeared consistent with expected local system and user behaviour.
4625
EventID 4625 which shows the failed logins was used to check the failed login attempts on the system.Not all failed attempts can be counted as a malicious activity, multiple failed attempts over a small period of time depicts a suspicious activty but this was not a case in this scenerio. Just 2 failed login attempts were recorded in the logs which were minutes apart to each other, which depicts this as a normal behaviour.

4688
EventID 4688 which shows the processes being created, and which user is responsible for it, making it essential to detect malicious activity. It was used to detect suspicious processes being created. 

Analysis
The activity was completely normal, there was a lot of successful login attempts which showed a regular person logging in. Just 2 failed login attempts were recorded, which does not appear as a legimalicious activity alone. There was no indication of attack of any kind. 

Suspicion Level:
Suspicion level was very low as there was no indication of any malicious behavior in the logs. All the logs depicted normal behaviour.

Conclusion:
No indicator of malicious activity was found during the investigation.
