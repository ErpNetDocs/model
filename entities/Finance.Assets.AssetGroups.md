---
uid: Finance.Assets.AssetGroups
---
# Finance.Assets.AssetGroups


User-defined grouping of the assets.

## General
Namespace: [Finance.Assets](Finance.Assets.md)  
Repository: Finance.Assets.AssetGroups  
Base Table: Ast_Asset_Groups  
API access:  ReadWrite  

## Visualization
Display Format: {Name}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Assets.AssetGroups](Finance.Assets.AssetGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Finance.Assets.AssetGroups.md#code) | string (20) | The unique code of the AssetGroup. `Required` `Filter(eq)` `ORD` 
| [Name](Finance.Assets.AssetGroups.md#name) | string (254) | The name of this AssetGroup. `Required` `Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultValuationModel](Finance.Assets.AssetGroups.md#defaultvaluationmodel) | [ValuationModels](Finance.Assets.ValuationModels.md) (nullable) | Default valuation model when creating new assets from this group |
| [Parent](Finance.Assets.AssetGroups.md#parent) | [AssetGroups](Finance.Assets.AssetGroups.md) (nullable) | Parent asset group in the hierarchy. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Assets.AssetGroups.md#id) | guid |  
| [ObjectVersion](Finance.Assets.AssetGroups.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Finance.Assets.AssetGroups.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Assets.AssetGroups.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Finance.Assets.AssetGroups.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Finance.Assets.AssetGroups.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Code

The unique code of the AssetGroup. `Required` `Filter(eq)` `ORD`

Type: **string (20)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Maximum Length: **20**  
Show in UI: **ShownByDefault**  

### Name

The name of this AssetGroup. `Required` `Filter(like)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
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


## Reference Details

### DefaultValuationModel

Default valuation model when creating new assets from this group

Type: **[ValuationModels](Finance.Assets.ValuationModels.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### Parent

Parent asset group in the hierarchy. `Filter(multi eq)`

Type: **[AssetGroups](Finance.Assets.AssetGroups.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Finance.Assets.AssetGroups erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Assets.AssetGroups erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Assets_AssetGroups

Domain API Entity Type: 
Finance_Assets_AssetGroup

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Assets_AssetGroups?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Assets_AssetGroups?$top=10>

