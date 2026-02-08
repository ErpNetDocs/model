---
uid: Systems.Security.Users
---
# Systems.Security.Users


User logins.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.Users  
Base Table: Sec_Users  
API access:  ReadWrite  

## Visualization
Display Format: {Name} <{Login}> [{UserType:DB}]  
Search Members: Login; Name  
Code Member: Login  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  3 - Track object and attribute changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Security.Users](Systems.Security.Users.md)  
  * [Systems.Security.UserAccessKeys](Systems.Security.UserAccessKeys.md)  
  * [Systems.Security.UserDevices](Systems.Security.UserDevices.md)  
  * [Systems.Security.UserGroups](Systems.Security.UserGroups.md)  
  * [Systems.Security.UserProviderLogins](Systems.Security.UserProviderLogins.md)  
  * [Systems.Security.UserProviderTokens](Systems.Security.UserProviderTokens.md)  
  * [Systems.Security.RoleUsers](Systems.Security.RoleUsers.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessFailedCount](Systems.Security.Users.md#accessfailedcount) | int32 | Indicates how many times the user has failed to login. May be used for locking out the user.`Required` `Default(0)` `Filter(eq;ge;le)` `Introduced in version 18.2` 
| [Active](Systems.Security.Users.md#active) | boolean | True when the login is currently active and the user can log in.`Required` `Default(true)` `Filter(eq)` 
| [BasicAuthenticationAllowed](Systems.Security.Users.md#basicauthenticationallowed) | boolean | If true, this user is allowed to use basic authentication. Use with caution, because basic authentication is less secure than oauth!`Required` `Default(false)` `Filter(eq)` `Introduced in version 23.1.1.35` 
| [CompanyName](Systems.Security.Users.md#companyname) | string (64) __nullable__ | Name of the company in which the user claims they are working.`Introduced in version 22.1.6.61` 
| [CreationTimeUtc](Systems.Security.Users.md#creationtimeutc) | datetime | The date and time (in UTC), when the user was created.`Required` `Default(Now)` `Filter(ge;le)` `ReadOnly` `Introduced in version 18.2` 
| [DefaultLanguage](Systems.Security.Users.md#defaultlanguage) | string (15) __nullable__ | The preferred default language of the user for UI, notifications, etc. Null means "en=English"`Filter(eq)` `Introduced in version 25.1.0.34` 
| [Email](Systems.Security.Users.md#email) | string (254) __nullable__ | Unique email of the user. Can be NULL because there may be login providers that don't use emails.`Filter(multi eq;like)` `ORD` `Introduced in version 18.2` 
| [EmailConfirmed](Systems.Security.Users.md#emailconfirmed) | boolean | Indicates whether the email address for the specified user has been verified.`Required` `Default(false)` `Filter(eq)` `ReadOnly` `Introduced in version 18.2` 
| [IsAdmin](Systems.Security.Users.md#isadmin) | boolean | 1 if the user is administrator, otherwise 0.`Required` `Default(false)` `Filter(eq)` 
| [LockoutEndUtc](Systems.Security.Users.md#lockoutendutc) | datetime __nullable__ | Contains the date and time (in UTC) until the user is locked. NULL when the user is not locked.`Filter(eq;ge;le;like)` `Introduced in version 18.2` 
| [Login](Systems.Security.Users.md#login) | string (64) | The login name of the user, which is usually the email`Required` `Filter(multi eq;like)` `ORD` 
| [Name](Systems.Security.Users.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The full name of the user`Required` `Filter(like)` 
| [Notes](Systems.Security.Users.md#notes) | string (254) __nullable__ | Notes for this User. 
| [Password](Systems.Security.Users.md#password) | string (64) __nullable__ | The password hash of the user, stored in the format, specified in Password Format.`Unit: PasswordFormat` `ReadOnly` 
| [PasswordFormat](Systems.Security.Users.md#passwordformat) | [PasswordFormat](Systems.Security.Users.md#passwordformat) | The format of the Password. MD5=MD5 format; AN3 = ASP.NET Core Identity v3.`Required` `Default(&quot;MD5&quot;)` `Filter(eq)` `Introduced in version 18.2` 
| [PhoneNumber](Systems.Security.Users.md#phonenumber) | string (64) __nullable__ | Used only for two-factor authentication. NULL when phone-based two-factor is not used.`Filter(eq;like)` `Introduced in version 18.2` 
| [PhoneNumberConfirmed](Systems.Security.Users.md#phonenumberconfirmed) | boolean | Indicates whether the Phone Number has been verified.`Required` `Default(false)` `Filter(eq)` `Introduced in version 18.2` 
| [RegistrationMessage](Systems.Security.Users.md#registrationmessage) | string (254) __nullable__ | Message from the user to the registration operator, regarding the desired permissions and assignment.`Introduced in version 22.1.6.61` 
| [TwoFactorEnabled](Systems.Security.Users.md#twofactorenabled) | boolean | Indicates whether two-factor authentication has been enabled.`Required` `Default(false)` `Filter(eq)` `Introduced in version 18.2` 
| [UserType](Systems.Security.Users.md#usertype) | [UserType](Systems.Security.Users.md#usertype) | Specifies the user type. INT=Internal; EXT=External (community); VIR=Virtual (No login); SYS=System; APP=Application (No login); INI=Invitation Internal (No login); INE=Invitation External (No login).`Required` `Default(&quot;INT&quot;)` `Filter(multi eq;like)` `Introduced in version 18.2` 
| [VoiceExtensionNumbers](Systems.Security.Users.md#voiceextensionnumbers) | string (254) __nullable__ | Comma separated list of internal extension numbers and contexts of the voice telephones of the user in form 'Number@Context'. Used for VOIP integration 
| [WindowsUserName](Systems.Security.Users.md#windowsusername) | string (128) __nullable__ | The Windows (Active Directory) user, to which this login is bound. The user will be allowed to login only when the client machine is logged in Active Directory with the specified user. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Domain](Systems.Security.Users.md#domain) | [Domains](Systems.Security.Domains.md) (nullable) | The domain, to which the user belongs. |
| [Model](Systems.Security.Users.md#model) | [Models](Projects.AI.Models.md) (nullable) | The AI model associated with the user for their interactions. NULL means that this user has no AI model associated. |
| [Person](Systems.Security.Users.md#person) | [Persons](General.Contacts.Persons.md) (nullable) | The person from within the system, which is authenticated with this login. NULL means that this user is not associated with a person record in the database. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.Users.md#id) | guid |  
| [ObjectVersion](Systems.Security.Users.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Security.Users.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Security.Users.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Security.Users.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Security.Users.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| AccessKeys | [UserAccessKeys](Systems.Security.UserAccessKeys.md) | List of `UserAccessKey`(Systems.Security.UserAccessKeys.md) child objects, based on the `Systems.Security.UserAccessKey.User`(Systems.Security.UserAccessKeys.md#user) back reference 
| Devices | [UserDevices](Systems.Security.UserDevices.md) | List of `UserDevice`(Systems.Security.UserDevices.md) child objects, based on the `Systems.Security.UserDevice.User`(Systems.Security.UserDevices.md#user) back reference 
| Groups | [UserGroups](Systems.Security.UserGroups.md) | List of `UserGroup`(Systems.Security.UserGroups.md) child objects, based on the `Systems.Security.UserGroup.User`(Systems.Security.UserGroups.md#user) back reference 
| ProviderLogins | [UserProviderLogins](Systems.Security.UserProviderLogins.md) | List of `UserProviderLogin`(Systems.Security.UserProviderLogins.md) child objects, based on the `Systems.Security.UserProviderLogin.User`(Systems.Security.UserProviderLogins.md#user) back reference 
| ProviderTokens | [UserProviderTokens](Systems.Security.UserProviderTokens.md) | List of `UserProviderToken`(Systems.Security.UserProviderTokens.md) child objects, based on the `Systems.Security.UserProviderToken.User`(Systems.Security.UserProviderTokens.md#user) back reference 
| RoleUsers | [RoleUsers](Systems.Security.RoleUsers.md) | List of `RoleUser`(Systems.Security.RoleUsers.md) child objects, based on the `Systems.Security.RoleUser.User`(Systems.Security.RoleUsers.md#user) back reference 


## Attribute Details

### AccessFailedCount

Indicates how many times the user has failed to login. May be used for locking out the user.`Required` `Default(0)` `Filter(eq;ge;le)` `Introduced in version 18.2`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### Active

True when the login is currently active and the user can log in.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### BasicAuthenticationAllowed

If true, this user is allowed to use basic authentication. Use with caution, because basic authentication is less secure than oauth!`Required` `Default(false)` `Filter(eq)` `Introduced in version 23.1.1.35`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### CompanyName

Name of the company in which the user claims they are working.`Introduced in version 22.1.6.61`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### CreationTimeUtc

The date and time (in UTC), when the user was created.`Required` `Default(Now)` `Filter(ge;le)` `ReadOnly` `Introduced in version 18.2`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### DefaultLanguage

The preferred default language of the user for UI, notifications, etc. Null means "en=English"`Filter(eq)` `Introduced in version 25.1.0.34`

Type: **string (15) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **15**  
Show in UI: **ShownByDefault**  

### Email

Unique email of the user. Can be NULL because there may be login providers that don't use emails.`Filter(multi eq;like)` `ORD` `Introduced in version 18.2`

Type: **string (254) __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### EmailConfirmed

Indicates whether the email address for the specified user has been verified.`Required` `Default(false)` `Filter(eq)` `ReadOnly` `Introduced in version 18.2`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### IsAdmin

1 if the user is administrator, otherwise 0.`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LockoutEndUtc

Contains the date and time (in UTC) until the user is locked. NULL when the user is not locked.`Filter(eq;ge;le;like)` `Introduced in version 18.2`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Login

The login name of the user, which is usually the email`Required` `Filter(multi eq;like)` `ORD`

Type: **string (64)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Name

The full name of the user`Required` `Filter(like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this User.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Password

The password hash of the user, stored in the format, specified in Password Format.`Unit: PasswordFormat` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### PasswordFormat

The format of the Password. MD5=MD5 format; AN3 = ASP.NET Core Identity v3.`Required` `Default(&quot;MD5&quot;)` `Filter(eq)` `Introduced in version 18.2`

Type: **[PasswordFormat](Systems.Security.Users.md#passwordformat)**  
Category: **System**  
Allowed values for the `PasswordFormat`(Systems.Security.Users.md#passwordformat) data attribute  
Allowed Values (Systems.Security.UsersRepository.PasswordFormat Enum Members)  

| Value | Description |
| ---- | --- |
| MD5 | Store password in the old format, used by the Windows App. Stored as 'MD5'. <br /> Database Value: 'MD5' <br /> Model Value: 0 <br /> Domain API Value: 'MD5' |
| AspNetCoreV3 | Store passwords in v3 format used by ASP.NET Core. Stored as 'AN3'. <br /> Database Value: 'AN3' <br /> Model Value: 1 <br /> Domain API Value: 'AspNetCoreV3' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **MD5**  
Show in UI: **ShownByDefault**  

### PhoneNumber

Used only for two-factor authentication. NULL when phone-based two-factor is not used.`Filter(eq;like)` `Introduced in version 18.2`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### PhoneNumberConfirmed

Indicates whether the Phone Number has been verified.`Required` `Default(false)` `Filter(eq)` `Introduced in version 18.2`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### RegistrationMessage

Message from the user to the registration operator, regarding the desired permissions and assignment.`Introduced in version 22.1.6.61`

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### TwoFactorEnabled

Indicates whether two-factor authentication has been enabled.`Required` `Default(false)` `Filter(eq)` `Introduced in version 18.2`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### UserType

Specifies the user type. INT=Internal; EXT=External (community); VIR=Virtual (No login); SYS=System; APP=Application (No login); INI=Invitation Internal (No login); INE=Invitation External (No login).`Required` `Default(&quot;INT&quot;)` `Filter(multi eq;like)` `Introduced in version 18.2`

Type: **[UserType](Systems.Security.Users.md#usertype)**  
Category: **System**  
Allowed values for the `UserType`(Systems.Security.Users.md#usertype) data attribute  
Allowed Values (Systems.Security.UsersRepository.UserType Enum Members)  

| Value | Description |
| ---- | --- |
| InternalUser | Internal users are the usual ERP users. They have access to internal and external content.. Stored as 'INT'. <br /> Database Value: 'INT' <br /> Model Value: 0 <br /> Domain API Value: 'InternalUser' |
| ExternalCommunityUser | External users can access only external (community) content. They are usually created withing community sites.. Stored as 'EXT'. <br /> Database Value: 'EXT' <br /> Model Value: 1 <br /> Domain API Value: 'ExternalCommunityUser' |
| VirtualUserNoLogin | Virtual users cannot login, but can be used for task assignments, etc.. Stored as 'VIR'. <br /> Database Value: 'VIR' <br /> Model Value: 2 <br /> Domain API Value: 'VirtualUserNoLogin' |
| SystemUserNoLogin | System users are used only by local system applications.. Stored as 'SYS'. <br /> Database Value: 'SYS' <br /> Model Value: 3 <br /> Domain API Value: 'SystemUserNoLogin' |
| ApplicationUserNoLogin | Application users are used by applications. They do not have a password, but login by providing application credentials.. Stored as 'APP'. <br /> Database Value: 'APP' <br /> Model Value: 4 <br /> Domain API Value: 'ApplicationUserNoLogin' |
| InvitationInternalNoLogin | InvitationInternalNoLogin value. Stored as 'INI'. <br /> Database Value: 'INI' <br /> Model Value: 5 <br /> Domain API Value: 'InvitationInternalNoLogin' |
| InvitationExternalNoLogin | InvitationExternalNoLogin value. Stored as 'INE'. <br /> Database Value: 'INE' <br /> Model Value: 6 <br /> Domain API Value: 'InvitationExternalNoLogin' |

Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Default Value: **InternalUser**  
Show in UI: **ShownByDefault**  

### VoiceExtensionNumbers

Comma separated list of internal extension numbers and contexts of the voice telephones of the user in form 'Number@Context'. Used for VOIP integration

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### WindowsUserName

The Windows (Active Directory) user, to which this login is bound. The user will be allowed to login only when the client machine is logged in Active Directory with the specified user.

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **128**  
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

### Domain

The domain, to which the user belongs.

Type: **[Domains](Systems.Security.Domains.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Model

The AI model associated with the user for their interactions. NULL means that this user has no AI model associated.

Type: **[Models](Projects.AI.Models.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Person

The person from within the system, which is authenticated with this login. NULL means that this user is not associated with a person record in the database.

Type: **[Persons](General.Contacts.Persons.md) (nullable)**  
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

[!list limit=1000 erp.entity=Systems.Security.Users erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.Users erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_Users

Domain API Entity Type: 
Systems_Security_User

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_Users?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_Users?$top=10>

