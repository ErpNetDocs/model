---
uid: Systems.Core.ObjectVersions
---
# Systems.Core.ObjectVersions


Contains history of saved version of the managed objects.

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.ObjectVersions  
Base Table: Sys_Object_Versions  
API access:  ReadWrite  

## Visualization
Display Format: {Object}  
Search Members: Object  
Name Member: Object  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Core.ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)  
Aggregate Root:  
[Systems.Core.ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ObjectContents](Systems.Core.ObjectVersions.md#objectcontents) | byte[] | The compressed contents of the object.`Required` 
| [ServerVersion](Systems.Core.ObjectVersions.md#serverversion) | string (15) __nullable__ | The version of the EnterpriseOne server, which created the version. The version should be in the form (9.9.9.9). NULL means the version is unknown. 
| [Version](Systems.Core.ObjectVersions.md#version) | int32 | The version number of the version, stored in the current row, starting from 1.`Required` `Filter(multi eq;ge;le)` 
| [VersionTime](Systems.Core.ObjectVersions.md#versiontime) | datetime | The timestamp when the version was saved.`Required` `Filter(ge;le)` 
| [VersionType](Systems.Core.ObjectVersions.md#versiontype) | [VersionType](Systems.Core.ObjectVersions.md#versiontype) | Specifies the action, which occurred on the actual object, referred by the system object.  'C' means that with this version the object was created. 'U' means that this is an update to an existing object.`Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Object](Systems.Core.ObjectVersions.md#object) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The object, for which a version is stored. |
| [User](Systems.Core.ObjectVersions.md#user) | [Users](Systems.Security.Users.md) | The user, which saved the version. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Core.ObjectVersions.md#id) | guid |  
| [ObjectVersion](Systems.Core.ObjectVersions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Core.ObjectVersions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ObjectContents

The compressed contents of the object.`Required`

Type: **byte[]**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

### ServerVersion

The version of the EnterpriseOne server, which created the version. The version should be in the form (9.9.9.9). NULL means the version is unknown.

Type: **string (15) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **15**  
Show in UI: **ShownByDefault**  

### Version

The version number of the version, stored in the current row, starting from 1.`Required` `Filter(multi eq;ge;le)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### VersionTime

The timestamp when the version was saved.`Required` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### VersionType

Specifies the action, which occurred on the actual object, referred by the system object.  'C' means that with this version the object was created. 'U' means that this is an update to an existing object.`Required`

Type: **[VersionType](Systems.Core.ObjectVersions.md#versiontype)**  
Category: **System**  
Allowed values for the `VersionType`(Systems.Core.ObjectVersions.md#versiontype) data attribute  
Allowed Values (Systems.Core.ObjectVersionsRepository.VersionType Enum Members)  

| Value | Description |
| ---- | --- |
| Create | Create value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 0 <br /> Domain API Value: 'Create' |
| Update | Update value. Stored as 'U'. <br /> Database Value: 'U' <br /> Model Value: 1 <br /> Domain API Value: 'Update' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
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

### Object

The object, for which a version is stored.

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### User

The user, which saved the version.

Type: **[Users](Systems.Security.Users.md)**  
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

[!list limit=1000 erp.entity=Systems.Core.ObjectVersions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.ObjectVersions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Core_ObjectVersions

Domain API Entity Type: 
Systems_Core_ObjectVersion

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_ObjectVersions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_ObjectVersions?$top=10>

