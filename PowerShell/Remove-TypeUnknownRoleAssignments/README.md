# Remove-TypeUnknownRoleAssignments

## SYNOPSIS
Finds and removes unknown role assignments. 

## DESCRIPTION
Find and removes all unknown role assigments in an Azure subscription. 

## Parameters

```SubscriptionName```
Sets the Azure subscription name of the subscription to review.

```SubscriptionId```
Sets the Azure subscription Id of the subscription to review. 

```TenantId```
Sets the Azure Tenant to use. 

```QuotaIdContains```
Sets the QuotaId name of the subscription type. 

```QuotaIdExclude```
Sets the exclusions of the subscription type.

```All```
Bool to review all subscriptions. 

## Exaples
EXAMPLE 1
```PS>  Remove-AzTypeUnknownRoleAssignmentt -All```
Reviews all subscriptions for unknown role assignments and removes the found unkown role assignments.

EXAMPLE 2
```PS>  Remove-AzTypeUnknownRoleAssignment -SubscriptionName "ABC" -TenantId "123-456-789-000"```
Reviews the specified subscription for unknown role assignments and removes the found unknown role assignments. 

EXAMPLE 3
```PS>  Remove-AzTypeUnknownRoleAssignment -SubscriptionId "ABC" -TenantId "123-456-789-000"```
Reviews the specified subscription for unknown role assignments and removes the found unknown role assignments. 

EXAMPLE 4
```PS>  Remove-AzTypeUnknownRoleAssignment -SubscriptionName "ABC" -TenantId "123-456-789-000" -QuotaIdContains "Enterprise"```
Reviews the specified subscription for unknown role assignments and only removes the found unknown role assignments if the subscription quota type contains Enterprise.

EXAMPLE 5
```PS>  Remove-AzTypeUnknownRoleAssignment -SubscriptionName "ABC" -TenantId "123-456-789-000" -QuotaIdExclude Enterprise,DevTest```
Reviews the specified subscription for unknown role assignments and only removes the found unknown role assignment if the subscription type is not in the provided exclusion list.
