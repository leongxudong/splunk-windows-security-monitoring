# Use Case: Administrative Activity

## Objective

Track account and group changes that may affect privileged access or auditability.

## Relevant Event IDs

| Event ID | Description |
|---:|---|
| 4720 | User account created |
| 4722 | User account enabled |
| 4726 | User account deleted |
| 4728 | Member added to global security group |
| 4732 | Member added to local security group |
| 4738 | User account changed |

## Starter SPL

```spl
index=windows sourcetype="WinEventLog:Security" (EventCode=4720 OR EventCode=4722 OR EventCode=4726 OR EventCode=4728 OR EventCode=4732 OR EventCode=4738)
| table _time, host, EventCode, Account_Name, Group_Name, Member_Name, Subject_Account_Name
| sort - _time
```

## Triage Questions

- Was the change expected and approved?
- Who performed the change?
- Which account or group was affected?
- Was the affected group privileged?
- Is there a related ticket, request, or approval record?

## Screenshot Placeholder

Add screenshot later:

```text
screenshots/splunk-admin-activity-search.png
```
