---
uid: Systems.Security.TrustedApplicationAuthorizations
---
# Systems.Security.TrustedApplicationAuthorizations


Authorization of a trusted application to access the data on behalf of a context user.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.TrustedApplicationAuthorizations  
Base Table: Sec_Trusted_Application_Authorizations  
Introduced In Version: 20.1  
API access:  ReadWrite  

## Visualization
Display Format: {TrustedApplication.Name}  
Search Members: TrustedApplication.Name  
Name Member: TrustedApplication.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Security.TrustedApplications](Systems.Security.TrustedApplications.md)  
Aggregate Root:  
[Systems.Security.TrustedApplications](Systems.Security.TrustedApplications.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [GrantTimeUtc](Systems.Security.TrustedApplicationAuthorizations.md#granttimeutc) | datetime | The time (in UTC) when the authorization was granted.`Required` `Default(NowUtc)` `Filter(ge;le)` 
| [IsRevoked](Systems.Security.TrustedApplicationAuthorizations.md#isrevoked) | boolean | Specifies whether the grant is explicitly revoked.`Required` `Default(false)` 
| [Notes](Systems.Security.TrustedApplicationAuthorizations.md#notes) | string (max) __nullable__ | Notes for this TrustedApplication<br />Authorization. 
| [ValidFromUtc](Systems.Security.TrustedApplicationAuthorizations.md#validfromutc) | datetime __nullable__ | The start of the validitiy of the authorization. NULL means that there is no restriction.`Filter(ge;le)` 
| [ValidUntilUtc](Systems.Security.TrustedApplicationAuthorizations.md#validuntilutc) | datetime __nullable__ | The time (in UTC) when the grant expires. NULL means that there is no time restriction.`Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ContextUser](Systems.Security.TrustedApplicationAuthorizations.md#contextuser) | [Users](Systems.Security.Users.md) | The user, whose permissions are granted to the application. |
| [GrantingUser](Systems.Security.TrustedApplicationAuthorizations.md#grantinguser) | [Users](Systems.Security.Users.md) | The user, who authorized the application. |
| [TrustedApplication](Systems.Security.TrustedApplicationAuthorizations.md#trustedapplication) | [TrustedApplications](Systems.Security.TrustedApplications.md) | The application, which is authorized. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.TrustedApplicationAuthorizations.md#id) | guid |  
| [ObjectVersion](Systems.Security.TrustedApplicationAuthorizations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Security.TrustedApplicationAuthorizations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### GrantTimeUtc

The time (in UTC) when the authorization was granted.`Required` `Default(NowUtc)` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### IsRevoked

Specifies whether the grant is explicitly revoked.`Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this TrustedApplicationAuthorization.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ValidFromUtc

The start of the validitiy of the authorization. NULL means that there is no restriction.`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidUntilUtc

The time (in UTC) when the grant expires. NULL means that there is no time restriction.`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

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

### ContextUser

The user, whose permissions are granted to the application.

Type: **[Users](Systems.Security.Users.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### GrantingUser

The user, who authorized the application.

Type: **[Users](Systems.Security.Users.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### TrustedApplication

The application, which is authorized.

Type: **[TrustedApplications](Systems.Security.TrustedApplications.md)**  
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

[!list limit=1000 erp.entity=Systems.Security.TrustedApplicationAuthorizations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.TrustedApplicationAuthorizations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_TrustedApplicationAuthorizations

Domain API Entity Type: 
Systems_Security_TrustedApplicationAuthorization

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_TrustedApplicationAuthorizations?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_TrustedApplicationAuthorizations?$top=10>

