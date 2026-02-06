---
uid: Projects.AI.TrainingConversationMessages
---
# Projects.AI.TrainingConversationMessages


Message in a training conversation.

## General
Namespace: [Projects.AI](Projects.AI.md)  
Repository: Projects.AI.TrainingConversationMessages  
Base Table: Llm_Training_Conversation_Messages  
Introduced In Version: 24.1.3.89  
API access:  ReadWrite  

## Visualization
Display Format: {ParticipantName}  
Search Members: ParticipantName  
Name Member: ParticipantName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.AI.TrainingConversations](Projects.AI.TrainingConversations.md)  
Aggregate Root:  
[Projects.AI.TrainingConversations](Projects.AI.TrainingConversations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Contents](Projects.AI.TrainingConversationMessages.md#contents) | string (max) | Contents of the message. Can be formatted using MarkDown. 
| [MessageNo](Projects.AI.TrainingConversationMessages.md#messageno) | int32 | Message number within the conversation. 
| [MessageTimeUtc](Projects.AI.TrainingConversationMessages.md#messagetimeutc) | datetime | Date and time, when the message was originally typed (or created). 
| [ParticipantName](Projects.AI.TrainingConversationMessages.md#participantname) | string (64) __nullable__ | Name of the participant, who created the message. Name is optional, but gives more context to the message. 
| [ParticipantRole](Projects.AI.TrainingConversationMessages.md#participantrole) | [ParticipantRole](Projects.AI.TrainingConversationMessages.md#participantrole) | Role of the participant. Can be System - for system mood messages; User - for user messages; Assistant - for AI-created message. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [TrainingConversation](Projects.AI.TrainingConversationMessages.md#trainingconversation) | [TrainingConversations](Projects.AI.TrainingConversations.md) | The <see cref="Training<br />Conversation"/> to which this TrainingConversation<br />Message belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.AI.TrainingConversationMessages.md#id) | guid |  
| [ObjectVersion](Projects.AI.TrainingConversationMessages.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Projects.AI.TrainingConversationMessages.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Contents

Contents of the message. Can be formatted using MarkDown.

Type: **string (max)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### MessageNo

Message number within the conversation.

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.TrainingConversation.Messages.Select( c => c.MessageNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.TrainingConversation.Messages.Select( c => c.MessageNo).DefaultIfEmpty( 0).Max( ) + 1)`
### MessageTimeUtc

Date and time, when the message was originally typed (or created).

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### ParticipantName

Name of the participant, who created the message. Name is optional, but gives more context to the message.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### ParticipantRole

Role of the participant. Can be System - for system mood messages; User - for user messages; Assistant - for AI-created message.

Type: **[ParticipantRole](Projects.AI.TrainingConversationMessages.md#participantrole)**  
Category: **System**  
Allowed values for the `ParticipantRole`(Projects.AI.TrainingConversationMessages.md#participantrole) data attribute  
Allowed Values (Projects.AI.TrainingConversationMessagesRepository.ParticipantRole Enum Members)  

| Value | Description |
| ---- | --- |
| System | System. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 0 <br /> Domain API Value: 'System' |
| User | User. Stored as 'U'. <br /> Database Value: 'U' <br /> Model Value: 1 <br /> Domain API Value: 'User' |
| Assistant | Assistant. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 2 <br /> Domain API Value: 'Assistant' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **User**  
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

### TrainingConversation

The <see cref="TrainingConversation"/> to which this TrainingConversationMessage belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[TrainingConversations](Projects.AI.TrainingConversations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Projects.AI.TrainingConversationMessages erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.AI.TrainingConversationMessages erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_AI_TrainingConversationMessages

Domain API Entity Type: 
Projects_AI_TrainingConversationMessage

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_AI_TrainingConversationMessages?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_AI_TrainingConversationMessages?$top=10>

