---
uid: Systems.Security.TrustedApplications
---
# Systems.Security.TrustedApplications


Application, which is trusted to access the ERP data.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.TrustedApplications  
Base Table: Sec_Trusted_Applications  
Introduced In Version: 19.1  
API access:  ReadWrite  

## Visualization
Display Format: {Name}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  3 - Track object and attribute changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Security.TrustedApplications](Systems.Security.TrustedApplications.md)  
  * [Systems.Security.TrustedApplicationAuthorizations](Systems.Security.TrustedApplicationAuthorizations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessTokens](Systems.Security.TrustedApplications.md#accesstokens) | [AccessTokens](Systems.Security.TrustedApplications.md#accesstokens) | Defines who is allowed to issue reference access tokens for this trusted application. `Required` `Default("NON")` `Filter(multi eq)` `Introduced in version 26.2.0.16` 
| [ApplicationSecretHash](Systems.Security.TrustedApplications.md#applicationsecrethash) | string (250) __nullable__ | Hash of the secret of the client application. The secret is used when the client application needs to authorize itself in front of the identity provider. `Introduced in version 20.1` 
| [ApplicationUri](Systems.Security.TrustedApplications.md#applicationuri) | string (254) | Application globally unique Uri in reverse host name format. For example: "com.manufacturer/app". `Required` `Filter(eq)` `ORD` 
| [BasicAuthenticationAllowed](Systems.Security.TrustedApplications.md#basicauthenticationallowed) | boolean | If true, this application allows login with user name and password. When a client application uses basic authentication it must provide the application uri along with user name and password. Use with caution, because basic authentication is less secure than oauth! If a user is specified in System User, the basic authentication is allowed only for this user. `Required` `Default(false)` `Filter(eq)` 
| [ClientType](Systems.Security.TrustedApplications.md#clienttype) | [ClientType](Systems.Security.TrustedApplications.md#clienttype) | Specifies the client type, according to RFC 6749, e.g. the confidentiality of the client app. P=Public (e.g. browser or native app); C=Confidential (e.g. web server app). `Required` `Default("C")` `Introduced in version 20.1` 
| [CreationTimeUtc](Systems.Security.TrustedApplications.md#creationtimeutc) | datetime | Date and time (in UTC) when the application was registered. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly` 
| [ImpersonateAsCommunity<br />UserAllowed](Systems.Security.TrustedApplications.md#impersonateascommunityuserallowed) | boolean | Allows the application to request login from external users and operate on their behalf. `Required` `Default(false)` `Filter(eq)` 
| [ImpersonateAsInternal<br />UserAllowed](Systems.Security.TrustedApplications.md#impersonateasinternaluserallowed) | boolean | Allows the application to request login from internal users and operate on their behalf. `Required` `Default(false)` `Filter(eq)` 
| [ImpersonateLoginUrl](Systems.Security.TrustedApplications.md#impersonateloginurl) | string (254) __nullable__ | The login Url used when an application is impersonated as (usually community) user; may include multiple addresses, separated by commas. 
| [ImpersonateLogoutUrl](Systems.Security.TrustedApplications.md#impersonatelogouturl) | string (254) __nullable__ | The logout Url used when an application is impersonated as (usually community) user; may include multiple addresses, separated by commas. 
| [IsEnabled](Systems.Security.TrustedApplications.md#isenabled) | boolean | Specifies whether the application is enabled for login. `Required` `Default(true)` `Filter(eq)` 
| [Name](Systems.Security.TrustedApplications.md#name) | string (254) | The multi-language name of the application. `Required` `Filter(eq;like)` `ORD` 
| [Notes](Systems.Security.TrustedApplications.md#notes) | string (max) __nullable__ | Notes for this TrustedApplication. 
| [Scope](Systems.Security.TrustedApplications.md#scope) | string (max) __nullable__ | The scope (according to RFC 6749) for which the application was trusted. The scope is an unordered list of space-delimited case-sensitive strings. Each string denotes a permission (see docs for possible values). `Introduced in version 20.1` 
| [SystemUserAllowed](Systems.Security.TrustedApplications.md#systemuserallowed) | boolean | Allows this application to logon as a service. `Required` `Default(false)` `Filter(eq)` 
| [SystemUserLoginUrl](Systems.Security.TrustedApplications.md#systemuserloginurl) | string (254) __nullable__ | The URL, which will be used by the login process, when the application logs in as a service. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [SystemUser](Systems.Security.TrustedApplications.md#systemuser) | [Users](Systems.Security.Users.md) (nullable) | The user, which will be used when the application logins as a service. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.TrustedApplications.md#id) | guid |  
| [ObjectVersion](Systems.Security.TrustedApplications.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Security.TrustedApplications.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Security.TrustedApplications.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Security.TrustedApplications.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Security.TrustedApplications.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Authorizations | [TrustedApplicationAuthorizations](Systems.Security.TrustedApplicationAuthorizations.md) | List of `TrustedApplication<br />Authorization`(Systems.Security.TrustedApplication<br />Authorizations.md) child objects, based on the `Systems.Security.TrustedApplication<br />Authorization.TrustedApplication`(Systems.Security.TrustedApplication<br />Authorizations.md#trustedapplication) back reference 


## Attribute Details

### AccessTokens

Defines who is allowed to issue reference access tokens for this trusted application. `Required` `Default("NON")` `Filter(multi eq)` `Introduced in version 26.2.0.16`

Type: **[AccessTokens](Systems.Security.TrustedApplications.md#accesstokens)**  
Category: **System**  
Allowed values for the `AccessTokens`(Systems.Security.TrustedApplications.md#accesstokens) data attribute  
Allowed Values (Systems.Security.TrustedApplicationsRepository.AccessTokens Enum Members)  

| Value | Description |
| ---- | --- |
| None | Reference tokens cannot be issued. (Default). Stored as 'NON'. <br /> Database Value: 'NON' <br /> Model Value: 0 <br /> Domain API Value: 'None' |
| AuthenticatedUsers | Any authenticated (logged-in) user may issue.. Stored as 'USR'. <br /> Database Value: 'USR' <br /> Model Value: 1 <br /> Domain API Value: 'AuthenticatedUsers' |
| AdministratorsOnly | Only administrators may issue.. Stored as 'ADM'. <br /> Database Value: 'ADM' <br /> Model Value: 2 <br /> Domain API Value: 'AdministratorsOnly' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **None**  
Show in UI: **ShownByDefault**  

### ApplicationSecretHash

Hash of the secret of the client application. The secret is used when the client application needs to authorize itself in front of the identity provider. `Introduced in version 20.1`

Type: **string (250) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **250**  
Show in UI: **ShownByDefault**  

### ApplicationUri

Application globally unique Uri in reverse host name format. For example: "com.manufacturer/app". `Required` `Filter(eq)` `ORD`

Type: **string (254)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### BasicAuthenticationAllowed

If true, this application allows login with user name and password. When a client application uses basic authentication it must provide the application uri along with user name and password. Use with caution, because basic authentication is less secure than oauth! If a user is specified in System User, the basic authentication is allowed only for this user. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ClientType

Specifies the client type, according to RFC 6749, e.g. the confidentiality of the client app. P=Public (e.g. browser or native app); C=Confidential (e.g. web server app). `Required` `Default("C")` `Introduced in version 20.1`

Type: **[ClientType](Systems.Security.TrustedApplications.md#clienttype)**  
Category: **System**  
Allowed values for the `ClientType`(Systems.Security.TrustedApplications.md#clienttype) data attribute  
Allowed Values (Systems.Security.TrustedApplicationsRepository.ClientType Enum Members)  

| Value | Description |
| ---- | --- |
| Confidential | Confidential value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 0 <br /> Domain API Value: 'Confidential' |
| Public | Public value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 1 <br /> Domain API Value: 'Public' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Confidential**  
Show in UI: **ShownByDefault**  

### CreationTimeUtc

Date and time (in UTC) when the application was registered. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### ImpersonateAsCommunityUserAllowed

Allows the application to request login from external users and operate on their behalf. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ImpersonateAsInternalUserAllowed

Allows the application to request login from internal users and operate on their behalf. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ImpersonateLoginUrl

The login Url used when an application is impersonated as (usually community) user; may include multiple addresses, separated by commas.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ImpersonateLogoutUrl

The logout Url used when an application is impersonated as (usually community) user; may include multiple addresses, separated by commas.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### IsEnabled

Specifies whether the application is enabled for login. `Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

The multi-language name of the application. `Required` `Filter(eq;like)` `ORD`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this TrustedApplication.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Scope

The scope (according to RFC 6749) for which the application was trusted. The scope is an unordered list of space-delimited case-sensitive strings. Each string denotes a permission (see docs for possible values). `Introduced in version 20.1`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### SystemUserAllowed

Allows this application to logon as a service. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### SystemUserLoginUrl

The URL, which will be used by the login process, when the application logs in as a service.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
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

### SystemUser

The user, which will be used when the application logins as a service. `Filter(multi eq)`

Type: **[Users](Systems.Security.Users.md) (nullable)**  
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

[!list limit=1000 erp.entity=Systems.Security.TrustedApplications erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.TrustedApplications erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_TrustedApplications

Domain API Entity Type: 
Systems_Security_TrustedApplication

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_TrustedApplications?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_TrustedApplications?$top=10>

