# TICKET 2 — Interactive vs Background Execution

## 🧩 Interactive Execution

### Example Process
control.exe

### Process Chain
explorer.exe → control.exe

### SOC Analysis
- User initiated via GUI
- explorer.exe confirms user interaction
- No automation involved

### Conclusion
Normal user-driven execution

---

## 🧩 Service-Driven Execution

### Example Process
svchost.exe

### Process Chain
services.exe → svchost.exe

### SOC Analysis
- SYSTEM-level execution
- No user involvement
- Triggered by Windows Service Manager

### Conclusion
Normal system background execution

---

## 🧩 Scripted / Scheduled Execution

### Example Process Chain
cmd.exe → script → reg.exe

### Example
reg query HKLM\SYSTEM\CurrentControlSet

### SOC Analysis
- Executed via batch/script
- No user interaction
- Automation-based execution

### Conclusion
Normal administrative automation activity
