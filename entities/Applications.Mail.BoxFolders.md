---
uid: Applications.Mail.BoxFolders
---
# Applications.Mail.BoxFolders Entity

**Namespace:** [Applications.Mail](Applications.Mail.md)  

Contains the folders inside the mailboxes. Entity: Mail_Box_Folders

## Default Visualization
Default Display Text Format:  
_{FolderName:T}_  
Default Search Members:  
_FolderName_  
Name Data Member:  
_FolderName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _1 - Track last changes only_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Applications.Mail.BoxFolders.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FolderName](Applications.Mail.BoxFolders.md#foldername) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Multi-language folder name. `Required` `Filter(eq;like)` 
| [Id](Applications.Mail.BoxFolders.md#id) | guid |  
| [ObjectVersion](Applications.Mail.BoxFolders.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ServerFolderID](Applications.Mail.BoxFolders.md#serverfolderid) | string (256) __nullable__ | ID of the folder on the mail server in the format of the mail server. `Filter(eq)` 
| [SyncState](Applications.Mail.BoxFolders.md#syncstate) | string (max) __nullable__ | The synchronization state for the folder. The format of the contents is dependant on the server type. For IMAP, this is last message Id, for Exchange - this is SyncState. 
| [SystemPurpose](Applications.Mail.BoxFolders.md#systempurpose) | [SystemPurpose](Applications.Mail.BoxFolders.md#systempurpose) __nullable__ | When not null means that the folder has special system designation. Designations are: M=Mailbox(root folder), I=Inbox, D=Drafts, O=Outbox, S=Sent, T=Trash. `Filter(eq)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MailBox](Applications.Mail.BoxFolders.md#mailbox) | [Boxes](Applications.Mail.Boxes.md) | The <see cref="Box"/> to which this BoxFolder belongs. `Required` `Filter(multi eq)` `ReadOnly` `Owner` |
| [ParentFolder](Applications.Mail.BoxFolders.md#parentfolder) | [BoxFolders](Applications.Mail.BoxFolders.md) (nullable) | The parent folder in the folder hierarchy. Null when the folder is a root folder. `Filter(multi eq)` |


## Attribute Details

### Active

True when the mail box folder is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.76`

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

### FolderName

Multi-language folder name. `Required` `Filter(eq;like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ServerFolderID

ID of the folder on the mail server in the format of the mail server. `Filter(eq)`

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### SyncState

The synchronization state for the folder. The format of the contents is dependant on the server type. For IMAP, this is last message Id, for Exchange - this is SyncState.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **CannotBeShown**  

### SystemPurpose

When not null means that the folder has special system designation. Designations are: M=Mailbox(root folder), I=Inbox, D=Drafts, O=Outbox, S=Sent, T=Trash. `Filter(eq)` `ReadOnly`

_Type_: **[SystemPurpose](Applications.Mail.BoxFolders.md#systempurpose) __nullable__**  
_Category_: **System**  
Allowed values for the `SystemPurpose`(Applications.Mail.BoxFolders.md#systempurpose) data attribute  
_Allowed Values (Applications.Mail.BoxFoldersRepository.SystemPurpose Enum Members)_  

| Value | Description |
| ---- | --- |
| Mailbox | Mailbox value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Mailbox' |
| Inbox | Inbox value. Stored as 'I'. <br /> _Database Value:_ 'I' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Inbox' |
| Drafts | Drafts value. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Drafts' |
| Outbox | Outbox value. Stored as 'O'. <br /> _Database Value:_ 'O' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Outbox' |
| Sent | Sent value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Sent' |
| Trash | Trash value. Stored as 'T'. <br /> _Database Value:_ 'T' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Trash' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### MailBox

The <see cref="Box"/> to which this BoxFolder belongs. `Required` `Filter(multi eq)` `ReadOnly` `Owner`

_Type_: **[Boxes](Applications.Mail.Boxes.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ParentFolder

The parent folder in the folder hierarchy. Null when the folder is a root folder. `Filter(multi eq)`

_Type_: **[BoxFolders](Applications.Mail.BoxFolders.md) (nullable)**  
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

