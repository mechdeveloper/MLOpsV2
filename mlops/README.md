# Set up MLOps with Azure DevOps
<https://learn.microsoft.com/en-us/azure/machine-learning/how-to-setup-mlops-azureml?view=azureml-api-2&tabs=azure-shell>

## Set up authentication with Azure and DevOps

### Create service principal

```bash
projectName="<your project name>"
roleName="Contributor"
subscriptionId="<subscription Id>"
environment="<Dev|Prod>" #First letter should be capitalized
servicePrincipalName="Azure-ARM-${environment}-${projectName}"
# Verify the ID of the active subscription
echo "Using subscription ID $subscriptionID"
echo "Creating SP for RBAC with name $servicePrincipalName, with role $roleName and in scopes     /subscriptions/$subscriptionId"
az ad sp create-for-rbac --name $servicePrincipalName --role $roleName --scopes /subscriptions/$subscriptionId
echo "Please ensure that the information created here is properly save for future use."
```

Service Principal credentials
```bash
{
   "appId": "<application id>",
   "displayName": "Azure-ARM-dev-Sample_Project_Name",
   "password": "<password>",
   "tenant": "<tenant id>"
}
```