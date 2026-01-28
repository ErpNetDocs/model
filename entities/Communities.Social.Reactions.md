---
uid: Communities.Social.Reactions
---
# Communities.Social.Reactions


Reaction of a user to any social comment to an object of the system.

## General
Namespace: [Communities.Social](Communities.Social.md)  
Repository: Communities.Social.Reactions  
Base Table: Cmm_Social_Reactions  
Introduced In Version: 20.1  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {DataObjectId}  
Search Members:   
Category:  Definitions  
Show in UI:  CannotBeShown  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Communities.Social.Reactions](Communities.Social.Reactions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](Communities.Social.Reactions.md#creationtimeutc) | datetime | The exact server time (in UTC), when the reaction was created. `Required` `Default(NowUtc)` `Filter(ge;le)` 
| [ReactionType](Communities.Social.Reactions.md#reactiontype) | [ReactionType](Communities.Social.Reactions.md#reactiontype) | The type of the reaction. LIK = Like; LOV = Love; HAH = Haha; WOW = Wow; SAD = Sad; ANG = Angry. `Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Communities.Social.Reactions.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The root data object (post, marketplace product, document, etc), for which the reaction is. `Required` `Filter(multi eq)` |
| [SocialComment](Communities.Social.Reactions.md#socialcomment) | [Comments](Communities.Social.Comments.md) (nullable) | When not null, specifies that the reaction is for the specified comment within the data object. `Filter(multi eq)` |
| [User](Communities.Social.Reactions.md#user) | [Users](Systems.Security.Users.md) | The user, who reacted. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Communities.Social.Reactions.md#id) | guid |  
| [ObjectVersion](Communities.Social.Reactions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Communities.Social.Reactions.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Communities.Social.Reactions.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Communities.Social.Reactions.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Communities.Social.Reactions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CreationTimeUtc

The exact server time (in UTC), when the reaction was created. `Required` `Default(NowUtc)` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### ReactionType

The type of the reaction. LIK = Like; LOV = Love; HAH = Haha; WOW = Wow; SAD = Sad; ANG = Angry. `Required` `Filter(multi eq)`

Type: **[ReactionType](Communities.Social.Reactions.md#reactiontype)**  
Category: **System**  
Allowed values for the `ReactionType`(Communities.Social.Reactions.md#reactiontype) data attribute  
Allowed Values (Communities.Social.ReactionsRepository.ReactionType Enum Members)  

| Value | Description |
| ---- | --- |
| Like | Like value. Stored as 'LIK'. <br /> Database Value: 'LIK' <br /> Model Value: 0 <br /> Domain API Value: 'Like' |
| Love | Love value. Stored as 'LOV'. <br /> Database Value: 'LOV' <br /> Model Value: 1 <br /> Domain API Value: 'Love' |
| Haha | Haha value. Stored as 'HAH'. <br /> Database Value: 'HAH' <br /> Model Value: 2 <br /> Domain API Value: 'Haha' |
| Wow | Wow value. Stored as 'WOW'. <br /> Database Value: 'WOW' <br /> Model Value: 3 <br /> Domain API Value: 'Wow' |
| Sad | Sad value. Stored as 'SAD'. <br /> Database Value: 'SAD' <br /> Model Value: 4 <br /> Domain API Value: 'Sad' |
| Angry | Angry value. Stored as 'ANG'. <br /> Database Value: 'ANG' <br /> Model Value: 5 <br /> Domain API Value: 'Angry' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
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

### DataObject

The root data object (post, marketplace product, document, etc), for which the reaction is. `Required` `Filter(multi eq)`

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SocialComment

When not null, specifies that the reaction is for the specified comment within the data object. `Filter(multi eq)`

Type: **[Comments](Communities.Social.Comments.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### User

The user, who reacted. `Required` `Filter(multi eq)`

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

[!list limit=1000 erp.entity=Communities.Social.Reactions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Communities.Social.Reactions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Communities_Social_Reactions

Domain API Entity Type: 
Communities_Social_Reaction

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Communities_Social_Reactions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Communities_Social_Reactions?$top=10>

