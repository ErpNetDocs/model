---
uid: Systems.Security.AccessKeys
---
# Systems.Security.AccessKeys Entity

**Namespace:** [Systems.Security](Systems.Security.md)  

An Access key defines a set of access permissions to one or more entities. Access keys can be private, securing only one entity, or shared between more entities (of the same data type). The actual permissions are specified for security groups. Each group can have different specific permissions. Entity: Sec_Access_Keys

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _SystemData_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Security.AccessKeys](Systems.Security.AccessKeys.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Systems.Security.AccessKeys.md#code) | string (16) __nullable__ | Unique code for the access key. The codes can be null for legacy keys or entities that do not support codes. The codes are unique only among non-null entries. `Filter(eq;like)` `ORD` 
| [DisplayText](Systems.Security.AccessKeys.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EntityId](Systems.Security.AccessKeys.md#entityid) | guid __nullable__ | The field stores the Id of the entity that the key was created from. `Filter(multi eq)` `Introduced in version 25.1.1.32` 
| [EntityName](Systems.Security.AccessKeys.md#entityname) | string (64) __nullable__ | What entitity the key secures. Can be null for private, legacy keys. `Filter(eq;like)` `ORD` 
| [ExternalId](Systems.Security.AccessKeys.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Security.AccessKeys.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Security.AccessKeys.md#id) | guid |  
| [Name](Systems.Security.AccessKeys.md#name) | [MultilanguageString (1024)](../data-types.md#multilanguagestring) __nullable__ | Multilanguage descriptive name of the security key. Can be null for legacy keys. `Filter(eq;like)` 
| [ObjectVersion](Systems.Security.AccessKeys.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ShareLevel](Systems.Security.AccessKeys.md#sharelevel) | [ShareLevel](Systems.Security.AccessKeys.md#sharelevel) | Specifies the extent to which the key can be shared among multiple entities. `Required` `Default("PRI")` `Filter(eq)` `Introduced in version 25.1.1.32` 


## Attribute Details

### Code

Unique code for the access key. The codes can be null for legacy keys or entities that do not support codes. The codes are unique only among non-null entries. `Filter(eq;like)` `ORD`

_Type_: **string (16) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.IncMax( o => o.Code, o => ( o.EntityName == obj.EntityName), "00000")`

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EntityId

The field stores the Id of the entity that the key was created from. `Filter(multi eq)` `Introduced in version 25.1.1.32`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### EntityName

What entitity the key secures. Can be null for private, legacy keys. `Filter(eq;like)` `ORD`

_Type_: **string (64) __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
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

### Name

Multilanguage descriptive name of the security key. Can be null for legacy keys. `Filter(eq;like)`

_Type_: **[MultilanguageString (1024)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ShareLevel

Specifies the extent to which the key can be shared among multiple entities. `Required` `Default("PRI")` `Filter(eq)` `Introduced in version 25.1.1.32`

_Type_: **[ShareLevel](Systems.Security.AccessKeys.md#sharelevel)**  
_Category_: **System**  
Allowed values for the `ShareLevel`(Systems.Security.AccessKeys.md#sharelevel) data attribute  
_Allowed Values (Systems.Security.AccessKeysRepository.ShareLevel Enum Members)_  

| Value | Description |
| ---- | --- |
| Private | The key is private to the entity.. Stored as 'PRI'. <br /> _Database Value:_ 'PRI' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Private' |
| Referenceable | The key can be referenced from other entities.. Stored as 'RFA'. <br /> _Database Value:_ 'RFA' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Referenceable' |
| Referencing | The access permissions of the selected object are applied.. Stored as 'RFI'. <br /> _Database Value:_ 'RFI' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Referencing' |
| Inheriting | The access permissions of the parent object are inherited.. Stored as 'IHI'. <br /> _Database Value:_ 'IHI' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Inheriting' |
| Shared | The key is not specific to any entity.. Stored as 'SHA'. <br /> _Database Value:_ 'SHA' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Shared' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Private**  
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

[!list limit=1000 erp.entity=Systems.Security.AccessKeys erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.AccessKeys erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_AccessKeys

Domain API Entity Type: 
Systems_Security_AccessKey

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_AccessKeys?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_AccessKeys?$top=10>

