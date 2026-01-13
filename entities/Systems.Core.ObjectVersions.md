---
uid: Systems.Core.ObjectVersions
---
# Systems.Core.ObjectVersions Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Contains history of saved version of the managed objects. Entity: Sys_Object_Versions

## Default Visualization
Default Display Text Format:  
_{Object}_  
Default Search Members:  
_Object_  
Name Data Member:  
_Object_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Core.ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)  
Aggregate Root:  
[Systems.Core.ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Core.ObjectVersions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Core.ObjectVersions.md#id) | guid |  
| [ObjectContents](Systems.Core.ObjectVersions.md#objectcontents) | byte[] | The compressed contents of the object. `Required` 
| [ObjectVersion](Systems.Core.ObjectVersions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ServerVersion](Systems.Core.ObjectVersions.md#serverversion) | string (15) __nullable__ | The version of the EnterpriseOne server, which created the version. The version should be in the form (9.9.9.9). null means the version is unknown. 
| [Version](Systems.Core.ObjectVersions.md#version) | int32 | The version number of the version, stored in the current row, starting from 1. `Required` `Filter(multi eq;ge;le)` 
| [VersionTime](Systems.Core.ObjectVersions.md#versiontime) | datetime | The timestamp when the version was saved. `Required` `Filter(ge;le)` 
| [VersionType](Systems.Core.ObjectVersions.md#versiontype) | [VersionType](Systems.Core.ObjectVersions.md#versiontype) | Specifies the action, which occurred on the actual object, referred by the system object.  'C' means that with this version the object was created. 'U' means that this is an update to an existing object. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Object](Systems.Core.ObjectVersions.md#object) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The object, for which a version is stored. `Required` `Filter(multi eq)` `Owner` |
| [User](Systems.Core.ObjectVersions.md#user) | [Users](Systems.Security.Users.md) | The user, which saved the version. `Required` `Filter(multi eq)` |


## Attribute Details

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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### ObjectContents

The compressed contents of the object. `Required`

_Type_: **byte[]**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ServerVersion

The version of the EnterpriseOne server, which created the version. The version should be in the form (9.9.9.9). null means the version is unknown.

_Type_: **string (15) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **15**  
_Show in UI_: **ShownByDefault**  

### Version

The version number of the version, stored in the current row, starting from 1. `Required` `Filter(multi eq;ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### VersionTime

The timestamp when the version was saved. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### VersionType

Specifies the action, which occurred on the actual object, referred by the system object.  'C' means that with this version the object was created. 'U' means that this is an update to an existing object. `Required`

_Type_: **[VersionType](Systems.Core.ObjectVersions.md#versiontype)**  
_Category_: **System**  
Allowed values for the `VersionType`(Systems.Core.ObjectVersions.md#versiontype) data attribute  
_Allowed Values (Systems.Core.ObjectVersionsRepository.VersionType Enum Members)_  

| Value | Description |
| ---- | --- |
| Create | Create value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Create' |
| Update | Update value. Stored as 'U'. <br /> _Database Value:_ 'U' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Update' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Object

The object, for which a version is stored. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### User

The user, which saved the version. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

