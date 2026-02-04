---
uid: Applications.Mail.Boxes
---
# Applications.Mail.Boxes


Represents user mailboxes.

## General
Namespace: [Applications.Mail](Applications.Mail.md)  
Repository: Applications.Mail.Boxes  
Base Table: Mail_Boxes  
API access:  ReadWrite  

## Visualization
Display Format: {SentItemsFolderName}  
Search Members: SentItemsFolderName  
Name Member: SentItemsFolderName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Mail.Boxes](Applications.Mail.Boxes.md)  
  * [Applications.Mail.BoxFolders](Applications.Mail.BoxFolders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Applications.Mail.Boxes.md#active) | boolean | True when the mail box is active for mail sinchronization, sending and receiving. `Required` `Default(true)` `Filter(eq)` 
| [EmailAddress](Applications.Mail.Boxes.md#emailaddress) | string (254) | The email address associated with this mail box. `Required` `Filter(eq)` 
| [IsDefault](Applications.Mail.Boxes.md#isdefault) | boolean | True when this is the default mailbox for the user. `Required` `Default(true)` `Filter(eq)` 
| [IsEncrypted](Applications.Mail.Boxes.md#isencrypted) | boolean | True when the mailbox messages are stored in encrypted format. `Required` `Default(false)` `Filter(eq)` 
| [ResetOnNextSync](Applications.Mail.Boxes.md#resetonnextsync) | boolean | Reset is pending: true = next sync should delete and retrieve again all messages; false = no pending reset. `Required` `Default(false)` `Filter(eq)` `ReadOnly` 
| [SendServerAddress](Applications.Mail.Boxes.md#sendserveraddress) | string (254) __nullable__ | The address of the server to use for sending mail. The same credentials as the sync server are used. When null, the mail will be sent using the default server, which is setup at the application server. 
| [SentItemsFolderName](Applications.Mail.Boxes.md#sentitemsfoldername) | string (254) __nullable__ | The name of the SentItems folder. It is left empty, EnterpriseOne won't save the sent mail in any folder (but it is still possible that the actual mail server would nevertheless save the mail in a sent items folder, independently from EnterpriseOne). 
| [SignatureHtml](Applications.Mail.Boxes.md#signaturehtml) | string (max) __nullable__ | Html text of the default signature, when creating new emails from this mailbox. When is null, a default generic signature is attached. 
| [SyncPassword](Applications.Mail.Boxes.md#syncpassword) | string (512) __nullable__ | The password to supply to the server when retrieving email. null when the connection is not setup or the server does not require user name. 
| [SyncProtocol](Applications.Mail.Boxes.md#syncprotocol) | [SyncProtocol](Applications.Mail.Boxes.md#syncprotocol) __nullable__ | Synchronization protocol, 'POP3' or 'IMAP'. null means that syncrhonization is not setup. 
| [SyncServerAddress](Applications.Mail.Boxes.md#syncserveraddress) | string (254) __nullable__ | Incoming and outgoing mail server internet address. null when synchronization is not setup. 
| [SyncUserName](Applications.Mail.Boxes.md#syncusername) | string (64) __nullable__ | User name to supply to the server, when retrieving email. null when the connection is not setup or the server does not require user name. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [OwnerUser](Applications.Mail.Boxes.md#owneruser) | [Users](Systems.Security.Users.md) | The user, who owns the mailbox. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Mail.Boxes.md#id) | guid |  
| [ObjectVersion](Applications.Mail.Boxes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Applications.Mail.Boxes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.Mail.Boxes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Applications.Mail.Boxes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Applications.Mail.Boxes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Folders | [BoxFolders](Applications.Mail.BoxFolders.md) | List of `BoxFolder`(Applications.Mail.BoxFolders.md) child objects, based on the `Applications.Mail.BoxFolder.MailBox`(Applications.Mail.BoxFolders.md#mailbox) back reference 


## Attribute Details

### Active

True when the mail box is active for mail sinchronization, sending and receiving. `Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### EmailAddress

The email address associated with this mail box. `Required` `Filter(eq)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### IsDefault

True when this is the default mailbox for the user. `Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### IsEncrypted

True when the mailbox messages are stored in encrypted format. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ResetOnNextSync

Reset is pending: true = next sync should delete and retrieve again all messages; false = no pending reset. `Required` `Default(false)` `Filter(eq)` `ReadOnly`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### SendServerAddress

The address of the server to use for sending mail. The same credentials as the sync server are used. When null, the mail will be sent using the default server, which is setup at the application server.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### SentItemsFolderName

The name of the SentItems folder. It is left empty, EnterpriseOne won't save the sent mail in any folder (but it is still possible that the actual mail server would nevertheless save the mail in a sent items folder, independently from EnterpriseOne).

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### SignatureHtml

Html text of the default signature, when creating new emails from this mailbox. When is null, a default generic signature is attached.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### SyncPassword

The password to supply to the server when retrieving email. null when the connection is not setup or the server does not require user name.

Type: **string (512) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **512**  
Show in UI: **ShownByDefault**  

### SyncProtocol

Synchronization protocol, 'POP3' or 'IMAP'. null means that syncrhonization is not setup.

Type: **[SyncProtocol](Applications.Mail.Boxes.md#syncprotocol) __nullable__**  
Category: **System**  
Allowed values for the `SyncProtocol`(Applications.Mail.Boxes.md#syncprotocol) data attribute  
Allowed Values (Applications.Mail.BoxesRepository.SyncProtocol Enum Members)  

| Value | Description |
| ---- | --- |
| Recommended | Recommended value. Stored as 'IMAP'. <br /> Database Value: 'IMAP' <br /> Model Value: 0 <br /> Domain API Value: 'Recommended' |
| POP3 | POP3 value. Stored as 'POP3'. <br /> Database Value: 'POP3' <br /> Model Value: 1 <br /> Domain API Value: 'POP3' |
| MicrosoftExchange | MicrosoftExchange value. Stored as 'MEWS'. <br /> Database Value: 'MEWS' <br /> Model Value: 2 <br /> Domain API Value: 'MicrosoftExchange' |
| NOSYNC | Synchronization is not performed. Stored as 'NSNC'. <br /> Database Value: 'NSNC' <br /> Model Value: 3 <br /> Domain API Value: 'NOSYNC' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SyncServerAddress

Incoming and outgoing mail server internet address. null when synchronization is not setup.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### SyncUserName

User name to supply to the server, when retrieving email. null when the connection is not setup or the server does not require user name.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
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

### OwnerUser

The user, who owns the mailbox. `Required` `Filter(multi eq)`

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

[!list limit=1000 erp.entity=Applications.Mail.Boxes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Mail.Boxes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Mail_Boxes

Domain API Entity Type: 
Applications_Mail_Box

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Mail_Boxes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Mail_Boxes?$top=10>

