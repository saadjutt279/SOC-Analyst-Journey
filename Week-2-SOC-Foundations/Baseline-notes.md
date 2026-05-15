# Baseline Notes

## Authentication Activity
- 4625 failed logons showed repeated spikes from a single source, indicating possible brute-force behaviour.
- 4624 successful logons were observed following failed attempts, suggesting potential credential compromise or successful guessing.
- 4740 account lockout events were triggered, confirming authentication abuse patterns.

## Process Activity
- No abnormal process creation events were directly linked to authentication attempts in this phase.
- Standard Windows background processes remained consistent with baseline behaviour.
- No suspicious execution chains (e.g., PowerShell or cmd abuse) were observed during login activity.

## System Behaviour
- Authentication activity showed clear deviation from normal baseline due to repeated failed logins.
- Account lockout behaviour indicated active defensive response from the system.
- No privilege escalation activity (4672) confirmed post-login in this scenario.
- Overall system behaviour suggested an authentication-focused attack attempt (brute force simulation).
