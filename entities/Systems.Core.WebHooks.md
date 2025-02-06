---
uid: Systems.Core.WebHooks
---
# Systems.Core.WebHooks Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Webhook templates. Activated by business rules or other means. Entity: Sys_Web_Hooks (Introduced in version 22.1.5.8)
## Renamed
**New name:** [Systems.Config.WebHooks](Systems.Config.WebHooks.md)  



## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.WebHooks](Systems.Core.WebHooks.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Body](Systems.Core.WebHooks.md#body) | string (max) __nullable__ | The body of the POST request (interpolated string). 
| [Code](Systems.Core.WebHooks.md#code) | string (32) | The unique code of the WebHook. `Required` `Filter(eq;like)` `ORD` 
| [DisplayText](Systems.Core.WebHooks.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Headers](Systems.Core.WebHooks.md#headers) | string (max) __nullable__ | Optional headers for the request (interpolated string). Each header is specified on a separate line. 
| [Id](Systems.Core.WebHooks.md#id) | guid |  
| [Name](Systems.Core.WebHooks.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Webhook name (multi-language). `Required` `Filter(like)` 
| [Notes](Systems.Core.WebHooks.md#notes) | string (max) __nullable__ | Notes for this WebHook. 
| [ObjectVersion](Systems.Core.WebHooks.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RepositoryName](Systems.Core.WebHooks.md#repositoryname) | string (128) | The name of the repository for which the webhook is setup. All interpolated strings will be evaluated in the context of entities of the specified type. `Required` `Filter(eq;like)` 
| [RetryLogic](Systems.Core.WebHooks.md#retrylogic) | [RetryLogic](Systems.Core.WebHooks.md#retrylogic) | 0=Don't retry (default); 3=Retry up to 3 times. `Required` `Default("0")` 
| [URL](Systems.Core.WebHooks.md#url) | string (2000) | The destination URL, which should be called by the webhook (interpolated string). `Required` 


## Attribute Details

### Body

The body of the POST request (interpolated string).

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### Code

The unique code of the WebHook. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (32)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Headers

Optional headers for the request (interpolated string). Each header is specified on a separate line.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Name

Webhook name (multi-language). `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this WebHook.

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

### RepositoryName

The name of the repository for which the webhook is setup. All interpolated strings will be evaluated in the context of entities of the specified type. `Required` `Filter(eq;like)`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### RetryLogic

0=Don't retry (default); 3=Retry up to 3 times. `Required` `Default("0")`

_Type_: **[RetryLogic](Systems.Core.WebHooks.md#retrylogic)**  
_Category_: **System**  
Allowed values for the `RetryLogic`(Systems.Core.WebHooks.md#retrylogic) data attribute  
_Allowed Values (Systems.Core.WebHooksRepository.RetryLogic Enum Members)_  

| Value | Description |
| ---- | --- |
| NoRetry | NoRetry value. Stored as '0'. <br /> _Database Value:_ '0' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NoRetry' |
| Retry | Retry value. Stored as '3'. <br /> _Database Value:_ '3' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Retry' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **NoRetry**  
_Show in UI_: **ShownByDefault**  

### URL

The destination URL, which should be called by the webhook (interpolated string). `Required`

_Type_: **string (2000)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2000**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
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

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Systems.Core.WebHooks erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.WebHooks erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Core_WebHooks?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Core_WebHooks?$top=10>

