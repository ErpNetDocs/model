---
uid: Communities.Social.Comments
---
# Communities.Social.Comments


User comment to any object in the system.

## General
Namespace: [Communities.Social](Communities.Social.md)  
Repository: Communities.Social.Comments  
Base Table: Cmm_Social_Comments  
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
* [Communities.Social.Comments](Communities.Social.Comments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CommentText](Communities.Social.Comments.md#commenttext) | string (max) | The comment contents in clear text.[Required] 
| [CreationTimeUtc](Communities.Social.Comments.md#creationtimeutc) | datetime | The exact server time (in UTC), when the comment was created.[Required] [Filter(ge;le)] [ORD] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Communities.Social.Comments.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The root data object (post, marketplace product, document, etc), for which the comment is made. |
| [ReplyToComment](Communities.Social.Comments.md#replytocomment) | [Comments](Communities.Social.Comments.md) (nullable) | When not null, means that the comment is a reply to the specified comment. The comment and the reply should be for the same data object. |
| [User](Communities.Social.Comments.md#user) | [Users](Systems.Security.Users.md) | The user, who made the comment. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Communities.Social.Comments.md#id) | guid |  
| [ObjectVersion](Communities.Social.Comments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Communities.Social.Comments.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Communities.Social.Comments.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Communities.Social.Comments.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Communities.Social.Comments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CommentText

The comment contents in clear text.[Required]

Type: **string (max)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### CreationTimeUtc

The exact server time (in UTC), when the comment was created.[Required] [Filter(ge;le)] [ORD]

Type: **datetime**  
Indexed: **True**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
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

The root data object (post, marketplace product, document, etc), for which the comment is made.

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ReplyToComment

When not null, means that the comment is a reply to the specified comment. The comment and the reply should be for the same data object.

Type: **[Comments](Communities.Social.Comments.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### User

The user, who made the comment.

Type: **[Users](Systems.Security.Users.md)**  
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

[!list limit=1000 erp.entity=Communities.Social.Comments erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Communities.Social.Comments erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Communities_Social_Comments

Domain API Entity Type: 
Communities_Social_Comment

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Communities_Social_Comments?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Communities_Social_Comments?$top=10>

