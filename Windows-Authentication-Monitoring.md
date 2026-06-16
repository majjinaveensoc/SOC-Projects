# Windows Authentication Monitoring using Splunk

## Objective
Monitor Windows authentication events and identify failed login attempts.

## Tools Used
- Splunk Enterprise
- Windows Event Logs

## Failed Login Detection

Query:

```spl
source="WinEventLog:Security" EventCode=4625
```

Result:
Detected failed login attempts caused by invalid credentials.

## Successful Login Detection

Query:

```spl
source="WinEventLog:Security" EventCode=4624
```

Result:
Verified successful authentication events.

## Findings

- Event ID 4625 = Failed Logon
- Event ID 4624 = Successful Logon
- Windows Security Logs can be monitored using Splunk

## Conclusion

This project demonstrates how a SOC Analyst can investigate Windows authentication activity using Splunk Enterprise.

## Screenshots

### Event ID 4624 - Successful Login Events

### Event ID 4625 - Failed Login Events

![Failed Login Events](https://github.com/majjinaveensoc/SOC-Projects/blob/main/Screenshot%20(72).png?raw=true)

### Failed Login Investigation

### Authentication Statistics

### Top Accounts by Login Activity

### Failure Reason Analysis
