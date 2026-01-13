---
uid: Communities.Social.GroupMembers
---
# Communities.Social.GroupMembers Entity

**Namespace:** [Communities.Social](Communities.Social.md)  

Represents the membership of a user in a social group. Entity: Cmm_Social_Group_Members (Introduced in version 20.1)

## Default Visualization
Default Display Text Format:  
_{SocialGroup.Name}_  
Default Search Members:  
_SocialGroup.Name_  
Name Data Member:  
_SocialGroup.Name_  
Category:  _Definitions_  
Show in UI:  _CannotBeShown_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Communities.Social.Groups](Communities.Social.Groups.md)  
Aggregate Root:  
[Communities.Social.Groups](Communities.Social.Groups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Communities.Social.GroupMembers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [HistoryVisibleSinceTimeUtc](Communities.Social.GroupMembers.md#historyvisiblesincetimeutc) | datetime __nullable__ | Inclusive UTC timestamp that marks the earliest history item returned; records older than this moment are hidden. null removes the cutoff, exposing the full history. `Filter(ge;le)` `Introduced in version 26.1.4.14` 
| [Id](Communities.Social.GroupMembers.md#id) | guid |  
| [JoinTimeUtc](Communities.Social.GroupMembers.md#jointimeutc) | datetime | The exact server time (in UTC), when the user joined the group. `Required` `Default(NowUtc)` `Filter(ge;le)` 
| [LastSeenTimeUtc](Communities.Social.GroupMembers.md#lastseentimeutc) | datetime __nullable__ | The time (in UTC) until the group member caught up with the content in the corresponding group. null indicates that the group has no content or the member has never interacted with it. `Filter(ge;le)` `Introduced in version 26.1.4.14` 
| [ObjectVersion](Communities.Social.GroupMembers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Role](Communities.Social.GroupMembers.md#role) | [Role](Communities.Social.GroupMembers.md#role) | Member role in a group. Defaults to member. `Required` `Default("M")` `Filter(multi eq)` `Introduced in version 23.1.1.95` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [SocialGroup](Communities.Social.GroupMembers.md#socialgroup) | [Groups](Communities.Social.Groups.md) | The group in which the user participates. `Required` `Filter(multi eq)` `Owner` |
| [User](Communities.Social.GroupMembers.md#user) | [Users](Systems.Security.Users.md) | The user, who is a member of the group. `Required` `Filter(multi eq)` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### HistoryVisibleSinceTimeUtc

Inclusive UTC timestamp that marks the earliest history item returned; records older than this moment are hidden. null removes the cutoff, exposing the full history. `Filter(ge;le)` `Introduced in version 26.1.4.14`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### JoinTimeUtc

The exact server time (in UTC), when the user joined the group. `Required` `Default(NowUtc)` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### LastSeenTimeUtc

The time (in UTC) until the group member caught up with the content in the corresponding group. null indicates that the group has no content or the member has never interacted with it. `Filter(ge;le)` `Introduced in version 26.1.4.14`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Role

Member role in a group. Defaults to member. `Required` `Default("M")` `Filter(multi eq)` `Introduced in version 23.1.1.95`

_Type_: **[Role](Communities.Social.GroupMembers.md#role)**  
_Category_: **System**  
Allowed values for the `Role`(Communities.Social.GroupMembers.md#role) data attribute  
_Allowed Values (Communities.Social.GroupMembersRepository.Role Enum Members)_  

| Value | Description |
| ---- | --- |
| Member | Member. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Member' |
| Admin | Admin. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Admin' |
| Observer | Mostly, read-only permissions. Can like comments.. Stored as 'O'. <br /> _Database Value:_ 'O' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Observer' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Member**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### SocialGroup

The group in which the user participates. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Groups](Communities.Social.Groups.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### User

The user, who is a member of the group. `Required` `Filter(multi eq)`

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

[!list limit=1000 erp.entity=Communities.Social.GroupMembers erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Communities.Social.GroupMembers erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Communities_Social_GroupMembers

Domain API Entity Type: 
Communities_Social_GroupMember

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Communities_Social_GroupMembers?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Communities_Social_GroupMembers?$top=10>

