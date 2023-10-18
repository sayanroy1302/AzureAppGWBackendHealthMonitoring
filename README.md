# Logic app to send Backend health to Log analytics

Azure Application Gateway backend health check server unhealth status is not stored in metrics. Following Logic App code can be used to create a Logic App which can be triggered whenever there is an alert for backend host unhealth count > 0 and ingest logs into a custom table in Log Analytics workspace. 

You can use the code view and upload this code, but you have to edit the code to create a log analytics connector and Managed Identity for Logic App which has sufficient privileges to query Application Gateway backend health.
1. Upload the attached code to logic app.
2. Copy the send data step code.
3. Create a new Send data step with connection and paste the send data code. 
4. Create Managed Identity for logic app and give sufficient permissions for the same.
5. Use the Managed Identity for HTTP step for authentication. 
6. Configure the alert to trigger logicApp

Check here for common alert schema to be used in Logic App: https://learn.microsoft.com/en-us/azure/azure-monitor/alerts/alerts-logic-apps?tabs=send-email
You can customize the alert notification by extracting information about the affected resource on which the alert fired, for example, the resourceID, resource group, subscription ID. 

![image](https://github.com/sayanroy1302/AzureAppGWBackendHealthMonitoring/assets/141024289/b1060a70-0bc6-4032-a9ec-be059c69b067)

![image](https://github.com/sayanroy1302/AzureAppGWBackendHealthMonitoring/assets/141024289/38c932e4-29c8-4602-8b99-24b73002f18b)

![image](https://github.com/sayanroy1302/AzureAppGWBackendHealthMonitoring/assets/141024289/d747c6ac-f682-4ca2-a1e4-995212156b5f)

![image](https://github.com/sayanroy1302/AzureAppGWBackendHealthMonitoring/assets/141024289/844514e8-cf13-47a6-a275-e1af13564640)

![image](https://github.com/sayanroy1302/AzureAppGWBackendHealthMonitoring/assets/141024289/8f1f410e-cfdb-492c-97df-f4498dd0bc0c)

![image](https://github.com/sayanroy1302/AzureAppGWBackendHealthMonitoring/assets/141024289/2d2ca0f7-f985-4620-a2d8-b92ca5151626)


