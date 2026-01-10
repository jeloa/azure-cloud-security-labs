# Sentinel Analytics Rule – Failed Sign-In Detection

## Objective
To create a Microsoft Sentinel analytics rule that detects multiple failed Azure sign-in attempts.

## Tools Used
- Microsoft Sentinel
- Log Analytics Workspace
- Azure Sign-in Logs
- KQL (Kusto Query Language)

## Steps Performed
1. Opened Microsoft Sentinel and selected the assigned workspace
2. Navigated to Analytics and created a scheduled query rule
3. Defined detection logic using KQL to identify repeated failed sign-ins
4. Configured rule severity and MITRE ATT&CK tactic
5. Enabled incident creation for detected events

Outcome
-Sentinel generates alerts for potential brute-force sign-in activity
-Incidents are automatically created for investigation

Security Concepts Learned
-SIEM detection rules
-Brute-force attack indicators
-Log-based alerting using KQL

Configuration
-Rule type: Scheduled query
-Severity: Medium
-Tactic: Credential Access

## Detection Query
```kql
SigninLogs
| where ResultType != 0
| summarize FailedAttempts = count() by UserPrincipalName
| where FailedAttempts >= 3

