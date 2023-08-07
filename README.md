# Logic app to send Backend health to Log analytics

Azure Application Gateway backend health check server unhealth status is not stored in metrics. Following Logic App code can be used to create a Logic App which can be triggered whenever there is an alert for backend host unhealth count > 0 and ingest logs into a custom table in LA workspace. 

You can use the code view and upload this code, but you have to edit the code to create a log analytics connector and Managed Identity for logic app which has sufficient privileges to query AppGW health. 
1. Upload the attached code to logic app.
2. Copy the send data step code.
3. Create a new Send data step with connection and paste the send data code. 
4. Create Managed Identity for logic app and give sufficient permissions for the same.
5. Use the Managed Identity for HTTP step for authentication. 
6. Configure the alert to trigger logicApp

![image](https://github.com/sayanroy1302/AzureAppGWBackendHealthMonitoring/assets/141024289/2d2ca0f7-f985-4620-a2d8-b92ca5151626)


