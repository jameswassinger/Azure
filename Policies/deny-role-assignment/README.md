# Deny Role Assignment for PrincipalId

Get Azure Role Id
```
(Get-AzRoleDefinition | Where-Object { $_.Name -eq 'Role_Name' }).Id
```

Get Azure Group Id
```
(Get-AzADGroup | Where-Object {$_.DisplayName -eq 'Security_Group_Name' }).Id
```
