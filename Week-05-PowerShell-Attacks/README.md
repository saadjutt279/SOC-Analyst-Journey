# Week 5 – PowerShell Attack Analysis (SOC Simulation)

## Objective
Simulate and analyze PowerShell-based attack techniques to understand detection, investigation, and escalation workflows used in SOC environments.

---

## Attack Techniques Covered
- Encoded PowerShell execution (-EncodedCommand)
- Execution policy bypass
- Hidden PowerShell execution
- Phishing → Office → PowerShell attack chain

---

## Skills Developed
- Windows process analysis (Sysmon Event ID 1)
- Parent-child process investigation
- PowerShell telemetry analysis
- IOC extraction and classification
- Attack timeline reconstruction
- SOC escalation decision-making
- Basic detection engineering (KQL logic)

---

## Cases Investigated

### Case 1 – Baseline PowerShell
Normal interactive PowerShell usage via Windows Terminal.

### Case 2 – Encoded PowerShell
Base64 encoded command execution requiring decoding and analysis.

### Case 3 – Stealth Execution
Execution policy bypass and hidden window execution techniques.

### Case 4 – Phishing Execution Chain
Office document leading to cmd.exe and PowerShell execution.

---

## Key Security Insights
- Encoding ≠ malicious by default, but increases suspicion
- Parent-child relationships are critical for detection
- Office spawning PowerShell is a high-risk indicator
- Execution context matters more than individual commands

---

## Outcome
Completed end-to-end SOC workflow:
Detection → Investigation → IOC extraction → Timeline reconstruction → Escalation decisions
