---
uid: Applications.Mail.BoxFolders
---
# Applications.Mail.BoxFolders


Contains the folders inside the mailboxes.

## General
Namespace: [Applications.Mail](Applications.Mail.md)  
Repository: Applications.Mail.BoxFolders  
Base Table: Mail_Box_Folders  
API access:  ReadWrite  

## Visualization
Display Format: {FolderName:T}  
Search Members: FolderName  
Name Member: FolderName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Mail.Boxes](Applications.Mail.Boxes.md)  
Aggregate Root:  
[Applications.Mail.Boxes](Applications.Mail.Boxes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Applications.Mail.BoxFolders.md#active) | boolean | True when the mail box folder is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.76` 
| [FolderName](Applications.Mail.BoxFolders.md#foldername) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Multi-language folder name 
| [ServerFolderID](Applications.Mail.BoxFolders.md#serverfolderid) | string (256) __nullable__ | ID of the folder on the mail server in the format of the mail server 
| [SyncState](Applications.Mail.BoxFolders.md#syncstate) | string (max) __nullable__ | The synchronization state for the folder. The format of the contents is dependant on the server type. For IMAP, this is last message Id, for Exchange - this is SyncState. 
| [SystemPurpose](Applications.Mail.BoxFolders.md#systempurpose) | [SystemPurpose](Applications.Mail.BoxFolders.md#systempurpose) __nullable__ | When not NULL means that the folder has special system designation. Designations are: Mailbox, Inbox, Drafts, Outbox, Sent, Trash. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MailBox](Applications.Mail.BoxFolders.md#mailbox) | [Boxes](Applications.Mail.Boxes.md) | The <see cref="Box"/> to which this BoxFolder belongs. `Required` `Filter(multi eq)` `ReadOnly` `Owner` |
| [ParentFolder](Applications.Mail.BoxFolders.md#parentfolder) | [BoxFolders](Applications.Mail.BoxFolders.md) (nullable) | The parent folder in the folder hierarchy. Null when the folder is a root folder. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Mail.BoxFolders.md#id) | guid |  
| [ObjectVersion](Applications.Mail.BoxFolders.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.Mail.BoxFolders.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Active

True when the mail box folder is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.76`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### FolderName

Multi-language folder name

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ServerFolderID

ID of the folder on the mail server in the format of the mail server

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### SyncState

The synchronization state for the folder. The format of the contents is dependant on the server type. For IMAP, this is last message Id, for Exchange - this is SyncState.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **CannotBeShown**  

### SystemPurpose

When not NULL means that the folder has special system designation. Designations are: Mailbox, Inbox, Drafts, Outbox, Sent, Trash.

Type: **[SystemPurpose](Applications.Mail.BoxFolders.md#systempurpose) __nullable__**  
Category: **System**  
Allowed values for the `SystemPurpose`(Applications.Mail.BoxFolders.md#systempurpose) data attribute  
Allowed Values (Applications.Mail.BoxFoldersRepository.SystemPurpose Enum Members)  

| Value | Description |
| ---- | --- |
| Mailbox | Mailbox value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 0 <br /> Domain API Value: 'Mailbox' |
| Inbox | Inbox value. Stored as 'I'. <br /> Database Value: 'I' <br /> Model Value: 1 <br /> Domain API Value: 'Inbox' |
| Drafts | Drafts value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 2 <br /> Domain API Value: 'Drafts' |
| Outbox | Outbox value. Stored as 'O'. <br /> Database Value: 'O' <br /> Model Value: 3 <br /> Domain API Value: 'Outbox' |
| Sent | Sent value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 4 <br /> Domain API Value: 'Sent' |
| Trash | Trash value. Stored as 'T'. <br /> Database Value: 'T' <br /> Model Value: 5 <br /> Domain API Value: 'Trash' |

Supported Filters: **Equals**  
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

### MailBox

The <see cref="Box"/> to which this BoxFolder belongs. `Required` `Filter(multi eq)` `ReadOnly` `Owner`

Type: **[Boxes](Applications.Mail.Boxes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ParentFolder

The parent folder in the folder hierarchy. Null when the folder is a root folder.

Type: **[BoxFolders](Applications.Mail.BoxFolders.md) (nullable)**  
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

[!list limit=1000 erp.entity=Applications.Mail.BoxFolders erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Mail.BoxFolders erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Mail_BoxFolders

Domain API Entity Type: 
Applications_Mail_BoxFolder

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Mail_BoxFolders?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Mail_BoxFolders?$top=10>

