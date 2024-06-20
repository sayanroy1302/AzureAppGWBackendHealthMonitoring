# Azure FrontDoor WAF Triage Workbook

Author: [Sayan Roy](https://github.com/sayanroy1302)

This workbook visualizes Azure FrontDoor WAF rule violations and helps with triaging those so to facilitate tuning the WAF against valid traffic.

This workbook is designed to parse WAF logs from Application Gateway WAF V2 configured with WAF Policy.

Often companies struggle to parse the logs from the Application Gateway Web Application Firewall and triage them to determine which ones are true violations and which ones are false positives. Especially during the design phase of an application, it is important to review these logs and make sure to adapt the application and/or WAF configuration so to eliminate false positives. This is where this workbook might help.


## Deploying the Workbook

To deploy this workbook, click the button "Deploy to Azure".  Fill in the requested parameters:

- `Workbook Display Name`: the name of the workbook as it will be shown in the portal
- `Workbook Source Id`: the full Resource ID of the Log Analytics workspace you want to link to workbook to.  Example of a value: /subscriptions/'GUID'/resourcegroups/'RG Name'/providers/microsoft.operationalinsights/workspaces/'Workspace Name'

Then click "Review + create".

_**Note**: If you need to use the transaction ID in the FrontDoorAccessLog, then replace "host_s" with "hostName_s" in the join between ApplicationGatewayAccessLog and FrontDoorWebApplicationFirewallLog_
