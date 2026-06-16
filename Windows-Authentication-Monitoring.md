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

![Successful Login Events](https://github.com/majjinaveensoc/SOC-Projects/blob/main/Screenshot%20(73).png?raw=true)

### Event ID 4625 - Failed Login Events

![Failed Login Events](https://github.com/majjinaveensoc/SOC-Projects/blob/main/Screenshot%20(72).png?raw=true)

### Failed Login Investigation

![Failed Login Investigation](https://github.com/majjinaveensoc/SOC-Projects/blob/main/Screenshot%20(74).png?raw=true)

### Authentication Statistics

![Authentication Statistics](https://github.com/majjinaveensoc/SOC-Projects/blob/main/Screenshot%20(78).png?raw=true)

Analysis:
Authentication events were aggregated by account name to understand login frequency and establish a baseline for user activity.

### Top Accounts by Login Activity

![Top Accounts by Login Activity](https://github.com/majjinaveensoc/SOC-Projects/blob/main/Screenshot%20(75).png?raw=true)

Analysis:
The analysis shows the most active accounts in the environment. This helps SOC analysts identify normal user behavior and detect unusual account activity.

### Failure Reason Analysis

![Failure Reason Analysis](https://github.com/majjinaveensoc/SOC-Projects/blob/main/Screenshot%20(79).png?raw=true)

Analysis:
The failed login attempt was triggered by an invalid username or incorrect password. Splunk helped identify the account involved, the affected host, and the exact failure reason from Windows Security logs.
