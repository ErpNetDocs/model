---
uid: Applications.Mail.Boxes
---
# Applications.Mail.Boxes Entity

**Namespace:** [Applications.Mail](Applications.Mail.md)  

Represents user mailboxes. Entity: Mail_Boxes

## Default Visualization
Default Display Text Format:  
_{SentItemsFolderName}_  
Default Search Members:  
_SentItemsFolderName_  
Name Data Member:  
_SentItemsFolderName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Mail.Boxes](Applications.Mail.Boxes.md)  
  * [Applications.Mail.BoxFolders](Applications.Mail.BoxFolders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Applications.Mail.Boxes.md#active) | boolean | True when the mail box is active for mail sinchronization, sending and receiving. `Required` `Default(true)` `Filter(eq)` 
| [DisplayText](Applications.Mail.Boxes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EmailAddress](Applications.Mail.Boxes.md#emailaddress) | string (254) | The email address associated with this mail box. `Required` `Filter(eq)` 
| [ExternalId](Applications.Mail.Boxes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.Mail.Boxes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Applications.Mail.Boxes.md#id) | guid |  
| [IsDefault](Applications.Mail.Boxes.md#isdefault) | boolean | True when this is the default mailbox for the user. `Required` `Default(true)` `Filter(eq)` 
| [IsEncrypted](Applications.Mail.Boxes.md#isencrypted) | boolean | True when the mailbox messages are stored in encrypted format. `Required` `Default(false)` `Filter(eq)` 
| [ObjectVersion](Applications.Mail.Boxes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
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

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Folders | [BoxFolders](Applications.Mail.BoxFolders.md) | List of `BoxFolder`(Applications.Mail.BoxFolders.md) child objects, based on the `Applications.Mail.BoxFolder.MailBox`(Applications.Mail.BoxFolders.md#mailbox) back reference 


## Attribute Details

### Active

True when the mail box is active for mail sinchronization, sending and receiving. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EmailAddress

The email address associated with this mail box. `Required` `Filter(eq)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
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

### IsDefault

True when this is the default mailbox for the user. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### IsEncrypted

True when the mailbox messages are stored in encrypted format. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ResetOnNextSync

Reset is pending: true = next sync should delete and retrieve again all messages; false = no pending reset. `Required` `Default(false)` `Filter(eq)` `ReadOnly`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### SendServerAddress

The address of the server to use for sending mail. The same credentials as the sync server are used. When null, the mail will be sent using the default server, which is setup at the application server.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### SentItemsFolderName

The name of the SentItems folder. It is left empty, EnterpriseOne won't save the sent mail in any folder (but it is still possible that the actual mail server would nevertheless save the mail in a sent items folder, independently from EnterpriseOne).

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### SignatureHtml

Html text of the default signature, when creating new emails from this mailbox. When is null, a default generic signature is attached.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### SyncPassword

The password to supply to the server when retrieving email. null when the connection is not setup or the server does not require user name.

_Type_: **string (512) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **512**  
_Show in UI_: **ShownByDefault**  

### SyncProtocol

Synchronization protocol, 'POP3' or 'IMAP'. null means that syncrhonization is not setup.

_Type_: **[SyncProtocol](Applications.Mail.Boxes.md#syncprotocol) __nullable__**  
_Category_: **System**  
Allowed values for the `SyncProtocol`(Applications.Mail.Boxes.md#syncprotocol) data attribute  
_Allowed Values (Applications.Mail.BoxesRepository.SyncProtocol Enum Members)_  

| Value | Description |
| ---- | --- |
| Recommended | Recommended value. Stored as 'IMAP'. <br /> _Database Value:_ 'IMAP' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Recommended' |
| POP3 | POP3 value. Stored as 'POP3'. <br /> _Database Value:_ 'POP3' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'POP3' |
| MicrosoftExchange | MicrosoftExchange value. Stored as 'MEWS'. <br /> _Database Value:_ 'MEWS' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'MicrosoftExchange' |
| NOSYNC | Synchronization is not performed. Stored as 'NSNC'. <br /> _Database Value:_ 'NSNC' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'NOSYNC' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### SyncServerAddress

Incoming and outgoing mail server internet address. null when synchronization is not setup.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### SyncUserName

User name to supply to the server, when retrieving email. null when the connection is not setup or the server does not require user name.

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### OwnerUser

The user, who owns the mailbox. `Required` `Filter(multi eq)`

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

