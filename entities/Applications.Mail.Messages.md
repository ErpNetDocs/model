---
uid: Applications.Mail.Messages
---
# Applications.Mail.Messages


Represents email messages.

## General
Namespace: [Applications.Mail](Applications.Mail.md)  
Repository: Applications.Mail.Messages  
Base Table: Mail_Messages  
API access:  ReadWrite  

## Visualization
Display Format: {CreationDateTime:d} : {Subject}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Mail.Messages](Applications.Mail.Messages.md)  
  * [Applications.Mail.MessageAttachments](Applications.Mail.MessageAttachments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Body](Applications.Mail.Messages.md#body) | string (max) __nullable__ | The body of the message 
| [CcEmailAddressList](Applications.Mail.Messages.md#ccemailaddresslist) | string (2048) __nullable__ | Semicolon-separated list of Cc email addresses`Filter(like)` 
| [CreationDateTime](Applications.Mail.Messages.md#creationdatetime) | datetime | Date and time when the message was created`Required` `Default(Now)` `Filter(ge;le)` 
| [FromEmailAddress](Applications.Mail.Messages.md#fromemailaddress) | string (512) | Sending email address`Required` `Filter(like)` 
| [IsEncrypted](Applications.Mail.Messages.md#isencrypted) | boolean | 1 when the message is stored in encrypted format`Required` `Default(false)` `Filter(eq)` 
| [IsRead](Applications.Mail.Messages.md#isread) | boolean | 1 when the message was read by the user`Required` `Default(false)` `Filter(eq)` 
| [ReceivedDateTime](Applications.Mail.Messages.md#receiveddatetime) | datetime __nullable__ | Date and time when the message was received`Filter(ge;le)` 
| [SentDateTime](Applications.Mail.Messages.md#sentdatetime) | datetime __nullable__ | Date and time when the message was sent`Filter(ge;le)` 
| [ServerMessageID](Applications.Mail.Messages.md#servermessageid) | string (256) __nullable__ | Message ID as it appears on the mail server`Filter(eq)` `ORD` 
| [Subject](Applications.Mail.Messages.md#subject) | string (1024) __nullable__ | The message subject`Filter(like)` 
| [ToEmailAddressList](Applications.Mail.Messages.md#toemailaddresslist) | string (2048) __nullable__ | Semicolon-separated list of receiving email addresses`Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MailBoxFolder](Applications.Mail.Messages.md#mailboxfolder) | [BoxFolders](Applications.Mail.BoxFolders.md) | The folder where the message belongs |
| [RelatedToParty](Applications.Mail.Messages.md#relatedtoparty) | [Parties](General.Contacts.Parties.md) (nullable) | The party id of the external participating (sender/receiver) party (customer, supplier, etc.) in this mail. NULL means that the email is still not related to any specific party |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Mail.Messages.md#id) | guid |  
| [ObjectVersion](Applications.Mail.Messages.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Applications.Mail.Messages.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.Mail.Messages.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Applications.Mail.Messages.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Applications.Mail.Messages.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Attachments | [MessageAttachments](Applications.Mail.MessageAttachments.md) | List of `MessageAttachment`(Applications.Mail.MessageAttachments.md) child objects, based on the `Applications.Mail.MessageAttachment.MailMessage`(Applications.Mail.MessageAttachments.md#mailmessage) back reference 


## Attribute Details

### Body

The body of the message

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### CcEmailAddressList

Semicolon-separated list of Cc email addresses`Filter(like)`

Type: **string (2048) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2048**  
Show in UI: **ShownByDefault**  

### CreationDateTime

Date and time when the message was created`Required` `Default(Now)` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **HiddenByDefault**  

### FromEmailAddress

Sending email address`Required` `Filter(like)`

Type: **string (512)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **512**  
Show in UI: **ShownByDefault**  

### IsEncrypted

1 when the message is stored in encrypted format`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### IsRead

1 when the message was read by the user`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ReceivedDateTime

Date and time when the message was received`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SentDateTime

Date and time when the message was sent`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ServerMessageID

Message ID as it appears on the mail server`Filter(eq)` `ORD`

Type: **string (256) __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Maximum Length: **256**  
Show in UI: **CannotBeShown**  

### Subject

The message subject`Filter(like)`

Type: **string (1024) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **1024**  
Show in UI: **ShownByDefault**  

### ToEmailAddressList

Semicolon-separated list of receiving email addresses`Filter(like)`

Type: **string (2048) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2048**  
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

### MailBoxFolder

The folder where the message belongs

Type: **[BoxFolders](Applications.Mail.BoxFolders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### RelatedToParty

The party id of the external participating (sender/receiver) party (customer, supplier, etc.) in this mail. NULL means that the email is still not related to any specific party

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
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

[!list limit=1000 erp.entity=Applications.Mail.Messages erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Mail.Messages erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Mail_Messages

Domain API Entity Type: 
Applications_Mail_Message

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Mail_Messages?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Mail_Messages?$top=10>

