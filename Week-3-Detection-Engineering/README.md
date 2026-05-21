# Week 3 — Detection Engineering Sprint

This week focused on authentication detection engineering and SOC operational reasoning using Microsoft Sentinel and KQL.

The objective was to understand authentication baselines, create detections for common identity attacks, tune thresholds based on environmental noise, classify false positives, and simulate Tier 1 SOC analyst decision-making.

The project emphasized behavioral analysis rather than only query creation.


## SOC Skills Practiced

- Authentication baseline analysis
- KQL detection engineering
- Brute force detection logic
- Password spray detection
- Threshold tuning
- False positive analysis
- Alert triage
- Escalation decision-making
- Confidence scoring
- MITRE ATT&CK mapping
- Signal vs noise analysis
- Authentication attack simulation

## Detections Built

1. Repeated Failed Login Detection
2. Multi-User per IP (Password Spray Detection)
3. Authentication Burst / Login Spike Detection
4. Account Lockout Behaviour Detection

## Key Concepts Learned

- Difference between benign authentication failures and malicious activity
- How attackers avoid account lockout policies
- Importance of threshold balancing in SOC environments
- Operational impact of false positives
- Difference between signal and environmental noise
- How contextual indicators affect confidence scoring

## MITRE ATT&CK Techniques Covered

- T1110 — Brute Force
- T1110.003 — Password Spraying
- Credential stuffing / authentication automation behaviour
- Account lockout progression indicators

## Repository Structure

- Baseline Analysis
- Detection Creation
- Detection Tuning
- SOC Decision Logic
- MITRE Mapping
- Authentication Attack Simulation

## Environment

- Microsoft Sentinel
- KQL (Kusto Query Language)
- Windows Authentication Logs
- Security Events
