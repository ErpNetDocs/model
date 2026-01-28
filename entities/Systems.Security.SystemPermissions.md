---
uid: Systems.Security.SystemPermissions
---
# Systems.Security.SystemPermissions (View)


System permissions.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.SystemPermissions  
Introduced In Version: 24.1.4.91  
API access:  ReadWrite  

## Visualization
Display Format: {Subsystem}/{Module}/{Permission}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Security.SystemPermissions](Systems.Security.SystemPermissions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKeyId](Systems.Security.SystemPermissions.md#accesskeyid) | guid | The access key Id 
| [Module](Systems.Security.SystemPermissions.md#module) | string | The module of the permission. 
| [Permission](Systems.Security.SystemPermissions.md#permission) | string | The permission meaning. 
| [Subsystem](Systems.Security.SystemPermissions.md#subsystem) | string | The subsystem of the permission. 


## Attribute Details

### AccessKeyId

The access key Id

Type: **guid**  
Category: **System**  
Supported Filters: **NotFilterable**  
Show in UI: **CannotBeShown**  

### Module

The module of the permission.

Type: **string**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **ShownByDefault**  

### Permission

The permission meaning.

Type: **string**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **ShownByDefault**  

### Subsystem

The subsystem of the permission.

Type: **string**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Security_SystemPermissions

Domain API Entity Type: 
Systems_Security_SystemPermissionsEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_SystemPermissions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_SystemPermissions?$top=10>

