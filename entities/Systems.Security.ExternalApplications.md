---
uid: Systems.Security.ExternalApplications
---
# Systems.Security.ExternalApplications


List of external applications. Used to run external applications.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.ExternalApplications  
Base Table: Sys_External_Applications  
API access:  ReadWrite  

## Renames

Old name: Systems.Core.ExternalApplications  
New name: Systems.Security.ExternalApplications  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Name:T}  
Search Members: Name  
Name Member: Name  
Category:  SystemData  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Security.ExternalApplications](Systems.Security.ExternalApplications.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Address](Systems.Security.ExternalApplications.md#address) | string (max) | The address (path) to the application. The address is platform-dependant.`Required` 
| [AvailableInMode](Systems.Security.ExternalApplications.md#availableinmode) | [AvailableInMode](Systems.Security.ExternalApplications.md#availableinmode) | Whether the application will be displayed to the end users when a single object is opened or when multiple objects are listed.`Required` `Default(&quot;SINGLE&quot;)` `Filter(eq)` 
| [EntityName](Systems.Security.ExternalApplications.md#entityname) | string (64) | The entity, for which the application is defined.`Required` `Filter(eq)` `ORD` 
| [ExecuteForAllObjects](Systems.Security.ExternalApplications.md#executeforallobjects) | boolean | Whether to execute the application for all selected objects at once or to execute the application for each object, one by one.`Required` `Default(true)` `Filter(eq)` 
| [IsActive](Systems.Security.ExternalApplications.md#isactive) | boolean __nullable__ | Specifies whether the external application is currently used.`Default(true)` `Filter(eq)` 
| [Name](Systems.Security.ExternalApplications.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of the external application.`Required` `Filter(eq;like)` 
| [Notes](Systems.Security.ExternalApplications.md#notes) | string (max) __nullable__ | Notes for this ExternalApplication. 
| [Platform](Systems.Security.ExternalApplications.md#platform) | [Platform](Systems.Security.ExternalApplications.md#platform) | The execution platform of the application.`Required` `Filter(eq)` 
| [RefreshAfterFinish](Systems.Security.ExternalApplications.md#refreshafterfinish) | boolean | Whether to refresh the data, displayed to the user, after the execution finishes. Not all platforms and/or applications support finish notification.`Required` `Default(true)` `Filter(eq)` 
| [SaveBeforeStart](Systems.Security.ExternalApplications.md#savebeforestart) | boolean | Whether to save the form data to the server before starting the application.`Required` `Default(true)` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Systems.Security.ExternalApplications.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the permissions for this ExternalApplication. An empty value means that all users have unlimited permissions. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.ExternalApplications.md#id) | guid |  
| [ObjectVersion](Systems.Security.ExternalApplications.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Security.ExternalApplications.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Security.ExternalApplications.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Security.ExternalApplications.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Security.ExternalApplications.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Address

The address (path) to the application. The address is platform-dependant.`Required`

Type: **string (max)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### AvailableInMode

Whether the application will be displayed to the end users when a single object is opened or when multiple objects are listed.`Required` `Default(&quot;SINGLE&quot;)` `Filter(eq)`

Type: **[AvailableInMode](Systems.Security.ExternalApplications.md#availableinmode)**  
Category: **System**  
Allowed values for the `AvailableInMode`(Systems.Security.ExternalApplications.md#availableinmode) data attribute  
Allowed Values (Systems.Security.ExternalApplicationsRepository.AvailableInMode Enum Members)  

| Value | Description |
| ---- | --- |
| SINGLE | SINGLE value. Stored as 'SINGLE'. <br /> Database Value: 'SINGLE' <br /> Model Value: 0 <br /> Domain API Value: 'SINGLE' |
| LIST | LIST value. Stored as 'LIST'. <br /> Database Value: 'LIST' <br /> Model Value: 1 <br /> Domain API Value: 'LIST' |
| ALL | ALL value. Stored as 'ALL'. <br /> Database Value: 'ALL' <br /> Model Value: 2 <br /> Domain API Value: 'ALL' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **SINGLE**  
Show in UI: **ShownByDefault**  

### EntityName

The entity, for which the application is defined.`Required` `Filter(eq)` `ORD`

Type: **string (64)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### ExecuteForAllObjects

Whether to execute the application for all selected objects at once or to execute the application for each object, one by one.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### IsActive

Specifies whether the external application is currently used.`Default(true)` `Filter(eq)`

Type: **boolean __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

The name of the external application.`Required` `Filter(eq;like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this ExternalApplication.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Platform

The execution platform of the application.`Required` `Filter(eq)`

Type: **[Platform](Systems.Security.ExternalApplications.md#platform)**  
Category: **System**  
Allowed values for the `Platform`(Systems.Security.ExternalApplications.md#platform) data attribute  
Allowed Values (Systems.Security.ExternalApplicationsRepository.Platform Enum Members)  

| Value | Description |
| ---- | --- |
| WINDOWS | WINDOWS value. Stored as 'WINDOWS'. <br /> Database Value: 'WINDOWS' <br /> Model Value: 0 <br /> Domain API Value: 'WINDOWS' |
| WEBPAGE | WEBPAGE value. Stored as 'WEBPAGE'. <br /> Database Value: 'WEBPAGE' <br /> Model Value: 1 <br /> Domain API Value: 'WEBPAGE' |
| WEBSERVICE | WEBSERVICE value. Stored as 'WEBSERVICE'. <br /> Database Value: 'WEBSERVICE' <br /> Model Value: 2 <br /> Domain API Value: 'WEBSERVICE' |
| ANDROID | ANDROID value. Stored as 'ANDROID'. <br /> Database Value: 'ANDROID' <br /> Model Value: 3 <br /> Domain API Value: 'ANDROID' |
| IOS | IOS value. Stored as 'iOS'. <br /> Database Value: 'iOS' <br /> Model Value: 4 <br /> Domain API Value: 'IOS' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### RefreshAfterFinish

Whether to refresh the data, displayed to the user, after the execution finishes. Not all platforms and/or applications support finish notification.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### SaveBeforeStart

Whether to save the form data to the server before starting the application.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
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

### AccessKey

The access key, containing the permissions for this ExternalApplication. An empty value means that all users have unlimited permissions. `Filter(multi eq)`

Type: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  


Remarks  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |

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

[!list limit=1000 erp.entity=Systems.Security.ExternalApplications erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.ExternalApplications erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_ExternalApplications

Domain API Entity Type: 
Systems_Security_ExternalApplication

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_ExternalApplications?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_ExternalApplications?$top=10>

