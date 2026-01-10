# Azure Activity Logs Integration – Microsoft Sentinel

## Objective
To connect Azure subscription activity logs to Microsoft Sentinel for centralized monitoring.

## Tools Used
- Microsoft Sentinel
- Log Analytics Workspace
- Azure Activity Logs

## Steps Performed
1. Opened Microsoft Sentinel and selected workspace
2. Accessed Content Hub and selected Azure Activity solution
3. Associated Azure subscription with Sentinel workspace
4. Verified log ingestion using KQL queries

## Verification
```kql
AzureActivity
| take 5
