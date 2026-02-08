---
uid: Systems.Documents.DataSourceQueries
---
# Systems.Documents.DataSourceQueries


Represents a query within a data source.

## General
Namespace: [Systems.Documents](Systems.Documents.md)  
Repository: Systems.Documents.DataSourceQueries  
Base Table: Sys_Data_Source_Queries  
API access:  ReadWrite  

## Renames

Old name: Systems.Reporting.DataSourceQueries  
New name: Systems.Documents.DataSourceQueries  
Version: 24.1.5.35  
Case: 35911  



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
[Systems.Documents.DataSources](Systems.Documents.DataSources.md)  
Aggregate Root:  
[Systems.Documents.DataSources](Systems.Documents.DataSources.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DependsOnChildRows](Systems.Documents.DataSourceQueries.md#dependsonchildrows) | [DependsOnChildRows](Systems.Documents.DataSourceQueries.md#dependsonchildrows) | Determines the visibility of rows in this table depending on the rows in the sub-tables`Required` `Default(0)` 
| [ExtensionsList](Systems.Documents.DataSourceQueries.md#extensionslist) | string (max) __nullable__ | A comma separated list of report extension names. An extension is set of additional fields that participate in the query 
| [FilterXml](Systems.Documents.DataSourceQueries.md#filterxml) | dataaccessfilter __nullable__ | Filter for the data from the current table.`Unit: obj.GetTableName()` 
| [FirstRow](Systems.Documents.DataSourceQueries.md#firstrow) | boolean | Specifies, that only the first row of the current query will be retrieved. Used and applied only when the data source type is not multitable.`Required` `Default(false)` 
| [ReferencePath](Systems.Documents.DataSourceQueries.md#referencepath) | string (max) | A sequence of tables ordered by their references.`Required` 
| [TableName](Systems.Documents.DataSourceQueries.md#tablename) | string (64) __nullable__ | The name of the report query. A Reference_Path can participate more than one time in the report but with different Report_Query_Name. This can be used to specify different filter for the same query. Can be NULL. 
| [UniqueName](Systems.Documents.DataSourceQueries.md#uniquename) | string (64) __nullable__ | If not empty for the current query will be created separate set of tables with unique prefix in their names.  

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataSource](Systems.Documents.DataSourceQueries.md#datasource) | [DataSources](Systems.Documents.DataSources.md) | The report of the query. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Documents.DataSourceQueries.md#id) | guid |  
| [ObjectVersion](Systems.Documents.DataSourceQueries.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Documents.DataSourceQueries.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DependsOnChildRows

Determines the visibility of rows in this table depending on the rows in the sub-tables`Required` `Default(0)`

Type: **[DependsOnChildRows](Systems.Documents.DataSourceQueries.md#dependsonchildrows)**  
Category: **System**  
Allowed values for the `DependsOnChildRows`(Systems.Documents.DataSourceQueries.md#dependsonchildrows) data attribute  
Allowed Values (Systems.Documents.DataSourceQueriesRepository.DependsOnChildRows Enum Members)  

| Value | Description |
| ---- | --- |
| NoChildRowDependency | NoChildRowDependency value. Stored as 0. <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'NoChildRowDependency' |
| TheRowIsVisible<br />IfThereIsAtLeast<br />OneChildRow | TheRowIsVisible<br />IfThereIsAtLeast<br />OneChildRow value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'TheRowIsVisible<br />IfThereIsAtLeast<br />OneChildRow' |
| TheRowIsVisible<br />IfAllSubTables<br />ContainChildRows | TheRowIsVisible<br />IfAllSubTables<br />ContainChildRows value. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'TheRowIsVisible<br />IfAllSubTables<br />ContainChildRows' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
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

Filter for the data from the current table.`Unit: obj.GetTableName()`

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FirstRow

Specifies, that only the first row of the current query will be retrieved. Used and applied only when the data source type is not multitable.`Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ReferencePath

A sequence of tables ordered by their references.`Required`

Type: **string (max)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### TableName

The name of the report query. A Reference_Path can participate more than one time in the report but with different Report_Query_Name. This can be used to specify different filter for the same query. Can be NULL.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### UniqueName

If not empty for the current query will be created separate set of tables with unique prefix in their names.

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

### DataSource

The report of the query.

Type: **[DataSources](Systems.Documents.DataSources.md)**  
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

[!list limit=1000 erp.entity=Systems.Documents.DataSourceQueries erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.DataSourceQueries erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_DataSourceQueries

Domain API Entity Type: 
Systems_Documents_DataSourceQuery

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_DataSourceQueries?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_DataSourceQueries?$top=10>

