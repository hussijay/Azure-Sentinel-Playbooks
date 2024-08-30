AI-Driven Incident Response Logic App Template
This JSON file is an ARM (Azure Resource Manager) template designed to deploy an AI-integrated Logic App within Azure.
The Logic App is configured to automate incident response processes in Microsoft Sentinel by leveraging OpenAI's GPT-3.5 model.
The playbook automatically generates remediation suggestions based on incident data and adds these suggestions as comments to the corresponding incidents in Microsoft Sentinel.

Template Overview:
Resource Type: Azure Logic App
Location: East US (eastus)
Identity: System-assigned managed identity for secure connections to Azure Sentinel and OpenAI APIs.
Triggers:
Microsoft Sentinel Incident Creation: The Logic App is triggered whenever a new incident is created in Microsoft Sentinel.
Actions:
GPT-3.5 Completion: The Logic App uses GPT-3.5 to generate a text-based remediation strategy based on the incident title and description.
For Each Loop: Iterates through the generated responses and adds each as a comment to the incident in Microsoft Sentinel.
Connections:
Azure Sentinel: Secure connection to Microsoft Sentinel to receive incident data and post comments.
OpenAI API: Secure connection to OpenAI's API to generate incident response recommendations.
Parameters:
workflows_Ai_Integration_name: Name of the Logic App workflow (default is Ai-Integration).
connections_azuresentinel_Ai_Integration_externalid: External ID for the Azure Sentinel connection.
connections_openaiip_2_externalid: External ID for the OpenAI API connection.
How to Use:
Deploy the Template:

Upload this JSON template to your Azure environment using the Azure Portal, Azure CLI, or PowerShell.
Customize the parameters if necessary to fit your Azure environment.
Configure Connections:

Ensure that the Azure Sentinel and OpenAI API connections are properly configured using managed service identity (MSI).
Trigger the Playbook:

Once deployed, the Logic App will automatically trigger upon incident creation in Microsoft Sentinel, generating and posting AI-driven remediation suggestions.
Use Case:
This Logic App is particularly useful for automating the initial response phase in a Security Operations Center (SOC). By integrating AI-driven insights directly into the incident management workflow, it helps SOC analysts respond to threats more quickly and efficiently.

To Deploy  
  [![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https://raw.githubusercontent.com/hussijay/Azure-Sentinel-Playbooks/main/template.json)

