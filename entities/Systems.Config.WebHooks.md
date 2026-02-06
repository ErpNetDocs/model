---
uid: Systems.Config.WebHooks
---
# Systems.Config.WebHooks


Webhook templates. Activated by business rules or other means.

## General
Namespace: [Systems.Config](Systems.Config.md)  
Repository: Systems.Config.WebHooks  
Base Table: Sys_Web_Hooks  
Introduced In Version: 22.1.5.8  
API access:  ReadWrite  

## Renames

Old name: Systems.Core.WebHooks  
New name: Systems.Config.WebHooks  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Config.WebHooks](Systems.Config.WebHooks.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Body](Systems.Config.WebHooks.md#body) | string (max) __nullable__ | The body of the POST request (interpolated string). 
| [Code](Systems.Config.WebHooks.md#code) | string (32) | The unique code of the WebHook. `Required` `Filter(eq;like)` `ORD` 
| [Headers](Systems.Config.WebHooks.md#headers) | string (max) __nullable__ | Optional headers for the request (interpolated string). Each header is specified on a separate line. 
| [Name](Systems.Config.WebHooks.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Webhook name (multi-language).[Required] [Filter(like)] 
| [Notes](Systems.Config.WebHooks.md#notes) | string (max) __nullable__ | Notes for this WebHook. 
| [RepositoryName](Systems.Config.WebHooks.md#repositoryname) | string (128) | The name of the repository for which the webhook is setup. All interpolated strings will be evaluated in the context of entities of the specified type.[Required] [Filter(eq;like)] 
| [RetryLogic](Systems.Config.WebHooks.md#retrylogic) | [RetryLogic](Systems.Config.WebHooks.md#retrylogic) | 0=Don't retry (default); 3=Retry up to 3 times[Required] [Default(&quot;0&quot;)] 
| [URL](Systems.Config.WebHooks.md#url) | string (2000) | The destination URL, which should be called by the webhook (interpolated string).[Required] 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Config.WebHooks.md#id) | guid |  
| [ObjectVersion](Systems.Config.WebHooks.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Config.WebHooks.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Config.WebHooks.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Config.WebHooks.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Config.WebHooks.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Body

The body of the POST request (interpolated string).

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Code

The unique code of the WebHook. `Required` `Filter(eq;like)` `ORD`

Type: **string (32)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### Headers

Optional headers for the request (interpolated string). Each header is specified on a separate line.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Name

Webhook name (multi-language).[Required] [Filter(like)]

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this WebHook.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### RepositoryName

The name of the repository for which the webhook is setup. All interpolated strings will be evaluated in the context of entities of the specified type.[Required] [Filter(eq;like)]

Type: **string (128)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### RetryLogic

0=Don't retry (default); 3=Retry up to 3 times[Required] [Default(&quot;0&quot;)]

Type: **[RetryLogic](Systems.Config.WebHooks.md#retrylogic)**  
Category: **System**  
Allowed values for the `RetryLogic`(Systems.Config.WebHooks.md#retrylogic) data attribute  
Allowed Values (Systems.Config.WebHooksRepository.RetryLogic Enum Members)  

| Value | Description |
| ---- | --- |
| NoRetry | NoRetry value. Stored as '0'. <br /> Database Value: '0' <br /> Model Value: 0 <br /> Domain API Value: 'NoRetry' |
| Retry | Retry value. Stored as '3'. <br /> Database Value: '3' <br /> Model Value: 1 <br /> Domain API Value: 'Retry' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **NoRetry**  
Show in UI: **ShownByDefault**  

### URL

The destination URL, which should be called by the webhook (interpolated string).[Required]

Type: **string (2000)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2000**  
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

[!list limit=1000 erp.entity=Systems.Config.WebHooks erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Config.WebHooks erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Config_WebHooks

Domain API Entity Type: 
Systems_Config_WebHook

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Config_WebHooks?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Config_WebHooks?$top=10>

