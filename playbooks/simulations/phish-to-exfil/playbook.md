Microsoft Sentinel Query:

Rule name: DP--Potential-Attack-Chain-Markers

Log:
DeviceEvents
| where DeviceName == "dp--win11--dp"
| where AdditionalFields has_any ("3100","3200","3215","3300","3400","3410","3500","3510","3520","3999")
| project TimeGenerated, DeviceName, ActionType, AdditionalFields, InitiatingProcessFileName, ReportId
| order by TimeGenerated asc
