---
uid: Systems.Reporting.DataSources
---
# Systems.Reporting.DataSources Entity

**Namespace:** [Systems.Reporting](Systems.Reporting.md)  

Contains user-defined data sources, which retrieve rows from multiple queries. Entity: Sys_Data_Sources
## Renamed
**New name:** [Systems.Documents.DataSources](Systems.Documents.DataSources.md)  



## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Reporting.DataSources](Systems.Reporting.DataSources.md)  
  * [Systems.Reporting.DataSourceQueries](Systems.Reporting.DataSourceQueries.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseQueryName](Systems.Reporting.DataSources.md#basequeryname) | string (128) | The name of the query or table that is used for root reference point of the loaded data. `Required` `Filter(eq;like)` 
| [DataSourceType](Systems.Reporting.DataSources.md#datasourcetype) | [DataSourceType](Systems.Reporting.DataSources.md#datasourcetype) | 'M' = MULTI-TABLE (many tables); 'D' = MASTER-DETAIL (two tables); 'S' = SINGLE-TABLE . `Required` `Default("M")` `Filter(eq)` 
| [DisplayText](Systems.Reporting.DataSources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Reporting.DataSources.md#id) | guid |  
| [Name](Systems.Reporting.DataSources.md#name) | string (64) | The name of the data source. `Required` `Filter(eq;like)` 
| [ObjectVersion](Systems.Reporting.DataSources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ShowParentTables](Systems.Reporting.DataSources.md#showparenttables) | boolean | Indicates whether the parent nodes in the Reference_Path in Sys_Data_Source_<br />Queries_Table are automaticaly included in the report or not. `Required` `Default(false)` 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Queries | [DataSourceQueries](Systems.Reporting.DataSourceQueries.md) | List of `DataSourceQuery`(Systems.Reporting.DataSourceQueries.md) child objects, based on the `Systems.Reporting.DataSourceQuery.DataSource`(Systems.Reporting.DataSourceQueries.md#datasource) back reference 


## Attribute Details

### BaseQueryName

The name of the query or table that is used for root reference point of the loaded data. `Required` `Filter(eq;like)`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### DataSourceType

'M' = MULTI-TABLE (many tables); 'D' = MASTER-DETAIL (two tables); 'S' = SINGLE-TABLE . `Required` `Default("M")` `Filter(eq)`

_Type_: **[DataSourceType](Systems.Reporting.DataSources.md#datasourcetype)**  
_Category_: **System**  
Allowed values for the `DataSourceType`(Systems.Reporting.DataSources.md#datasourcetype) data attribute  
_Allowed Values (Systems.Reporting.DataSourcesRepository.DataSourceType Enum Members)_  

| Value | Description |
| ---- | --- |
| MultiTable | MultiTable value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'MultiTable' |
| MasterDetail | MasterDetail value. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'MasterDetail' |
| SingleTable | SingleTable value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'SingleTable' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **MultiTable**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Name

The name of the data source. `Required` `Filter(eq;like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ShowParentTables

Indicates whether the parent nodes in the Reference_Path in Sys_Data_Source_Queries_Table are automaticaly included in the report or not. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
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

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Systems.Reporting.DataSources erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Reporting.DataSources erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Reporting_DataSources?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Reporting_DataSources?$top=10>

