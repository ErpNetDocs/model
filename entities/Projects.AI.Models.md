---
uid: Projects.AI.Models
---
# Projects.AI.Models Entity

**Namespace:** [Projects.AI](Projects.AI.md)  

Language models, which will be enriched with domain specific knowledge. Entity: Llm_Models (Introduced in version 24.1.1.92)

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.AI.Models](Projects.AI.Models.md)  
  * [Projects.AI.ModelQAs](Projects.AI.ModelQAs.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Projects.AI.Models.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [AutoUpdateToLatestBuild](Projects.AI.Models.md#autoupdatetolatestbuild) | boolean | Indicates whether to automatically update Conversation Build to the latest successful build. `Required` `Default(true)` 
| [BuildAssistant](Projects.AI.Models.md#buildassistant) | boolean | Specifies whether the model should produce an AI assistant. `Required` `Default(true)` `Introduced in version 24.1.5.31` 
| [DisplayText](Projects.AI.Models.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Projects.AI.Models.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.AI.Models.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Projects.AI.Models.md#id) | guid |  
| [IsDefault](Projects.AI.Models.md#isdefault) | boolean | Specifies whether this is the default model which will handle AI prompts. `Required` `Default(false)` `Filter(eq)` `Introduced in version 24.1.3.23` 
| [Name](Projects.AI.Models.md#name) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Multi-language name of the model. `Required` `Filter(like)` 
| [Notes](Projects.AI.Models.md#notes) | string (max) __nullable__ | Notes for this Model. 
| [ObjectVersion](Projects.AI.Models.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [SystemMessage](Projects.AI.Models.md#systemmessage) | string (max) __nullable__ | Provides system message to the chat bot. The system message sets the mood and is the primary instruction for the bot. `Introduced in version 24.1.3.7` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConversationalCompilation](Projects.AI.Models.md#conversationalcompilation) | [Compilations](Projects.AI.Compilations.md) (nullable) | The compilation which should be used when conversing with the model. Usually, updated to the latest successful compilation. null means the model cannot be used for conversations. `Filter(multi eq)` `Introduced in version 24.1.2.11` |
| [Parent](Projects.AI.Models.md#parent) | [Models](Projects.AI.Models.md) (nullable) | A model, which contains the current model. When building a parent model, it will consume all QAs from all child models. `Filter(multi eq)` |
| [Provider](Projects.AI.Models.md#provider) | [Providers](Projects.AI.Providers.md) (nullable) | The provider and base model, which should be fine-tuned with the domain specific knowledge. null means that this model cannot by compiled and can only be used as a child for another model. `Filter(multi eq)` `Introduced in version 24.1.3.3` |
| [VirtualUser](Projects.AI.Models.md#virtualuser) | [Users](Systems.Security.Users.md) (nullable) | The virtual user, which will answer in chats on behalf of the model. null means the model cannot be used in chat. Each model should have different virtual user. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| QAs | [ModelQAs](Projects.AI.ModelQAs.md) | List of `ModelQA`(Projects.AI.ModelQAs.md) child objects, based on the `Projects.AI.ModelQA.Model`(Projects.AI.ModelQAs.md#model) back reference 


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### AutoUpdateToLatestBuild

Indicates whether to automatically update Conversation Build to the latest successful build. `Required` `Default(true)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### BuildAssistant

Specifies whether the model should produce an AI assistant. `Required` `Default(true)` `Introduced in version 24.1.5.31`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
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

Specifies whether this is the default model which will handle AI prompts. `Required` `Default(false)` `Filter(eq)` `Introduced in version 24.1.3.23`

_Type_: **boolean**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Name

Multi-language name of the model. `Required` `Filter(like)`

_Type_: **[MultilanguageString (256)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Model.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### SystemMessage

Provides system message to the chat bot. The system message sets the mood and is the primary instruction for the bot. `Introduced in version 24.1.3.7`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### ConversationalCompilation

The compilation which should be used when conversing with the model. Usually, updated to the latest successful compilation. null means the model cannot be used for conversations. `Filter(multi eq)` `Introduced in version 24.1.2.11`

_Type_: **[Compilations](Projects.AI.Compilations.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Parent

A model, which contains the current model. When building a parent model, it will consume all QAs from all child models. `Filter(multi eq)`

_Type_: **[Models](Projects.AI.Models.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Provider

The provider and base model, which should be fine-tuned with the domain specific knowledge. null means that this model cannot by compiled and can only be used as a child for another model. `Filter(multi eq)` `Introduced in version 24.1.3.3`

_Type_: **[Providers](Projects.AI.Providers.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### VirtualUser

The virtual user, which will answer in chats on behalf of the model. null means the model cannot be used in chat. Each model should have different virtual user. `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
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

