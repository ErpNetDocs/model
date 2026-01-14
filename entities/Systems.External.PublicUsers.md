---
uid: Systems.External.PublicUsers
---
# Systems.External.PublicUsers Entity

**Namespace:** [Systems.External](Systems.External.md)  

/Users of the publicly offered services. This includes Internet, external and employee users. Entity: Ext_Public_Users (Obsoleted in version 22.1.6.73)

> [!NOTE]  
> **OBSOLETE! Do not use!**   


## Default Visualization
Default Display Text Format:  
_{CompanyName}_  
Default Search Members:  
_PhoneNumber; CompanyName_  
Code Data Member:  
_PhoneNumber_  
Name Data Member:  
_CompanyName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.External.PublicUsers](Systems.External.PublicUsers.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AboutMeText](Systems.External.PublicUsers.md#aboutmetext) | string (1024) __nullable__ | About me text, written by the user. 
| [Address](Systems.External.PublicUsers.md#address) | string (128) __nullable__ | The primary address of the user. Can be specified with latin or local characters. `Filter(like)` 
| [AggregateLastUpdateTimeUtc](Systems.External.PublicUsers.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [AlternateEmail](Systems.External.PublicUsers.md#alternateemail) | string (64) __nullable__ | Alternate email of the user. Can be used for backup email for password restore. `Filter(like)` 
| [City](Systems.External.PublicUsers.md#city) | string (64) __nullable__ | The state of residence of the user. Can be specified with latin or local letters. `Filter(like)` 
| [CompanyName](Systems.External.PublicUsers.md#companyname) | string (64) __nullable__ | The name of the company, for which the user works, as specified by the user. `Filter(like)` 
| [Country](Systems.External.PublicUsers.md#country) | string (64) __nullable__ | The country of residence of the user, with latin letters. `Filter(like)` 
| [CreatedOn](Systems.External.PublicUsers.md#createdon) | datetime __nullable__ | The date and time when the user was created. `Default(Now)` `Filter(ge;le)` 
| [DisplayText](Systems.External.PublicUsers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Email](Systems.External.PublicUsers.md#email) | string (64) | The primary email of the user. Used for notifications and password restore. `Required` `Filter(like)` 
| [ExternalId](Systems.External.PublicUsers.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.External.PublicUsers.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FirstName](Systems.External.PublicUsers.md#firstname) | string (64) | First name of the user. `Required` `Filter(like)` 
| [Id](Systems.External.PublicUsers.md#id) | guid |  
| [IsActive](Systems.External.PublicUsers.md#isactive) | boolean | Specifies whether the user account is active and access should be allowed. `Required` `Default(true)` `Filter(eq)` 
| [LastName](Systems.External.PublicUsers.md#lastname) | string (64) | Last name of the user. `Required` `Filter(like)` 
| [Notes](Systems.External.PublicUsers.md#notes) | string (max) __nullable__ | Notes for this PublicUser. 
| [ObjectVersion](Systems.External.PublicUsers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PasswordAlgorithm](Systems.External.PublicUsers.md#passwordalgorithm) | string (16) | Uniquely specifies the password storage algorithm among some system recognized algorithms. Usually specifies the hashing and the stretching functions. For example, 'PBKDF2-SHA1'. `Required` `Filter(like)` 
| [PasswordHash](Systems.External.PublicUsers.md#passwordhash) | string (128) | Actual password storage. The format of the contents is determined by Password Algorithm. `Required` `Filter(like)` 
| [PasswordRecoveryCode](Systems.External.PublicUsers.md#passwordrecoverycode) | guid __nullable__ | Automatically generated unique code for the last password recovery attempt. `Filter(multi eq)` `ReadOnly` 
| [PasswordRecovery<br />CreationTime](Systems.External.PublicUsers.md#passwordrecoverycreationtime) | datetime __nullable__ | Date and time when the last password recovery code was created. `Filter(ge;le)` `ReadOnly` 
| [PhoneNumber](Systems.External.PublicUsers.md#phonenumber) | string (16) __nullable__ | The primary phone number of the user. `Filter(like)` 
| [PostalCode](Systems.External.PublicUsers.md#postalcode) | string (16) __nullable__ | The postal code of the default address of the user. `Filter(like)` 
| [ProfilePicture](Systems.External.PublicUsers.md#profilepicture) | byte[] __nullable__ | Profile picture of the user. 
| [State](Systems.External.PublicUsers.md#state) | string (64) __nullable__ | The state of residence of the user within the country. Can be specified with latin or local characters. `Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Company](Systems.External.PublicUsers.md#company) | [Companies](General.Contacts.Companies.md) (nullable) | Link to an internal company record, specified by internal employee. `Filter(multi eq)` |
| [Person](Systems.External.PublicUsers.md#person) | [Persons](General.Contacts.Persons.md) (nullable) | Link to an internal person record. Usually specified by internal employee, but can also be an automated process. `Filter(multi eq)` |
| [<s>PublicUserList</s>](Systems.External.PublicUsers.md#publicuserlist) | [PublicUserLists](Systems.External.PublicUserLists.md) | **OBSOLETE! Do not use!** The list in which the user account is saved. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` `Obsolete` |


## Attribute Details

### AboutMeText

About me text, written by the user.

_Type_: **string (1024) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **1024**  
_Show in UI_: **ShownByDefault**  

### Address

The primary address of the user. Can be specified with latin or local characters. `Filter(like)`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### AlternateEmail

Alternate email of the user. Can be used for backup email for password restore. `Filter(like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### City

The state of residence of the user. Can be specified with latin or local letters. `Filter(like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### CompanyName

The name of the company, for which the user works, as specified by the user. `Filter(like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Country

The country of residence of the user, with latin letters. `Filter(like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### CreatedOn

The date and time when the user was created. `Default(Now)` `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Email

The primary email of the user. Used for notifications and password restore. `Required` `Filter(like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
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

### FirstName

First name of the user. `Required` `Filter(like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Specifies whether the user account is active and access should be allowed. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### LastName

Last name of the user. `Required` `Filter(like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this PublicUser.

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

### PasswordAlgorithm

Uniquely specifies the password storage algorithm among some system recognized algorithms. Usually specifies the hashing and the stretching functions. For example, 'PBKDF2-SHA1'. `Required` `Filter(like)`

_Type_: **string (16)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### PasswordHash

Actual password storage. The format of the contents is determined by Password Algorithm. `Required` `Filter(like)`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### PasswordRecoveryCode

Automatically generated unique code for the last password recovery attempt. `Filter(multi eq)` `ReadOnly`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PasswordRecoveryCreationTime

Date and time when the last password recovery code was created. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### PhoneNumber

The primary phone number of the user. `Filter(like)`

_Type_: **string (16) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### PostalCode

The postal code of the default address of the user. `Filter(like)`

_Type_: **string (16) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### ProfilePicture

Profile picture of the user.

_Type_: **byte[] __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### State

The state of residence of the user within the country. Can be specified with latin or local characters. `Filter(like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Company

Link to an internal company record, specified by internal employee. `Filter(multi eq)`

_Type_: **[Companies](General.Contacts.Companies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Person

Link to an internal person record. Usually specified by internal employee, but can also be an automated process. `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PublicUserList

**OBSOLETE! Do not use!** The list in which the user account is saved. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` `Obsolete`

_Type_: **[PublicUserLists](Systems.External.PublicUserLists.md)**  
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

[!list limit=1000 erp.entity=Systems.External.PublicUsers erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.External.PublicUsers erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_External_PublicUsers

Domain API Entity Type: 
Systems_External_PublicUser

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_External_PublicUsers?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_External_PublicUsers?$top=10>

