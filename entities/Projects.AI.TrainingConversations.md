---
uid: Projects.AI.TrainingConversations
---
# Projects.AI.TrainingConversations


One piece of training data for fine-tuning AI models.

## General
Namespace: [Projects.AI](Projects.AI.md)  
Repository: Projects.AI.TrainingConversations  
Base Table: Llm_Training_Conversations  
Introduced In Version: 24.1.3.89  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {ModelId}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.AI.TrainingConversations](Projects.AI.TrainingConversations.md)  
  * [Projects.AI.TrainingConversationMessages](Projects.AI.TrainingConversationMessages.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](Projects.AI.TrainingConversations.md#creationtimeutc) | datetime | The date and time (UTC) when the conversation was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ReadOnly` 
| [LastUpdateTimeUtc](Projects.AI.TrainingConversations.md#lastupdatetimeutc) | datetime | Time when the conversation or any messages in it were created or last modified. Can be used to track changes to the whole aggregate. `Required` `Filter(ge;le)` `ORD` `ReadOnly` 
| [Notes](Projects.AI.TrainingConversations.md#notes) | string (max) __nullable__ | Notes for this training conversation. 
| [Origin](Projects.AI.TrainingConversations.md#origin) | [Origin](Projects.AI.TrainingConversations.md#origin) | Denotes how (based on what other object) was the conversation initially created. Possible values - User-entered, Chat, Calendar, etc. `Required` `Default("USR")` `Filter(multi eq)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Model](Projects.AI.TrainingConversations.md#model) | [Models](Projects.AI.Models.md) | The model, which is being trained. `Required` `Filter(multi eq)` |
| [OriginDataObject](Projects.AI.TrainingConversations.md#origindataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable) | The object, whose data was used to initially create the conversation. null means the object is unknown or not a data object. `Filter(multi eq)` `ReadOnly` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.AI.TrainingConversations.md#id) | guid |  
| [ObjectVersion](Projects.AI.TrainingConversations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.AI.TrainingConversations.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.AI.TrainingConversations.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.AI.TrainingConversations.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.AI.TrainingConversations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Messages | [TrainingConversationMessages](Projects.AI.TrainingConversationMessages.md) | List of `TrainingConversation<br />Message`(Projects.AI.TrainingConversation<br />Messages.md) child objects, based on the `Projects.AI.TrainingConversation<br />Message.TrainingConversation`(Projects.AI.TrainingConversation<br />Messages.md#trainingconversation) back reference 


## Attribute Details

### CreationTimeUtc

The date and time (UTC) when the conversation was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### LastUpdateTimeUtc

Time when the conversation or any messages in it were created or last modified. Can be used to track changes to the whole aggregate. `Required` `Filter(ge;le)` `ORD` `ReadOnly`

Type: **datetime**  
Indexed: **True**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this training conversation.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Origin

Denotes how (based on what other object) was the conversation initially created. Possible values - User-entered, Chat, Calendar, etc. `Required` `Default("USR")` `Filter(multi eq)` `ReadOnly`

Type: **[Origin](Projects.AI.TrainingConversations.md#origin)**  
Category: **System**  
Allowed values for the `Origin`(Projects.AI.TrainingConversations.md#origin) data attribute  
Allowed Values (Projects.AI.TrainingConversationsRepository.Origin Enum Members)  

| Value | Description |
| ---- | --- |
| UserEntered | User-entered. Stored as 'USR'. <br /> Database Value: 'USR' <br /> Model Value: 0 <br /> Domain API Value: 'UserEntered' |
| Chat | Chat. Stored as 'CHT'. <br /> Database Value: 'CHT' <br /> Model Value: 1 <br /> Domain API Value: 'Chat' |
| Calendar | Calendar. Stored as 'CAL'. <br /> Database Value: 'CAL' <br /> Model Value: 2 <br /> Domain API Value: 'Calendar' |
| Case | Case. Stored as 'CAS'. <br /> Database Value: 'CAS' <br /> Model Value: 3 <br /> Domain API Value: 'Case' |
| ToDo | To Do. Stored as 'TOD'. <br /> Database Value: 'TOD' <br /> Model Value: 4 <br /> Domain API Value: 'ToDo' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **UserEntered**  
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

### Model

The model, which is being trained. `Required` `Filter(multi eq)`

Type: **[Models](Projects.AI.Models.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OriginDataObject

The object, whose data was used to initially create the conversation. null means the object is unknown or not a data object. `Filter(multi eq)` `ReadOnly`

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable)**  
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

[!list limit=1000 erp.entity=Projects.AI.TrainingConversations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.AI.TrainingConversations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_AI_TrainingConversations

Domain API Entity Type: 
Projects_AI_TrainingConversation

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_AI_TrainingConversations?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_AI_TrainingConversations?$top=10>

