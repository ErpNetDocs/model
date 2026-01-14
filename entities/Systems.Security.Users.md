---
uid: Systems.Security.Users
---
# Systems.Security.Users Entity

**Namespace:** [Systems.Security](Systems.Security.md)  

User logins. Entity: Sec_Users

## Default Visualization
Default Display Text Format:  
_{Name} <{Login}> [{UserType:DB}]_  
Default Search Members:  
_Login; Name_  
Code Data Member:  
_Login_  
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
| [AccessFailedCount](Systems.Security.Users.md#accessfailedcount) | int32 | Indicates how many times the user has failed to login. May be used for locking out the user. `Required` `Default(0)` `Filter(eq;ge;le)` `Introduced in version 18.2` 
| [Active](Systems.Security.Users.md#active) | boolean | True when the login is currently active and the user can log in. `Required` `Default(true)` `Filter(eq)` 
| [AggregateLastUpdateTimeUtc](Systems.Security.Users.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [BasicAuthenticationAllowed](Systems.Security.Users.md#basicauthenticationallowed) | boolean | If true, this user is allowed to use basic authentication. Use with caution, because basic authentication is less secure than oauth!. `Required` `Default(false)` `Filter(eq)` `Introduced in version 23.1.1.35` 
| [CompanyName](Systems.Security.Users.md#companyname) | string (64) __nullable__ | Name of the company in which the user claims they are working. `Introduced in version 22.1.6.61` 
| [CreationTimeUtc](Systems.Security.Users.md#creationtimeutc) | datetime | The date and time (in UTC), when the user was created. `Required` `Default(Now)` `Filter(ge;le)` `ReadOnly` `Introduced in version 18.2` 
| [DefaultLanguage](Systems.Security.Users.md#defaultlanguage) | string (15) __nullable__ | The preferred default language of the user for UI, notifications, etc. Null means "en=English". `Filter(eq)` `Introduced in version 25.1.0.34` 
| [DisplayText](Systems.Security.Users.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Email](Systems.Security.Users.md#email) | string (254) __nullable__ | Unique email of the user. Can be null because there may be login providers that don't use emails. `Filter(multi eq;like)` `ORD` `Introduced in version 18.2` 
| [EmailConfirmed](Systems.Security.Users.md#emailconfirmed) | boolean | Indicates whether the email address for the specified user has been verified. `Required` `Default(false)` `Filter(eq)` `ReadOnly` `Introduced in version 18.2` 
| [ExternalId](Systems.Security.Users.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Security.Users.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Security.Users.md#id) | guid |  
| [IsAdmin](Systems.Security.Users.md#isadmin) | boolean | True if the user is administrator, otherwise 0. `Required` `Default(false)` `Filter(eq)` 
| [LockoutEndUtc](Systems.Security.Users.md#lockoutendutc) | datetime __nullable__ | Contains the date and time (in UTC) until the user is locked. null when the user is not locked. `Filter(eq;ge;le;like)` `Introduced in version 18.2` 
| [Login](Systems.Security.Users.md#login) | string (64) | The login name of the user, which is usually the email. `Required` `Filter(multi eq;like)` `ORD` 
| [Name](Systems.Security.Users.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The full name of the user. `Required` `Filter(like)` 
| [Notes](Systems.Security.Users.md#notes) | string (254) __nullable__ | Notes for this User. 
| [ObjectVersion](Systems.Security.Users.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Password](Systems.Security.Users.md#password) | string (64) __nullable__ | The password hash of the user, stored in the format, specified in Password Format. `Unit: PasswordFormat` `ReadOnly` 
| [PasswordFormat](Systems.Security.Users.md#passwordformat) | [PasswordFormat](Systems.Security.Users.md#passwordformat) | The format of the Password. MD5=MD5 format; AN3 = ASP.NET Core Identity v3. `Required` `Default("MD5")` `Filter(eq)` `Introduced in version 18.2` 
| [PhoneNumber](Systems.Security.Users.md#phonenumber) | string (64) __nullable__ | Used only for two-factor authentication. null when phone-based two-factor is not used. `Filter(eq;like)` `Introduced in version 18.2` 
| [PhoneNumberConfirmed](Systems.Security.Users.md#phonenumberconfirmed) | boolean | Indicates whether the Phone Number has been verified. `Required` `Default(false)` `Filter(eq)` `Introduced in version 18.2` 
| [RegistrationMessage](Systems.Security.Users.md#registrationmessage) | string (254) __nullable__ | Message from the user to the registration operator, regarding the desired permissions and assignment. `Introduced in version 22.1.6.61` 
| [TwoFactorEnabled](Systems.Security.Users.md#twofactorenabled) | boolean | Indicates whether two-factor authentication has been enabled. `Required` `Default(false)` `Filter(eq)` `Introduced in version 18.2` 
| [UserType](Systems.Security.Users.md#usertype) | [UserType](Systems.Security.Users.md#usertype) | Specifies the user type. INT=Internal; EXT=External (community); VIR=Virtual (No login); SYS=System; APP=Application (No lofin); INI=Invitation Internal (No login); INE=Invitation External (No login). `Required` `Default("INT")` `Filter(multi eq;like)` `Introduced in version 18.2` 
| [VoiceExtensionNumbers](Systems.Security.Users.md#voiceextensionnumbers) | string (254) __nullable__ | Comma separated list of internal extension numbers of the voice telephones of the user. Used for VOIP integration. 
| [WindowsUserName](Systems.Security.Users.md#windowsusername) | string (128) __nullable__ | The Windows (Active Directory) user, to which this login is bound. The user will be allowed to login only when the client machine is logged in Active Directory with the specified user. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Domain](Systems.Security.Users.md#domain) | [Domains](Systems.Security.Domains.md) (nullable) | The domain, to which the user belongs. `Filter(multi eq)` `Introduced in version 20.1` |
| [Model](Systems.Security.Users.md#model) | [Models](Projects.AI.Models.md) (nullable) | The AI model associated with the user for their interactions. null means that this user has no AI model associated. `Filter(multi eq)` `Introduced in version 24.1.5.34` |
| [Person](Systems.Security.Users.md#person) | [Persons](General.Contacts.Persons.md) (nullable) | The person from within the system, which is authenticated with this login. null means that this user is not associated with a person record in the database. `Filter(multi eq)` |

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

Indicates how many times the user has failed to login. May be used for locking out the user. `Required` `Default(0)` `Filter(eq;ge;le)` `Introduced in version 18.2`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### Active

True when the login is currently active and the user can log in. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### BasicAuthenticationAllowed

If true, this user is allowed to use basic authentication. Use with caution, because basic authentication is less secure than oauth!. `Required` `Default(false)` `Filter(eq)` `Introduced in version 23.1.1.35`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### CompanyName

Name of the company in which the user claims they are working. `Introduced in version 22.1.6.61`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### CreationTimeUtc

The date and time (in UTC), when the user was created. `Required` `Default(Now)` `Filter(ge;le)` `ReadOnly` `Introduced in version 18.2`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

### DefaultLanguage

The preferred default language of the user for UI, notifications, etc. Null means "en=English". `Filter(eq)` `Introduced in version 25.1.0.34`

_Type_: **string (15) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **15**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Email

Unique email of the user. Can be null because there may be login providers that don't use emails. `Filter(multi eq;like)` `ORD` `Introduced in version 18.2`

_Type_: **string (254) __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### EmailConfirmed

Indicates whether the email address for the specified user has been verified. `Required` `Default(false)` `Filter(eq)` `ReadOnly` `Introduced in version 18.2`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

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

### IsAdmin

True if the user is administrator, otherwise 0. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### LockoutEndUtc

Contains the date and time (in UTC) until the user is locked. null when the user is not locked. `Filter(eq;ge;le;like)` `Introduced in version 18.2`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Login

The login name of the user, which is usually the email. `Required` `Filter(multi eq;like)` `ORD`

_Type_: **string (64)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Name

The full name of the user. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this User.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Password

The password hash of the user, stored in the format, specified in Password Format. `Unit: PasswordFormat` `ReadOnly`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### PasswordFormat

The format of the Password. MD5=MD5 format; AN3 = ASP.NET Core Identity v3. `Required` `Default("MD5")` `Filter(eq)` `Introduced in version 18.2`

_Type_: **[PasswordFormat](Systems.Security.Users.md#passwordformat)**  
_Category_: **System**  
Allowed values for the `PasswordFormat`(Systems.Security.Users.md#passwordformat) data attribute  
_Allowed Values (Systems.Security.UsersRepository.PasswordFormat Enum Members)_  

| Value | Description |
| ---- | --- |
| MD5 | Store password in the old format, used by the Windows App. Stored as 'MD5'. <br /> _Database Value:_ 'MD5' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'MD5' |
| AspNetCoreV3 | Store passwords in v3 format used by ASP.NET Core. Stored as 'AN3'. <br /> _Database Value:_ 'AN3' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'AspNetCoreV3' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **MD5**  
_Show in UI_: **ShownByDefault**  

### PhoneNumber

Used only for two-factor authentication. null when phone-based two-factor is not used. `Filter(eq;like)` `Introduced in version 18.2`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### PhoneNumberConfirmed

Indicates whether the Phone Number has been verified. `Required` `Default(false)` `Filter(eq)` `Introduced in version 18.2`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### RegistrationMessage

Message from the user to the registration operator, regarding the desired permissions and assignment. `Introduced in version 22.1.6.61`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### TwoFactorEnabled

Indicates whether two-factor authentication has been enabled. `Required` `Default(false)` `Filter(eq)` `Introduced in version 18.2`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### UserType

Specifies the user type. INT=Internal; EXT=External (community); VIR=Virtual (No login); SYS=System; APP=Application (No lofin); INI=Invitation Internal (No login); INE=Invitation External (No login). `Required` `Default("INT")` `Filter(multi eq;like)` `Introduced in version 18.2`

_Type_: **[UserType](Systems.Security.Users.md#usertype)**  
_Category_: **System**  
Allowed values for the `UserType`(Systems.Security.Users.md#usertype) data attribute  
_Allowed Values (Systems.Security.UsersRepository.UserType Enum Members)_  

| Value | Description |
| ---- | --- |
| InternalUser | Internal users are the usual ERP users. They have access to internal and external content.. Stored as 'INT'. <br /> _Database Value:_ 'INT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'InternalUser' |
| ExternalCommunityUser | External users can access only external (community) content. They are usually created withing community sites.. Stored as 'EXT'. <br /> _Database Value:_ 'EXT' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ExternalCommunityUser' |
| VirtualUserNoLogin | Virtual users cannot login, but can be used for task assignments, etc.. Stored as 'VIR'. <br /> _Database Value:_ 'VIR' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'VirtualUserNoLogin' |
| SystemUserNoLogin | System users are used only by local system applications.. Stored as 'SYS'. <br /> _Database Value:_ 'SYS' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'SystemUserNoLogin' |
| ApplicationUserNoLogin | Application users are used by applications. They do not have a password, but login by providing application credentials.. Stored as 'APP'. <br /> _Database Value:_ 'APP' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'ApplicationUserNoLogin' |
| InvitationInternalNoLogin | InvitationInternalNoLogin value. Stored as 'INI'. <br /> _Database Value:_ 'INI' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'InvitationInternalNoLogin' |
| InvitationExternalNoLogin | InvitationExternalNoLogin value. Stored as 'INE'. <br /> _Database Value:_ 'INE' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'InvitationExternalNoLogin' |

_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **InternalUser**  
_Show in UI_: **ShownByDefault**  

### VoiceExtensionNumbers

Comma separated list of internal extension numbers of the voice telephones of the user. Used for VOIP integration.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### WindowsUserName

The Windows (Active Directory) user, to which this login is bound. The user will be allowed to login only when the client machine is logged in Active Directory with the specified user.

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Domain

The domain, to which the user belongs. `Filter(multi eq)` `Introduced in version 20.1`

_Type_: **[Domains](Systems.Security.Domains.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Model

The AI model associated with the user for their interactions. null means that this user has no AI model associated. `Filter(multi eq)` `Introduced in version 24.1.5.34`

_Type_: **[Models](Projects.AI.Models.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Person

The person from within the system, which is authenticated with this login. null means that this user is not associated with a person record in the database. `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md) (nullable)**  
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

