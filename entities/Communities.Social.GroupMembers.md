---
uid: Communities.Social.GroupMembers
---
# Communities.Social.GroupMembers


Represents the membership of a user in a social group.

## General
Namespace: [Communities.Social](Communities.Social.md)  
Repository: Communities.Social.GroupMembers  
Base Table: Cmm_Social_Group_Members  
Introduced In Version: 20.1  
API access:  ReadWrite  

## Visualization
Display Format: {SocialGroup.Name}  
Search Members: SocialGroup.Name  
Name Member: SocialGroup.Name  
Category:  Definitions  
Show in UI:  CannotBeShown  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Communities.Social.Groups](Communities.Social.Groups.md)  
Aggregate Root:  
[Communities.Social.Groups](Communities.Social.Groups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [HistoryVisibleSinceTimeUtc](Communities.Social.GroupMembers.md#historyvisiblesincetimeutc) | datetime __nullable__ | Inclusive UTC timestamp that marks the earliest history item returned; records older than this moment are hidden. NULL removes the cutoff, exposing the full history.`Filter(ge;le)` `Introduced in version 26.1.4.14` 
| [JoinTimeUtc](Communities.Social.GroupMembers.md#jointimeutc) | datetime | The exact server time (in UTC), when the user joined the group.`Required` `Default(NowUtc)` `Filter(ge;le)` 
| [LastSeenTimeUtc](Communities.Social.GroupMembers.md#lastseentimeutc) | datetime __nullable__ | The time (in UTC) until the group member caught up with the content in the corresponding group. NULL indicates that the group has no content or the member has never interacted with it.`Filter(ge;le)` `Introduced in version 26.1.4.14` 
| [Role](Communities.Social.GroupMembers.md#role) | [Role](Communities.Social.GroupMembers.md#role) | Member role in a group. Defaults to member.`Required` `Default(&quot;M&quot;)` `Filter(multi eq)` `Introduced in version 23.1.1.95` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [SocialGroup](Communities.Social.GroupMembers.md#socialgroup) | [Groups](Communities.Social.Groups.md) | The group in which the user participates. |
| [User](Communities.Social.GroupMembers.md#user) | [Users](Systems.Security.Users.md) | The user, who is a member of the group. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Communities.Social.GroupMembers.md#id) | guid |  
| [ObjectVersion](Communities.Social.GroupMembers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Communities.Social.GroupMembers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### HistoryVisibleSinceTimeUtc

Inclusive UTC timestamp that marks the earliest history item returned; records older than this moment are hidden. NULL removes the cutoff, exposing the full history.`Filter(ge;le)` `Introduced in version 26.1.4.14`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### JoinTimeUtc

The exact server time (in UTC), when the user joined the group.`Required` `Default(NowUtc)` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### LastSeenTimeUtc

The time (in UTC) until the group member caught up with the content in the corresponding group. NULL indicates that the group has no content or the member has never interacted with it.`Filter(ge;le)` `Introduced in version 26.1.4.14`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Role

Member role in a group. Defaults to member.`Required` `Default(&quot;M&quot;)` `Filter(multi eq)` `Introduced in version 23.1.1.95`

Type: **[Role](Communities.Social.GroupMembers.md#role)**  
Category: **System**  
Allowed values for the `Role`(Communities.Social.GroupMembers.md#role) data attribute  
Allowed Values (Communities.Social.GroupMembersRepository.Role Enum Members)  

| Value | Description |
| ---- | --- |
| Member | Member. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 0 <br /> Domain API Value: 'Member' |
| Admin | Admin. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 1 <br /> Domain API Value: 'Admin' |
| Observer | Mostly, read-only permissions. Can like comments.. Stored as 'O'. <br /> Database Value: 'O' <br /> Model Value: 2 <br /> Domain API Value: 'Observer' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Member**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

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

### SocialGroup

The group in which the user participates.

Type: **[Groups](Communities.Social.Groups.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### User

The user, who is a member of the group.

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

