# Use Case: Failed Logons

## Objective

Identify repeated Windows failed logon activity and support triage by account, source host, and failure reason.

## Primary Event ID

| Event ID | Description |
|---:|---|
| 4625 | Failed logon |

## Starter SPL

```spl
index=windows sourcetype="WinEventLog:Security" EventCode=4625
| stats count by Account_Name, Workstation_Name, Source_Network_Address, Failure_Reason
| sort - count
```

## Triage Questions

- Which account has the highest number of failed attempts?
- Are failures coming from a single source or many sources?
- Is the account privileged, dormant, or service-related?
- Did the activity lead to account lockout?
- Is there a successful logon after repeated failures?

## Screenshot Placeholder

Add screenshot later:

```text
screenshots/splunk-search-4625-failed-logons.png
```
