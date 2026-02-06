---
uid: Systems.Core.ObjectChanges
---
# Systems.Core.ObjectChanges


Actual tracked changes to one object.

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.ObjectChanges  
Base Table: Sys_Object_Changes  
Introduced In Version: 19.1  
API access:  ReadWrite  

## Visualization
Display Format: {RepositoryName}  
Search Members: RepositoryName  
Name Member: RepositoryName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  0 - Do not track changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Core.ObjectChangesets](Systems.Core.ObjectChangesets.md)  
Aggregate Root:  
[Systems.Core.ObjectChangesets](Systems.Core.ObjectChangesets.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ChangesJsonCompressed](Systems.Core.ObjectChanges.md#changesjsoncompressed) | byte[] __nullable__ | Contains JSON formatted attribute values. GZip compressed.[Introduced in version 24.1.4.29] 
| [ChangeType](Systems.Core.ObjectChanges.md#changetype) | [ChangeType](Systems.Core.ObjectChanges.md#changetype) | Type of change - Create, Update or Delete.[Required] 
| [EntityItemId](Systems.Core.ObjectChanges.md#entityitemid) | guid | The id of the actual changed object, described by this change. This is different than the aggregate root, which is pointed by Root Object. `Required` `Filter(multi eq)` 
| [<s>OldValuesJson</s>](Systems.Core.ObjectChanges.md#oldvaluesjson) | string (max) __nullable__ | **OBSOLETE! Do not use!** Old values in a name-value Json format. Only changed data attributes are recorded. Old values are recorded for update and delete.[Obsolete] [Obsoleted in version 22.1.6.61] 
| [RepositoryName](Systems.Core.ObjectChanges.md#repositoryname) | string (64) | The repository of the actual changed object, described by this change. This is different than the aggregate root, which is pointed by Root Object.[Required] [Filter(multi eq;like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ObjectChangeset](Systems.Core.ObjectChanges.md#objectchangeset) | [ObjectChangesets](Systems.Core.ObjectChangesets.md) | The changeset containing this change. |
| [RootObject](Systems.Core.ObjectChanges.md#rootobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The root object in the aggregate of the object, which has been changed. Each change is recorded at the aggregate root level. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Core.ObjectChanges.md#id) | guid |  
| [ObjectVersion](Systems.Core.ObjectChanges.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Core.ObjectChanges.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ChangesJsonCompressed

Contains JSON formatted attribute values. GZip compressed.[Introduced in version 24.1.4.29]

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ChangeType

Type of change - Create, Update or Delete.[Required]

Type: **[ChangeType](Systems.Core.ObjectChanges.md#changetype)**  
Category: **System**  
Allowed values for the `ChangeType`(Systems.Core.ObjectChanges.md#changetype) data attribute  
Allowed Values (Systems.Core.ObjectChangesRepository.ChangeType Enum Members)  

| Value | Description |
| ---- | --- |
| Create | Create value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 0 <br /> Domain API Value: 'Create' |
| Update | Update value. Stored as 'U'. <br /> Database Value: 'U' <br /> Model Value: 1 <br /> Domain API Value: 'Update' |
| Delete | Delete value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 2 <br /> Domain API Value: 'Delete' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### EntityItemId

The id of the actual changed object, described by this change. This is different than the aggregate root, which is pointed by Root Object. `Required` `Filter(multi eq)`

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OldValuesJson

**OBSOLETE! Do not use!** Old values in a name-value Json format. Only changed data attributes are recorded. Old values are recorded for update and delete.[Obsolete] [Obsoleted in version 22.1.6.61]

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### RepositoryName

The repository of the actual changed object, described by this change. This is different than the aggregate root, which is pointed by Root Object.[Required] [Filter(multi eq;like)]

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **64**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### ObjectChangeset

The changeset containing this change.

Type: **[ObjectChangesets](Systems.Core.ObjectChangesets.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### RootObject

The root object in the aggregate of the object, which has been changed. Each change is recorded at the aggregate root level.

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=Systems.Core.ObjectChanges erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.ObjectChanges erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Core_ObjectChanges

Domain API Entity Type: 
Systems_Core_ObjectChange

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_ObjectChanges?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_ObjectChanges?$top=10>

