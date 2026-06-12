---
uid: Systems.Dmv.DatabaseInfo
---
# Systems.Dmv.DatabaseInfo View

**Namespace:** [Systems.Dmv](Systems.Dmv.md)  

Information about the database. Entity: Dmv_Database_Info (Introduced in version 24.1.1.67)

## Default Visualization
Default Display Text Format:  
_{ParameterName}: {ParameterValue}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Dmv.DatabaseInfo](Systems.Dmv.DatabaseInfo.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ParameterName](Systems.Dmv.DatabaseInfo.md#parametername) | string (256) | Name of database parameter. `Required` 
| [ParameterValue](Systems.Dmv.DatabaseInfo.md#parametervalue) | string (256) | Value of database parameter. `Required` 


## Attribute Details

### ParameterName

Name of database parameter. `Required`

_Type_: **string (256)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### ParameterValue

Value of database parameter. `Required`

_Type_: **string (256)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Dmv_DatabaseInfo?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Dmv_DatabaseInfo?$top=10>

