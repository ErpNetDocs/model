---
uid: Projects.AI.Models
---
# Projects.AI.Models


Language models, which will be enriched with domain specific knowledge.

## General
Namespace: [Projects.AI](Projects.AI.md)  
Repository: Projects.AI.Models  
Base Table: Llm_Models  
Introduced In Version: 24.1.1.92  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.AI.Models](Projects.AI.Models.md)  
  * [Projects.AI.ModelQAs](Projects.AI.ModelQAs.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AutoUpdateToLatestBuild](Projects.AI.Models.md#autoupdatetolatestbuild) | boolean | Indicates whether to automatically update Conversation Build to the latest successful build. `Required` `Default(true)` 
| [BuildAssistant](Projects.AI.Models.md#buildassistant) | boolean | Specifies whether the model should produce an AI assistant. `Required` `Default(true)` `Introduced in version 24.1.5.31` 
| [IsDefault](Projects.AI.Models.md#isdefault) | boolean | Specifies whether this is the default model which will handle AI prompts. `Required` `Default(false)` `Filter(eq)` `Introduced in version 24.1.3.23` 
| [Name](Projects.AI.Models.md#name) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Multi-language name of the model. `Required` `Filter(like)` 
| [Notes](Projects.AI.Models.md#notes) | string (max) __nullable__ | Notes for this Model. 
| [SystemMessage](Projects.AI.Models.md#systemmessage) | string (max) __nullable__ | Provides system message to the chat bot. The system message sets the mood and is the primary instruction for the bot. `Introduced in version 24.1.3.7` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConversationalCompilation](Projects.AI.Models.md#conversationalcompilation) | [Compilations](Projects.AI.Compilations.md) (nullable) | The compilation which should be used when conversing with the model. Usually, updated to the latest successful compilation. null means the model cannot be used for conversations. `Filter(multi eq)` `Introduced in version 24.1.2.11` |
| [Parent](Projects.AI.Models.md#parent) | [Models](Projects.AI.Models.md) (nullable) | A model, which contains the current model. When building a parent model, it will consume all QAs from all child models. `Filter(multi eq)` |
| [Provider](Projects.AI.Models.md#provider) | [Providers](Projects.AI.Providers.md) (nullable) | The provider and base model, which should be fine-tuned with the domain specific knowledge. null means that this model cannot by compiled and can only be used as a child for another model. `Filter(multi eq)` `Introduced in version 24.1.3.3` |
| [VirtualUser](Projects.AI.Models.md#virtualuser) | [Users](Systems.Security.Users.md) (nullable) | The virtual user, which will answer in chats on behalf of the model. null means the model cannot be used in chat. Each model should have different virtual user. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.AI.Models.md#id) | guid |  
| [ObjectVersion](Projects.AI.Models.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.AI.Models.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.AI.Models.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.AI.Models.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.AI.Models.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| QAs | [ModelQAs](Projects.AI.ModelQAs.md) | List of `ModelQA`(Projects.AI.ModelQAs.md) child objects, based on the `Projects.AI.ModelQA.Model`(Projects.AI.ModelQAs.md#model) back reference 


## Attribute Details

### AutoUpdateToLatestBuild

Indicates whether to automatically update Conversation Build to the latest successful build. `Required` `Default(true)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### BuildAssistant

Specifies whether the model should produce an AI assistant. `Required` `Default(true)` `Introduced in version 24.1.5.31`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### IsDefault

Specifies whether this is the default model which will handle AI prompts. `Required` `Default(false)` `Filter(eq)` `Introduced in version 24.1.3.23`

Type: **boolean**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Name

Multi-language name of the model. `Required` `Filter(like)`

Type: **[MultilanguageString (256)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this Model.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### SystemMessage

Provides system message to the chat bot. The system message sets the mood and is the primary instruction for the bot. `Introduced in version 24.1.3.7`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
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

### ConversationalCompilation

The compilation which should be used when conversing with the model. Usually, updated to the latest successful compilation. null means the model cannot be used for conversations. `Filter(multi eq)` `Introduced in version 24.1.2.11`

Type: **[Compilations](Projects.AI.Compilations.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Parent

A model, which contains the current model. When building a parent model, it will consume all QAs from all child models. `Filter(multi eq)`

Type: **[Models](Projects.AI.Models.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Provider

The provider and base model, which should be fine-tuned with the domain specific knowledge. null means that this model cannot by compiled and can only be used as a child for another model. `Filter(multi eq)` `Introduced in version 24.1.3.3`

Type: **[Providers](Projects.AI.Providers.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### VirtualUser

The virtual user, which will answer in chats on behalf of the model. null means the model cannot be used in chat. Each model should have different virtual user. `Filter(multi eq)`

Type: **[Users](Systems.Security.Users.md) (nullable)**  
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

[!list limit=1000 erp.entity=Projects.AI.Models erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.AI.Models erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_AI_Models

Domain API Entity Type: 
Projects_AI_Model

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_AI_Models?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_AI_Models?$top=10>

