---
uid: Systems.Core.ReportQueries
---
# Systems.Core.ReportQueries


Contains the sub-queries, which a report contains.

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.ReportQueries  
Base Table: Gen_Report_Queries  
API access:  ReadWrite  

## Renames

Old name: General.ReportQueries  
New name: Systems.Core.ReportQueries  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {TableName}  
Search Members: TableName  
Name Member: TableName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Reports](General.Reports.md)  
Aggregate Root:  
[General.Reports](General.Reports.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DependsOnChildRows](Systems.Core.ReportQueries.md#dependsonchildrows) | boolean | If True the data in the current report table contains only the rows that have child rows in sub-tables.`Required` `Default(false)` 
| [ExtensionsList](Systems.Core.ReportQueries.md#extensionslist) | string (max) __nullable__ | A comma separated list of report extension names. An extension is set of additional fields that participate in the query 
| [FilterXml](Systems.Core.ReportQueries.md#filterxml) | dataaccessfilter __nullable__ | Filter for the loaded table`Unit: obj.Report.QueryName` 
| [ReferencePath](Systems.Core.ReportQueries.md#referencepath) | string (512) | A sequence of table names and foreign key columns that define how the data will be loaded by this query. For example - Gen_Documents/<br />Enterprise_Company_<br />Id/Company_Id - will load the definition of the company for the enterprise company of a document.`Required` 
| [ShowCustomProperties](Systems.Core.ReportQueries.md#showcustomproperties) | boolean | True to include the custom properties.`Required` `Default(false)` 
| [ShowTextColumns](Systems.Core.ReportQueries.md#showtextcolumns) | boolean | True to include text descriptions for certain columns.`Required` `Default(false)` 
| [TableName](Systems.Core.ReportQueries.md#tablename) | string (64) __nullable__ | The name of the report query. A Reference_Path can participate more than one time in the report but with different Report_Query_Name. This can be used to specify different filter for the same query. Can be NULL. 
| [UniqueName](Systems.Core.ReportQueries.md#uniquename) | string (64) __nullable__ | The name of the data table in the printout datasource. If NULL the Reference_Path is used. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [<s>Report</s>](Systems.Core.ReportQueries.md#report) | [Reports](General.Reports.md) | **OBSOLETE! Do not use!** The <see cref="General.Report"/> to which this ReportQuery belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` `Obsolete` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Core.ReportQueries.md#id) | guid |  
| [ObjectVersion](Systems.Core.ReportQueries.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Core.ReportQueries.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DependsOnChildRows

If True the data in the current report table contains only the rows that have child rows in sub-tables.`Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ExtensionsList

A comma separated list of report extension names. An extension is set of additional fields that participate in the query

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### FilterXml

Filter for the loaded table`Unit: obj.Report.QueryName`

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReferencePath

A sequence of table names and foreign key columns that define how the data will be loaded by this query. For example - Gen_Documents/Enterprise_Company_Id/Company_Id - will load the definition of the company for the enterprise company of a document.`Required`

Type: **string (512)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **512**  
Show in UI: **ShownByDefault**  

### ShowCustomProperties

True to include the custom properties.`Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **CannotBeShown**  

### ShowTextColumns

True to include text descriptions for certain columns.`Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **CannotBeShown**  

### TableName

The name of the report query. A Reference_Path can participate more than one time in the report but with different Report_Query_Name. This can be used to specify different filter for the same query. Can be NULL.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### UniqueName

The name of the data table in the printout datasource. If NULL the Reference_Path is used.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

Type: **int32**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Report

**OBSOLETE! Do not use!** The <see cref="General.Report"/> to which this ReportQuery belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` `Obsolete` `Owner`

Type: **[Reports](General.Reports.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
Return Type: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    Type: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    Type: string  
     Optional: True  
    Default Value: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **top**  
    The top clause - default is 10  
    Type: int32  
     Optional: True  
    Default Value: 10  

  * **skip**  
    The skip clause - default is 0  
    Type: int32  
     Optional: True  
    Default Value: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
Return Type: **void**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

**Parameters**  
  * **user**  
    The user.  
    Type: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    Type: string  

  * **subject**  
    The notification subject.  
    Type: string  

  * **priority**  
    The notification priority.  
    Type: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> Model Value: 1 <br /> Domain API Value: 'Background' |
    | Low | Low value. Stored as 2. <br /> Model Value: 2 <br /> Domain API Value: 'Low' |
    | Normal | Normal value. Stored as 3. <br /> Model Value: 3 <br /> Domain API Value: 'Normal' |
    | High | High value. Stored as 4. <br /> Model Value: 4 <br /> Domain API Value: 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> Model Value: 5 <br /> Domain API Value: 'Urgent' |

     Optional: True  
    Default Value: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Systems.Core.ReportQueries erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.ReportQueries erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Core_ReportQueries

Domain API Entity Type: 
Systems_Core_ReportQuery

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_ReportQueries?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_ReportQueries?$top=10>

