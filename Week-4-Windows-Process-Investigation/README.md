# Week 4 — Windows Process Investigation Sprint

This week focused on Windows process investigation, execution chain analysis, command-line forensics, PowerShell behaviour analysis, Sysmon telemetry interpretation, and SOC Tier 1 decision-making.

The objective was to understand how Windows processes behave under normal and suspicious conditions, analyse parent-child relationships, detect LOLBins abuse patterns, extract IOCs from process telemetry, and reconstruct execution timelines like a SOC analyst.

The project emphasized behavioural interpretation of process activity rather than only log reading.

---

## SOC Skills Practiced

- Windows process baselining
- Parent-child process analysis
- Interactive vs background execution analysis
- Suspicious execution chain identification
- PowerShell investigation (encoded commands, obfuscation)
- Command-line forensic analysis
- Sysmon Event ID 1 interpretation
- Process telemetry analysis
- IOC extraction from process data
- Execution timeline reconstruction
- Signed vs unsigned binary reasoning
- LOLBins (Living Off The Land Binaries) analysis
- SOC Tier 1 escalation decision-making

---

## Investigations Completed

1. Windows Process Behaviour Baseline (explorer.exe, cmd.exe, powershell.exe, services.exe, svchost.exe)
2. Interactive vs Background Execution Analysis
3. Parent-Child Process Chain Analysis
4. Suspicious PowerShell Execution Investigation
5. Suspicious Execution Chain Analysis
6. Command-Line Investigation (benign vs malicious commands)
7. Encoded PowerShell Command Analysis (Base64 decoding + IEX execution)
8. LOLBins Investigation (powershell.exe, cmd.exe, rundll32.exe, mshta.exe, certutil.exe)
9. Sysmon Process Telemetry Investigation (Event ID 1 analysis)
10. IOC Extraction (process, network, behavioural indicators)
11. Execution Timeline Reconstruction (step-by-step process flow)
12. Tier 1 SOC Decision Model (actionability + escalation rules)

---

## Key Concepts Learned

- How normal Windows processes behave in enterprise environments
- Difference between user-driven and system-driven execution
- How attackers abuse PowerShell for stealth execution
- Importance of parent-child process relationships in investigations
- How command-line arguments reveal attacker intent
- Understanding LOLBins as legitimate tools used for malicious activity
- How encoded PowerShell commands hide payload execution
- How Sysmon provides visibility into process creation and context
- How to extract meaningful IOCs from telemetry
- How to reconstruct attack execution timelines
- How Tier 1 SOC analysts decide to close, monitor, or escalate alerts

---

## MITRE ATT&CK Techniques Covered

- T1059.001 — PowerShell
- T1204 — User Execution
- T1083 — File and Directory Discovery
- T1059 — Command and Scripting Interpreter
- T1105 — Ingress Tool Transfer (certutil usage)
- T1218 — Signed Binary Proxy Execution (LOLBins)
- T1055 — Process Injection concepts (theoretical context via PowerShell execution chains)

---

## Repository Structure

- Windows Process Baseline
- Interactive vs Background Execution
- Parent-Child Process Analysis
- PowerShell Investigation
- Execution Chain Analysis
- Command-Line Investigation
- Encoded Command Analysis
- LOLBins Investigation
- Sysmon Telemetry Analysis
- IOC Extraction Notes
- Execution Timeline Reconstruction
- Tier 1 Decision Model

---

## Environment

- Windows 10 / Windows 11 telemetry
- Sysmon Event Logs
- PowerShell execution traces
- Command Prompt (cmd.exe) analysis
- Microsoft Windows service architecture (services.exe, svchost.exe)
