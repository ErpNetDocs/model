---
uid: General.Contacts.PartyCommunications
---
# General.Contacts.PartyCommunications


A “Communication timeline” centralizes emails, chats and internal notes with a specific Party.

## General
Namespace: [General.Contacts](General.Contacts.md)  
Repository: General.Contacts.PartyCommunications  
Base Table: Cm_Party_Communications  
Introduced In Version: 26.2.1.50  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {PartyId}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.Contacts.PartyCommunications](General.Contacts.PartyCommunications.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Channel](General.Contacts.PartyCommunications.md#channel) | [Channel](General.Contacts.PartyCommunications.md#channel) | Main channel of communication.`Required` `Default(&quot;EML&quot;)` `Filter(eq)` 
| [CommunicationFrom](General.Contacts.PartyCommunications.md#communicationfrom) | string (254) | Who the message is from (email/phone/identifier).`Required` `Filter(eq;like)` 
| [CommunicationTo](General.Contacts.PartyCommunications.md#communicationto) | string (254) | Who the message is addressed to (main recipient)`Required` `Filter(eq;like)` 
| [ConversationId](General.Contacts.PartyCommunications.md#conversationid) | guid __nullable__ | Conversation identifier to group messages into a single thread. `Filter(multi eq)` 
| [Direction](General.Contacts.PartyCommunications.md#direction) | [Direction](General.Contacts.PartyCommunications.md#direction) | Direction: received or sent.`Required` `Default(&quot;I&quot;)` `Filter(eq)` 
| [Message](General.Contacts.PartyCommunications.md#message) | string (max) __nullable__ | Full content of the message.`Filter(like)` 
| [SubChannel](General.Contacts.PartyCommunications.md#subchannel) | [SubChannel](General.Contacts.PartyCommunications.md#subchannel) | Specific application source.`Required` `Default(&quot;OUT&quot;)` `Filter(eq)` 
| [Subject](General.Contacts.PartyCommunications.md#subject) | string (254) __nullable__ | Short title of the message.`Filter(like)` 
| [TimeLastUpdate](General.Contacts.PartyCommunications.md#timelastupdate) | datetime | When it was last updated/synced in ERP.`Required` `Filter(eq;ge;le)` 
| [TimeOccurredAt](General.Contacts.PartyCommunications.md#timeoccurredat) | datetime | When the message happened.`Required` `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](General.Contacts.PartyCommunications.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | Which object this communication is about. |
| [ParentCommunicationLog](General.Contacts.PartyCommunications.md#parentcommunicationlog) | [PartyCommunications](General.Contacts.PartyCommunications.md) (nullable) | Link to a previous communication (for reply/forward or sequence). |
| [Party](General.Contacts.PartyCommunications.md#party) | [Parties](General.Contacts.Parties.md) | Which partner this communication is about. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Contacts.PartyCommunications.md#id) | guid |  
| [ObjectVersion](General.Contacts.PartyCommunications.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](General.Contacts.PartyCommunications.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Contacts.PartyCommunications.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](General.Contacts.PartyCommunications.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](General.Contacts.PartyCommunications.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Channel

Main channel of communication.`Required` `Default(&quot;EML&quot;)` `Filter(eq)`

Type: **[Channel](General.Contacts.PartyCommunications.md#channel)**  
Category: **System**  
Allowed values for the `Channel`(General.Contacts.PartyCommunications.md#channel) data attribute  
Allowed Values (General.Contacts.PartyCommunicationsRepository.Channel Enum Members)  

| Value | Description |
| ---- | --- |
| Email | Email value. Stored as 'EML'. <br /> Database Value: 'EML' <br /> Model Value: 0 <br /> Domain API Value: 'Email' |
| IM | IM value. Stored as 'MSG'. <br /> Database Value: 'MSG' <br /> Model Value: 1 <br /> Domain API Value: 'IM' |
| Note | Note value. Stored as 'NOT'. <br /> Database Value: 'NOT' <br /> Model Value: 2 <br /> Domain API Value: 'Note' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Email**  
Show in UI: **ShownByDefault**  

### CommunicationFrom

Who the message is from (email/phone/identifier).`Required` `Filter(eq;like)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### CommunicationTo

Who the message is addressed to (main recipient)`Required` `Filter(eq;like)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ConversationId

Conversation identifier to group messages into a single thread. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Direction

Direction: received or sent.`Required` `Default(&quot;I&quot;)` `Filter(eq)`

Type: **[Direction](General.Contacts.PartyCommunications.md#direction)**  
Category: **System**  
Allowed values for the `Direction`(General.Contacts.PartyCommunications.md#direction) data attribute  
Allowed Values (General.Contacts.PartyCommunicationsRepository.Direction Enum Members)  

| Value | Description |
| ---- | --- |
| Inbound | Inbound value. Stored as 'I'. <br /> Database Value: 'I' <br /> Model Value: 0 <br /> Domain API Value: 'Inbound' |
| Outbound | Outbound value. Stored as 'O'. <br /> Database Value: 'O' <br /> Model Value: 1 <br /> Domain API Value: 'Outbound' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Inbound**  
Show in UI: **ShownByDefault**  

### Message

Full content of the message.`Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### SubChannel

Specific application source.`Required` `Default(&quot;OUT&quot;)` `Filter(eq)`

Type: **[SubChannel](General.Contacts.PartyCommunications.md#subchannel)**  
Category: **System**  
Allowed values for the `SubChannel`(General.Contacts.PartyCommunications.md#subchannel) data attribute  
Allowed Values (General.Contacts.PartyCommunicationsRepository.SubChannel Enum Members)  

| Value | Description |
| ---- | --- |
| Outlook | Outlook value. Stored as 'OUT'. <br /> Database Value: 'OUT' <br /> Model Value: 0 <br /> Domain API Value: 'Outlook' |
| WhatsApp | WhatsApp value. Stored as 'WHA'. <br /> Database Value: 'WHA' <br /> Model Value: 1 <br /> Domain API Value: 'WhatsApp' |
| Viber | Viber value. Stored as 'VBR'. <br /> Database Value: 'VBR' <br /> Model Value: 2 <br /> Domain API Value: 'Viber' |
| Internal | Internal value. Stored as 'INT'. <br /> Database Value: 'INT' <br /> Model Value: 3 <br /> Domain API Value: 'Internal' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Outlook**  
Show in UI: **ShownByDefault**  

### Subject

Short title of the message.`Filter(like)`

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### TimeLastUpdate

When it was last updated/synced in ERP.`Required` `Filter(eq;ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TimeOccurredAt

When the message happened.`Required` `Filter(eq;ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
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

Which object this communication is about.

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ParentCommunicationLog

Link to a previous communication (for reply/forward or sequence).

Type: **[PartyCommunications](General.Contacts.PartyCommunications.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Party

Which partner this communication is about.

Type: **[Parties](General.Contacts.Parties.md)**  
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

[!list limit=1000 erp.entity=General.Contacts.PartyCommunications erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Contacts.PartyCommunications erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Contacts_PartyCommunications

Domain API Entity Type: 
General_Contacts_PartyCommunication

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Contacts_PartyCommunications?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Contacts_PartyCommunications?$top=10>

