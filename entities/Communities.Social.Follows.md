---
uid: Communities.Social.Follows
---
# Communities.Social.Follows Entity

**Namespace:** [Communities.Social](Communities.Social.md)  

Denotes a user following an object in the system. The user will be notified for events about the object. Entity: Cmm_Social_Follows (Introduced in version 22.1.6.73)

## Default Visualization
Default Display Text Format:  
_{Id}: {DataObjectId}_  
Default Search Members:  
__  
Category:  _Definitions_  
Show in UI:  _CannotBeShown_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Communities.Social.Follows](Communities.Social.Follows.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](Communities.Social.Follows.md#creationtimeutc) | datetime | The exact server time (in UTC), when the follow was created. `Required` `Default(NowUtc)` `Filter(ge;le)` 
| [DisplayText](Communities.Social.Follows.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Communities.Social.Follows.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Communities.Social.Follows.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FollowLevel](Communities.Social.Follows.md#followlevel) | [FollowLevel](Communities.Social.Follows.md#followlevel) | Indicates the level of user’s interest for this object. `Required` `Default("TAG")` `Filter(multi eq)` `Introduced in version 26.2.0.70` 
| [Id](Communities.Social.Follows.md#id) | guid |  
| [ObjectVersion](Communities.Social.Follows.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Communities.Social.Follows.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The object being followed by the user. `Required` `Filter(multi eq)` |
| [User](Communities.Social.Follows.md#user) | [Users](Systems.Security.Users.md) | The user which follows the object. `Required` `Filter(multi eq)` |


## Attribute Details

### CreationTimeUtc

The exact server time (in UTC), when the follow was created. `Required` `Default(NowUtc)` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

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

### FollowLevel

Indicates the level of user’s interest for this object. `Required` `Default("TAG")` `Filter(multi eq)` `Introduced in version 26.2.0.70`

_Type_: **[FollowLevel](Communities.Social.Follows.md#followlevel)**  
_Category_: **System**  
Allowed values for the `FollowLevel`(Communities.Social.Follows.md#followlevel) data attribute  
_Allowed Values (Communities.Social.FollowsRepository.FollowLevel Enum Members)_  

| Value | Description |
| ---- | --- |
| Tagged | Automatically followed due to mention or assignment.. Stored as 'TAG'. <br /> _Database Value:_ 'TAG' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Tagged' |
| Follow | User willingly chose to follow this object.. Stored as 'FLW'. <br /> _Database Value:_ 'FLW' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Follow' |
| Favorite | User marked this object as a favorite.. Stored as 'FAV'. <br /> _Database Value:_ 'FAV' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Favorite' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Tagged**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### DataObject

The object being followed by the user. `Required` `Filter(multi eq)`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### User

The user which follows the object. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Communities.Social.Follows erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Communities.Social.Follows erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Communities_Social_Follows

Domain API Entity Type: 
Communities_Social_Follow

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Communities_Social_Follows?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Communities_Social_Follows?$top=10>

