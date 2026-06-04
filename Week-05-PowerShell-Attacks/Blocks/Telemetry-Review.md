# TELEMETRY REVIEW

## 1. Data Sources Used
• Sysmon EventID 1  
• Process Logs  

---

## 2. What Worked Well
• Process Creation Visibility  
• User Context Investigation  
• Parent Child Process relationship  
• Command Line inspection  

---

## 3. What Was Missing
• Network Connections and DNS activity  
• Complete Powershell Commands  
• Email metadata and attachment analysis  

---

## 4. Why It Matters
Process creation logs alone cannot confirm malicious intent.  
Multiple telemetry sources are required to reconstruct full attacker behavior.  

---

## 5. Key Learning
PowerShell attacks are best detected through:  
• Process tree analysis  
• Command line inspection  
• Execution context (parent process behavior)  
```

