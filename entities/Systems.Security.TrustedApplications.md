---
uid: Systems.Security.TrustedApplications
---
# Systems.Security.TrustedApplications Entity

**Namespace:** [Systems.Security](Systems.Security.md)  

Application, which is trusted to access the ERP data. Entity: Sec_Trusted_Applications (Introduced in version 19.1)

## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _3 - Track object and attribute changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Systems.Security.TrustedApplications.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Systems.Security.TrustedApplications.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Security.TrustedApplications.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Security.TrustedApplications.md#id) | guid |  
| [ImpersonateAsCommunity<br />UserAllowed](Systems.Security.TrustedApplications.md#impersonateascommunityuserallowed) | boolean | Allows the application to request login from external users and operate on their behalf. `Required` `Default(false)` `Filter(eq)` 
| [ImpersonateAsInternal<br />UserAllowed](Systems.Security.TrustedApplications.md#impersonateasinternaluserallowed) | boolean | Allows the application to request login from internal users and operate on their behalf. `Required` `Default(false)` `Filter(eq)` 
| [ImpersonateLoginUrl](Systems.Security.TrustedApplications.md#impersonateloginurl) | string (254) __nullable__ | The login Url used when an application is impersonated as (usually community) user; may include multiple addresses, separated by commas. 
| [ImpersonateLogoutUrl](Systems.Security.TrustedApplications.md#impersonatelogouturl) | string (254) __nullable__ | The logout Url used when an application is impersonated as (usually community) user; may include multiple addresses, separated by commas. 
| [IsEnabled](Systems.Security.TrustedApplications.md#isenabled) | boolean | Specifies whether the application is enabled for login. `Required` `Default(true)` `Filter(eq)` 
| [Name](Systems.Security.TrustedApplications.md#name) | string (254) | The multi-language name of the application. `Required` `Filter(eq;like)` `ORD` 
| [Notes](Systems.Security.TrustedApplications.md#notes) | string (max) __nullable__ | Notes for this TrustedApplication. 
| [ObjectVersion](Systems.Security.TrustedApplications.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Scope](Systems.Security.TrustedApplications.md#scope) | string (max) __nullable__ | The scope (according to RFC 6749) for which the application was trusted. The scope is an unordered list of space-delimited case-sensitive strings. Each string denotes a permission (see docs for possible values). `Introduced in version 20.1` 
| [SystemUserAllowed](Systems.Security.TrustedApplications.md#systemuserallowed) | boolean | Allows this application to logon as a service. `Required` `Default(false)` `Filter(eq)` 
| [SystemUserLoginUrl](Systems.Security.TrustedApplications.md#systemuserloginurl) | string (254) __nullable__ | The URL, which will be used by the login process, when the application logs in as a service. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [SystemUser](Systems.Security.TrustedApplications.md#systemuser) | [Users](Systems.Security.Users.md) (nullable) | The user, which will be used when the application logins as a service. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Authorizations | [TrustedApplicationAuthorizations](Systems.Security.TrustedApplicationAuthorizations.md) | List of `TrustedApplication<br />Authorization`(Systems.Security.TrustedApplication<br />Authorizations.md) child objects, based on the `Systems.Security.TrustedApplication<br />Authorization.TrustedApplication`(Systems.Security.TrustedApplication<br />Authorizations.md#trustedapplication) back reference 


## Attribute Details

### AccessTokens

Defines who is allowed to issue reference access tokens for this trusted application. `Required` `Default("NON")` `Filter(multi eq)` `Introduced in version 26.2.0.16`

_Type_: **[AccessTokens](Systems.Security.TrustedApplications.md#accesstokens)**  
_Category_: **System**  
Allowed values for the `AccessTokens`(Systems.Security.TrustedApplications.md#accesstokens) data attribute  
_Allowed Values (Systems.Security.TrustedApplicationsRepository.AccessTokens Enum Members)_  

| Value | Description |
| ---- | --- |
| None | Reference tokens cannot be issued. (Default). Stored as 'NON'. <br /> _Database Value:_ 'NON' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'None' |
| AuthenticatedUsers | Any authenticated (logged-in) user may issue.. Stored as 'USR'. <br /> _Database Value:_ 'USR' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'AuthenticatedUsers' |
| AdministratorsOnly | Only administrators may issue.. Stored as 'ADM'. <br /> _Database Value:_ 'ADM' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'AdministratorsOnly' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **None**  
_Show in UI_: **ShownByDefault**  

### ApplicationSecretHash

Hash of the secret of the client application. The secret is used when the client application needs to authorize itself in front of the identity provider. `Introduced in version 20.1`

_Type_: **string (250) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **250**  
_Show in UI_: **ShownByDefault**  

### ApplicationUri

Application globally unique Uri in reverse host name format. For example: "com.manufacturer/app". `Required` `Filter(eq)` `ORD`

_Type_: **string (254)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### BasicAuthenticationAllowed

If true, this application allows login with user name and password. When a client application uses basic authentication it must provide the application uri along with user name and password. Use with caution, because basic authentication is less secure than oauth! If a user is specified in System User, the basic authentication is allowed only for this user. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### ClientType

Specifies the client type, according to RFC 6749, e.g. the confidentiality of the client app. P=Public (e.g. browser or native app); C=Confidential (e.g. web server app). `Required` `Default("C")` `Introduced in version 20.1`

_Type_: **[ClientType](Systems.Security.TrustedApplications.md#clienttype)**  
_Category_: **System**  
Allowed values for the `ClientType`(Systems.Security.TrustedApplications.md#clienttype) data attribute  
_Allowed Values (Systems.Security.TrustedApplicationsRepository.ClientType Enum Members)_  

| Value | Description |
| ---- | --- |
| Confidential | Confidential value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Confidential' |
| Public | Public value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Public' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Confidential**  
_Show in UI_: **ShownByDefault**  

### CreationTimeUtc

Date and time (in UTC) when the application was registered. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
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
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### ImpersonateAsCommunityUserAllowed

Allows the application to request login from external users and operate on their behalf. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### ImpersonateAsInternalUserAllowed

Allows the application to request login from internal users and operate on their behalf. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### ImpersonateLoginUrl

The login Url used when an application is impersonated as (usually community) user; may include multiple addresses, separated by commas.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ImpersonateLogoutUrl

The logout Url used when an application is impersonated as (usually community) user; may include multiple addresses, separated by commas.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### IsEnabled

Specifies whether the application is enabled for login. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

The multi-language name of the application. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this TrustedApplication.

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

### Scope

The scope (according to RFC 6749) for which the application was trusted. The scope is an unordered list of space-delimited case-sensitive strings. Each string denotes a permission (see docs for possible values). `Introduced in version 20.1`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### SystemUserAllowed

Allows this application to logon as a service. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### SystemUserLoginUrl

The URL, which will be used by the login process, when the application logs in as a service.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### SystemUser

The user, which will be used when the application logins as a service. `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
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

