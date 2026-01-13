---
uid: Systems.Documents.DataSourceQueries
---
# Systems.Documents.DataSourceQueries Entity

**Namespace:** [Systems.Documents](Systems.Documents.md)  

Represents a query within a data source. Entity: Sys_Data_Source_Queries

## Renames

Old name: **Systems.Reporting.DataSourceQueries**  
New name: **Systems.Documents.DataSourceQueries**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{TableName}_  
Default Search Members:  
_TableName_  
Name Data Member:  
_TableName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DataSources](Systems.Documents.DataSources.md)  
Aggregate Root:  
[Systems.Documents.DataSources](Systems.Documents.DataSources.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DependsOnChildRows](Systems.Documents.DataSourceQueries.md#dependsonchildrows) | [DependsOnChildRows](Systems.Documents.DataSourceQueries.md#dependsonchildrows) | Determines the visibility of rows in this table. 0 - allways visible; 1 - the row is visible if there is at least one child row; 2 - the row is visible if all sub-tables contain child rows. `Required` `Default(0)` 
| [DisplayText](Systems.Documents.DataSourceQueries.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExtensionsList](Systems.Documents.DataSourceQueries.md#extensionslist) | string (max) __nullable__ | A comma separated list of report extension names. An extension is set of additional fields that participate in the query. 
| [FilterXml](Systems.Documents.DataSourceQueries.md#filterxml) | dataaccessfilter __nullable__ | Filter for the loaded table. `Unit: obj.GetTableName()` 
| [FirstRow](Systems.Documents.DataSourceQueries.md#firstrow) | boolean | Specifies, that only the first row of the current query will be retrieved. Used and applied only when the data source type is not multitable. `Required` `Default(false)` 
| [Id](Systems.Documents.DataSourceQueries.md#id) | guid |  
| [ObjectVersion](Systems.Documents.DataSourceQueries.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ReferencePath](Systems.Documents.DataSourceQueries.md#referencepath) | string (max) | A sequence of table names and foreign key columns that define how the data will be loaded by this query. For example - Gen_Documents/<br />Enterprise_Company_<br />Id/Company_Id - will load the definition of the company for the enterprise company of a document. `Required` 
| [TableName](Systems.Documents.DataSourceQueries.md#tablename) | string (64) __nullable__ | The name of the report query. A Reference_Path can participate more than one time in the report but with different Report_Query_Name. This can be used to specify different filter for the same query. Can be null. 
| [UniqueName](Systems.Documents.DataSourceQueries.md#uniquename) | string (64) __nullable__ | The name of the data table in the printout datasource. If null the Reference_Path is used. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataSource](Systems.Documents.DataSourceQueries.md#datasource) | [DataSources](Systems.Documents.DataSources.md) | The report of the query. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DependsOnChildRows

Determines the visibility of rows in this table. 0 - allways visible; 1 - the row is visible if there is at least one child row; 2 - the row is visible if all sub-tables contain child rows. `Required` `Default(0)`

_Type_: **[DependsOnChildRows](Systems.Documents.DataSourceQueries.md#dependsonchildrows)**  
_Category_: **System**  
Allowed values for the `DependsOnChildRows`(Systems.Documents.DataSourceQueries.md#dependsonchildrows) data attribute  
_Allowed Values (Systems.Documents.DataSourceQueriesRepository.DependsOnChildRows Enum Members)_  

| Value | Description |
| ---- | --- |
| NoChildRowDependency | NoChildRowDependency value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NoChildRowDependency' |
| TheRowIsVisible<br />IfThereIsAtLeast<br />OneChildRow | TheRowIsVisible<br />IfThereIsAtLeast<br />OneChildRow value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'TheRowIsVisible<br />IfThereIsAtLeast<br />OneChildRow' |
| TheRowIsVisible<br />IfAllSubTables<br />ContainChildRows | TheRowIsVisible<br />IfAllSubTables<br />ContainChildRows value. Stored as 2. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'TheRowIsVisible<br />IfAllSubTables<br />ContainChildRows' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExtensionsList

A comma separated list of report extension names. An extension is set of additional fields that participate in the query.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### FilterXml

Filter for the loaded table. `Unit: obj.GetTableName()`

_Type_: **dataaccessfilter __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### FirstRow

Specifies, that only the first row of the current query will be retrieved. Used and applied only when the data source type is not multitable. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ReferencePath

A sequence of table names and foreign key columns that define how the data will be loaded by this query. For example - Gen_Documents/Enterprise_Company_Id/Company_Id - will load the definition of the company for the enterprise company of a document. `Required`

_Type_: **string (max)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### TableName

The name of the report query. A Reference_Path can participate more than one time in the report but with different Report_Query_Name. This can be used to specify different filter for the same query. Can be null.

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### UniqueName

The name of the data table in the printout datasource. If null the Reference_Path is used.

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### DataSource

The report of the query. `Required` `Filter(multi eq)` `Owner`

_Type_: **[DataSources](Systems.Documents.DataSources.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    _Type_: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    _Type_: string  
     _Optional_: True  
    _Default Value_: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **top**  
    The top clause - default is 10  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 10  

  * **skip**  
    The skip clause - default is 0  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
_Return Type_: **void**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  

**Parameters**  
  * **user**  
    The user.  
    _Type_: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    _Type_: string  

  * **subject**  
    The notification subject.  
    _Type_: string  

  * **priority**  
    The notification priority.  
    _Type_: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    _Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)_  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Background' |
    | Low | Low value. Stored as 2. <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Low' |
    | Normal | Normal value. Stored as 3. <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Normal' |
    | High | High value. Stored as 4. <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Urgent' |

     _Optional_: True  
    _Default Value_: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


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

