# Logic app to send Backend health to Log analytics

Azure Application Gateway backend health check server unhealth status is not stored in metrics. Following Logic App code can be used to create a Logic App which can be triggered whenever there is an alert for backend host unhealth count > 0 and ingest logs into a custom table in LA workspace. 

You can use the code view and upload this code, but you have to edit the code to create a log analytics connector and Managed Identity for logic app which has sufficient privileges to query AppGW health. 
•	Upload the attached code to logic app.
•	Copy the send data step code.
•	Create a new Send data step with connection and paste the send data code. 
•	Create Managed Identity for logic app and give sufficient permissions for the same.
•	Use the Managed Identity for HTTP step for authentication. 
•	Configure the alert to trigger logicApp

![image](https://github.com/sayanroy1302/AzureAppGWBackendHealthMonitoring/assets/141024289/010dec41-9d0c-4f97-b8a1-c603da9f698e)

