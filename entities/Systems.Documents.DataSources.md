---
uid: Systems.Documents.DataSources
---
# Systems.Documents.DataSources


Contains user-defined data sources, which retrieve rows from multiple queries.

## General
Namespace: [Systems.Documents](Systems.Documents.md)  
Repository: Systems.Documents.DataSources  
Base Table: Sys_Data_Sources  
API access:  ReadWrite  

## Renames

Old name: Systems.Reporting.DataSources  
New name: Systems.Documents.DataSources  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Name}  
Search Members: Name  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Documents.DataSources](Systems.Documents.DataSources.md)  
  * [Systems.Documents.DataSourceQueries](Systems.Documents.DataSourceQueries.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseQueryName](Systems.Documents.DataSources.md#basequeryname) | string (128) | Name of the root query of the data source. Can be table name.`Required` `Filter(eq;like)` 
| [DataSourceType](Systems.Documents.DataSources.md#datasourcetype) | [DataSourceType](Systems.Documents.DataSources.md#datasourcetype) | 'M' = MULTI-TABLE (many tables); 'D' = MASTER-DETAIL (two tables); 'S' = SINGLE-TABLE `Required` `Default(&quot;M&quot;)` `Filter(eq)` 
| [Name](Systems.Documents.DataSources.md#name) | string (64) | Name of the data source.`Required` `Filter(eq;like)` 
| [ShowParentTables](Systems.Documents.DataSources.md#showparenttables) | boolean | Indicates whether the unchecked tables that exist in a reference path of a checked table are participating in the data`Required` `Default(false)` 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Documents.DataSources.md#id) | guid |  
| [ObjectVersion](Systems.Documents.DataSources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Documents.DataSources.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Documents.DataSources.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Documents.DataSources.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Documents.DataSources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Queries | [DataSourceQueries](Systems.Documents.DataSourceQueries.md) | List of `DataSourceQuery`(Systems.Documents.DataSourceQueries.md) child objects, based on the `Systems.Documents.DataSourceQuery.DataSource`(Systems.Documents.DataSourceQueries.md#datasource) back reference 


## Attribute Details

### BaseQueryName

Name of the root query of the data source. Can be table name.`Required` `Filter(eq;like)`

Type: **string (128)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### DataSourceType

'M' = MULTI-TABLE (many tables); 'D' = MASTER-DETAIL (two tables); 'S' = SINGLE-TABLE `Required` `Default(&quot;M&quot;)` `Filter(eq)`

Type: **[DataSourceType](Systems.Documents.DataSources.md#datasourcetype)**  
Category: **System**  
Allowed values for the `DataSourceType`(Systems.Documents.DataSources.md#datasourcetype) data attribute  
Allowed Values (Systems.Documents.DataSourcesRepository.DataSourceType Enum Members)  

| Value | Description |
| ---- | --- |
| MultiTable | MultiTable value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 0 <br /> Domain API Value: 'MultiTable' |
| MasterDetail | MasterDetail value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 1 <br /> Domain API Value: 'MasterDetail' |
| SingleTable | SingleTable value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 2 <br /> Domain API Value: 'SingleTable' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **MultiTable**  
Show in UI: **ShownByDefault**  

### Name

Name of the data source.`Required` `Filter(eq;like)`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### ShowParentTables

Indicates whether the unchecked tables that exist in a reference path of a checked table are participating in the data`Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

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

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

[!list limit=1000 erp.entity=Systems.Documents.DataSources erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.DataSources erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_DataSources

Domain API Entity Type: 
Systems_Documents_DataSource

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_DataSources?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_DataSources?$top=10>

