# Week 2 — SOC Tier 1 Shift Simulation (Foundational Incident Handling)

## Topics Covered
- Brute Force Attack Investigation (Authentication Abuse)
- Account Lockout Analysis
- SOC Tier 1 Alert Triage Workflow
- Multi-Event Correlation (Failed → Successful Logons)
- Time-based Attack Pattern Detection
- Incident Severity Assessment
- Escalation Decision Making (True Positive vs False Positive)

## Event IDs Investigated
- 4625 — Failed Logons
- 4624 — Successful Logons
- 4740 — Account Lockouts
- 4672 — Special Privileges Assigned

## Tools Used
- Microsoft Sentinel
- KQL
- Windows Event Logs

## Investigation Work
- Mini Investigation #1
- Brute force login analysis
- Failed login spike detection
- Correlation of failed and successful logons
- Account lockout validation
- Mini Investigation #2
- SOC alert triage simulation
- Timeline reconstruction of authentication events
- Mini Investigation #3
- Post-login privilege check
- Session behaviour validation

## Key Learnings
- How brute force attacks appear in Windows logs
- Identifying automated vs human login behaviour patterns
- Correlating multiple authentication events into one incident
- Understanding account lockout as a detection signal
- SOC Tier 1 alert triage and escalation logic
- Building attack timelines from raw logs
- Moving from single-event thinking to incident-based analysis
