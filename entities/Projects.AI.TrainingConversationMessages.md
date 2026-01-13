---
uid: Projects.AI.TrainingConversationMessages
---
# Projects.AI.TrainingConversationMessages Entity

**Namespace:** [Projects.AI](Projects.AI.md)  

Message in a training conversation. Entity: Llm_Training_Conversation_Messages (Introduced in version 24.1.3.89)

## Default Visualization
Default Display Text Format:  
_{ParticipantName}_  
Default Search Members:  
_ParticipantName_  
Name Data Member:  
_ParticipantName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.AI.TrainingConversations](Projects.AI.TrainingConversations.md)  
Aggregate Root:  
[Projects.AI.TrainingConversations](Projects.AI.TrainingConversations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Contents](Projects.AI.TrainingConversationMessages.md#contents) | string (max) | Contents of the message. Can be formatted using MarkDown. `Required` 
| [DisplayText](Projects.AI.TrainingConversationMessages.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Projects.AI.TrainingConversationMessages.md#id) | guid |  
| [MessageNo](Projects.AI.TrainingConversationMessages.md#messageno) | int32 | Message number within the conversation. `Required` `Filter(eq)` 
| [MessageTimeUtc](Projects.AI.TrainingConversationMessages.md#messagetimeutc) | datetime | Date and time, when the message was originally typed (or created). `Required` `Default(NowUtc)` `Filter(ge;le)` 
| [ObjectVersion](Projects.AI.TrainingConversationMessages.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ParticipantName](Projects.AI.TrainingConversationMessages.md#participantname) | string (64) __nullable__ | Name of the participant, who created the message. Name is optional, but gives more context to the message. 
| [ParticipantRole](Projects.AI.TrainingConversationMessages.md#participantrole) | [ParticipantRole](Projects.AI.TrainingConversationMessages.md#participantrole) | Role of the participant. Can be System - for system mood messages; User - for user messages; Assistant - for AI-created message. `Required` `Default("U")` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [TrainingConversation](Projects.AI.TrainingConversationMessages.md#trainingconversation) | [TrainingConversations](Projects.AI.TrainingConversations.md) | The <see cref="Training<br />Conversation"/> to which this TrainingConversation<br />Message belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### Contents

Contents of the message. Can be formatted using MarkDown. `Required`

_Type_: **string (max)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
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

### MessageNo

Message number within the conversation. `Required` `Filter(eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.TrainingConversation.Messages.Select( c => c.MessageNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.TrainingConversation.Messages.Select( c => c.MessageNo).DefaultIfEmpty( 0).Max( ) + 1)`
### MessageTimeUtc

Date and time, when the message was originally typed (or created). `Required` `Default(NowUtc)` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ParticipantName

Name of the participant, who created the message. Name is optional, but gives more context to the message.

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### ParticipantRole

Role of the participant. Can be System - for system mood messages; User - for user messages; Assistant - for AI-created message. `Required` `Default("U")` `Filter(multi eq)`

_Type_: **[ParticipantRole](Projects.AI.TrainingConversationMessages.md#participantrole)**  
_Category_: **System**  
Allowed values for the `ParticipantRole`(Projects.AI.TrainingConversationMessages.md#participantrole) data attribute  
_Allowed Values (Projects.AI.TrainingConversationMessagesRepository.ParticipantRole Enum Members)_  

| Value | Description |
| ---- | --- |
| System | System. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'System' |
| User | User. Stored as 'U'. <br /> _Database Value:_ 'U' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'User' |
| Assistant | Assistant. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Assistant' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **User**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### TrainingConversation

The <see cref="TrainingConversation"/> to which this TrainingConversationMessage belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[TrainingConversations](Projects.AI.TrainingConversations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

