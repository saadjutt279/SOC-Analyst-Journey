```md id="ioc91"
# IOC WORKSHEET

## Case 1

| Indicator Type | Indicator Value | Risk | Reason |
|----------------|----------------|------|--------|
| Process | Powershell.exe | Low | Common Admin Tool |
| Process | WindowsTerminal.exe | Low | Normal Parent Child Chain |
| User | WindowsVictim | Low | Windows User |

---

## Case 2

| Indicator Type | Indicator Value | Risk | Reason |
|----------------|----------------|------|--------|
| Process | Powershell.exe | Low | Common Admin Tool |
| User | WindowsVictim | Low | Windows User |
| Argument | -EncodedCommand | Medium | Command Obfuscation can be used for both purposes |
| Payload | Base64String | Medium | Requires decoding and review |

---

## Case 3

| Indicator Type | Indicator Value | Risk | Reason |
|----------------|----------------|------|--------|
| Process | Powershell.exe | Medium | Common Admin Tool but suspicious under circumstances |
| Argument | -ExecutionPolicy Bypass | High | Defense evasion indicator |
| Argument | -WindowStyle Hidden | High | Stealth method |

---

## Case 4

| Indicator Type | Indicator Value | Risk | Reason |
|----------------|----------------|------|--------|
| Process | Powershell.exe | Medium | Common Admin Tool but suspicious under circumstances |
| Parent-Child Chain | winword.exe → cmd.exe | High | A word document should not open cmd under normal circumstances |
| Parent-Child Chain | cmd.exe → powershell.exe | High | Cmd started by word document should definitely not open powershell (Abnormal parent-child) |
```

