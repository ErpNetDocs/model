---
uid: Systems.Security.SystemPermissions
---
# Systems.Security.SystemPermissions View

**Namespace:** [Systems.Security](Systems.Security.md)  

System permissions. Entity: Sec_System_Permissions (Introduced in version 24.1.4.91)

## Default Visualization
Default Display Text Format:  
_{Subsystem}/{Module}/{Permission}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

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

_Type_: **guid**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Show in UI_: **CannotBeShown**  

### Module

The module of the permission.

_Type_: **string**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **ShownByDefault**  

### Permission

The permission meaning.

_Type_: **string**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **ShownByDefault**  

### Subsystem

The subsystem of the permission.

_Type_: **string**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Security_SystemPermissions?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Security_SystemPermissions?$top=10>

