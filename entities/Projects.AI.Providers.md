---
uid: Projects.AI.Providers
---
# Projects.AI.Providers


Specifies provider and base model, on which the user models can be based.

## General
Namespace: [Projects.AI](Projects.AI.md)  
Repository: Projects.AI.Providers  
Base Table: Llm_Providers  
Introduced In Version: 24.1.3.3  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Name  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.AI.Providers](Projects.AI.Providers.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseModelName](Projects.AI.Providers.md#basemodelname) | string (64) | Provider-specific base model (for example "gpt-3.5-turbo-0613"), to which we will add domain specific knowledge.[Required] [Filter(eq)] 
| [Name](Projects.AI.Providers.md#name) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Multi-language name of the provider[Required] [Filter(like)] 
| [Notes](Projects.AI.Providers.md#notes) | string (max) __nullable__ | Notes for this Provider. 
| [ProviderApiKey](Projects.AI.Providers.md#providerapikey) | string (256) __nullable__ | The API key (provided by the model provider), which should be used to access the provider API. 
| [ProviderField](Projects.AI.Providers.md#providerfield) | [ProviderField](Projects.AI.Providers.md#providerfield) | The provider of the base model. Currently, only OpenAI is supported.[Required] [Default(&quot;OpenAI&quot;)] [Filter(eq)] 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.AI.Providers.md#id) | guid |  
| [ObjectVersion](Projects.AI.Providers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.AI.Providers.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.AI.Providers.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.AI.Providers.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.AI.Providers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BaseModelName

Provider-specific base model (for example "gpt-3.5-turbo-0613"), to which we will add domain specific knowledge.[Required] [Filter(eq)]

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Name

Multi-language name of the provider[Required] [Filter(like)]

Type: **[MultilanguageString (256)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this Provider.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ProviderApiKey

The API key (provided by the model provider), which should be used to access the provider API.

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### ProviderField

The provider of the base model. Currently, only OpenAI is supported.[Required] [Default(&quot;OpenAI&quot;)] [Filter(eq)]

Type: **[ProviderField](Projects.AI.Providers.md#providerfield)**  
Category: **System**  
Allowed values for the `ProviderField`(Projects.AI.Providers.md#providerfield) data attribute  
Allowed Values (Projects.AI.ProvidersRepository.ProviderField Enum Members)  

| Value | Description |
| ---- | --- |
| OpenAI | OpenAI value. Stored as 'OpenAI'. <br /> Database Value: 'OpenAI' <br /> Model Value: 0 <br /> Domain API Value: 'OpenAI' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **OpenAI**  
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

[!list limit=1000 erp.entity=Projects.AI.Providers erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.AI.Providers erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_AI_Providers

Domain API Entity Type: 
Projects_AI_Provider

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_AI_Providers?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_AI_Providers?$top=10>

