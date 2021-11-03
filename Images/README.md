[Deploy to Azure](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/deploy-to-azure-button)

```
$url = "https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/quickstarts/microsoft.storage/storage-account-create/azuredeploy.json"
[uri]::EscapeDataString($url)
```
