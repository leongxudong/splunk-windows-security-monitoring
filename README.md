# Splunk Windows Security Monitoring

A lightweight portfolio project documenting common Windows security monitoring use cases in Splunk.

The purpose is to show practical SIEM thinking: identifying useful Windows Event IDs, writing basic SPL searches, validating results, and explaining how each use case supports detection, audit, and incident response.

## Project Scope

This project covers:

- Windows Security Event ID mapping
- Basic SPL searches for common monitoring scenarios
- Screenshot placeholders for Splunk searches and dashboards
- Use case write-ups for authentication and administrative activity
- Practical notes for tuning and investigation workflow

## Repository Structure

```text
splunk-windows-security-monitoring/
├── README.md
├── windows-event-ids.md
├── splunk-searches.md
├── use-cases/
│   ├── failed-logons.md
│   └── admin-activity.md
└── screenshots/
    └── README.md
```

## Monitoring Use Cases

| Use Case | Event IDs | Purpose |
|---|---:|---|
| Failed logons | 4625 | Identify repeated authentication failures |
| Successful logons | 4624 | Review successful access patterns |
| Account lockout | 4740 | Identify accounts affected by repeated failures |
| User account created | 4720 | Track account creation activity |
| Security group membership changed | 4728 / 4732 | Monitor privileged group changes |
| Process creation | 4688 | Review command and process execution, where enabled |
| PowerShell activity | 4103 / 4104 | Review PowerShell command and script block logging, where enabled |

## Portfolio Value

This project demonstrates:

- SIEM use case development
- Windows log analysis fundamentals
- SPL search writing
- Evidence-based monitoring validation
- Ability to explain detection logic in operational terms

## Screenshot Status

Screenshots are not committed yet. See [screenshots/README.md](screenshots/README.md) for the required screenshot list.

## Disclaimer

This repository contains learning notes and sanitized examples only. It does not contain confidential logs, client data, employer data, or production telemetry.
