# Splunk Searches

This page contains basic SPL examples for Windows security monitoring.

> Replace `index=windows` and `sourcetype=WinEventLog:Security` with the actual index and sourcetype used in the lab.

## Failed Logons

```spl
index=windows sourcetype="WinEventLog:Security" EventCode=4625
| stats count by Account_Name, Workstation_Name, Source_Network_Address, Failure_Reason
| sort - count
```

## Successful Logons

```spl
index=windows sourcetype="WinEventLog:Security" EventCode=4624
| stats count by Account_Name, Logon_Type, Workstation_Name, Source_Network_Address
| sort - count
```

## Account Lockouts

```spl
index=windows sourcetype="WinEventLog:Security" EventCode=4740
| table _time, host, Account_Name, Caller_Computer_Name
| sort - _time
```

## New User Accounts

```spl
index=windows sourcetype="WinEventLog:Security" EventCode=4720
| table _time, host, Account_Name, Subject_Account_Name
| sort - _time
```

## Security Group Membership Changes

```spl
index=windows sourcetype="WinEventLog:Security" (EventCode=4728 OR EventCode=4732)
| table _time, host, Group_Name, Member_Name, Subject_Account_Name
| sort - _time
```

## Notes

These are starter searches for learning and validation. Production searches should be tuned using environment context, asset criticality, known administrator activity, expected service accounts, and false-positive review.
