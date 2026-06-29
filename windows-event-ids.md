# Windows Event ID Reference

This page records common Windows Event IDs that are useful for security monitoring, audit, and investigation workflows.

## Authentication Events

| Event ID | Event | Monitoring Use |
|---:|---|---|
| 4624 | Successful logon | Review successful access, logon type, source host, and account context |
| 4625 | Failed logon | Identify repeated failures, password spray indicators, and suspicious sources |
| 4634 | Logoff | Correlate session activity and access duration |
| 4648 | Logon using explicit credentials | Review credential use across hosts or applications |
| 4740 | Account lockout | Identify accounts affected by repeated failures |

## Account and Group Management

| Event ID | Event | Monitoring Use |
|---:|---|---|
| 4720 | User account created | Detect new account creation |
| 4722 | User account enabled | Review re-enabled accounts |
| 4726 | User account deleted | Track account removal |
| 4728 | Member added to global security group | Monitor privileged group changes |
| 4732 | Member added to local security group | Monitor local administrator group changes |
| 4738 | User account changed | Review account attribute changes |

## Process and PowerShell Events

| Event ID | Event | Monitoring Use |
|---:|---|---|
| 4688 | Process creation | Review command execution where process creation logging is enabled |
| 4103 | PowerShell module logging | Review PowerShell command activity |
| 4104 | PowerShell script block logging | Review script block content where enabled |

## Notes

Event IDs are only useful when the required audit policy or logging configuration is enabled. Always validate log source coverage before relying on a detection use case.
