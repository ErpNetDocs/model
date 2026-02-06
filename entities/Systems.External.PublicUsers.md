---
uid: Systems.External.PublicUsers
---
# Systems.External.PublicUsers


/Users of the publicly offered services. This includes Internet, external and employee users.

## General
Namespace: [Systems.External](Systems.External.md)  
Repository: Systems.External.PublicUsers  
Base Table: Ext_Public_Users  
API access:  ReadWrite  

> [!NOTE]  
> **OBSOLETE! Do not use!**   


## Visualization
Display Format: {CompanyName}  
Search Members: PhoneNumber; CompanyName  
Code Member: PhoneNumber  
Name Member: CompanyName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.External.PublicUsers](Systems.External.PublicUsers.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AboutMeText](Systems.External.PublicUsers.md#aboutmetext) | string (1024) __nullable__ | About me text, written by the user. 
| [Address](Systems.External.PublicUsers.md#address) | string (128) __nullable__ | The primary address of the user. Can be specified with latin or local characters. 
| [AlternateEmail](Systems.External.PublicUsers.md#alternateemail) | string (64) __nullable__ | Alternate email of the user. Can be used for backup email for password restore. 
| [City](Systems.External.PublicUsers.md#city) | string (64) __nullable__ | The state of residence of the user. Can be specified with latin or local letters. 
| [CompanyName](Systems.External.PublicUsers.md#companyname) | string (64) __nullable__ | The name of the company, for which the user works, as specified by the user. 
| [Country](Systems.External.PublicUsers.md#country) | string (64) __nullable__ | The country of residence of the user, with latin letters. 
| [CreatedOn](Systems.External.PublicUsers.md#createdon) | datetime __nullable__ | The date and time when the user was created. 
| [Email](Systems.External.PublicUsers.md#email) | string (64) | The primary email of the user. Used for notifications and password restore. 
| [FirstName](Systems.External.PublicUsers.md#firstname) | string (64) | First name of the user. 
| [IsActive](Systems.External.PublicUsers.md#isactive) | boolean | Specifies whether the user account is active and access should be allowed. 
| [LastName](Systems.External.PublicUsers.md#lastname) | string (64) | Last name of the user. 
| [Notes](Systems.External.PublicUsers.md#notes) | string (max) __nullable__ | Notes for this PublicUser. 
| [PasswordAlgorithm](Systems.External.PublicUsers.md#passwordalgorithm) | string (16) | Uniquely specifies the password storage algorithm among some system recognized algorithms. Usually specifies the hashing and the stretching functions. For example, 'PBKDF2-SHA1'. 
| [PasswordHash](Systems.External.PublicUsers.md#passwordhash) | string (128) | Actual password storage. The format of the contents is determined by Password Algorithm. 
| [PasswordRecoveryCode](Systems.External.PublicUsers.md#passwordrecoverycode) | guid __nullable__ | Automatically generated unique code for the last password recovery attempt 
| [PasswordRecovery<br />CreationTime](Systems.External.PublicUsers.md#passwordrecoverycreationtime) | datetime __nullable__ | Date and time when the last password recovery code was created 
| [PhoneNumber](Systems.External.PublicUsers.md#phonenumber) | string (16) __nullable__ | The primary phone number of the user. 
| [PostalCode](Systems.External.PublicUsers.md#postalcode) | string (16) __nullable__ | The postal code of the default address of the user. 
| [ProfilePicture](Systems.External.PublicUsers.md#profilepicture) | byte[] __nullable__ | Profile picture of the user. 
| [State](Systems.External.PublicUsers.md#state) | string (64) __nullable__ | The state of residence of the user within the country. Can be specified with latin or local characters. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Company](Systems.External.PublicUsers.md#company) | [Companies](General.Contacts.Companies.md) (nullable) | Link to an internal company record, specified by internal employee. |
| [Person](Systems.External.PublicUsers.md#person) | [Persons](General.Contacts.Persons.md) (nullable) | Link to an internal person record. Usually specified by internal employee, but can also be an automated process. |
| [<s>PublicUserList</s>](Systems.External.PublicUsers.md#publicuserlist) | [PublicUserLists](Systems.External.PublicUserLists.md) | **OBSOLETE! Do not use!** The list in which the user account is saved. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.External.PublicUsers.md#id) | guid |  
| [ObjectVersion](Systems.External.PublicUsers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.External.PublicUsers.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.External.PublicUsers.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.External.PublicUsers.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.External.PublicUsers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AboutMeText

About me text, written by the user.

Type: **string (1024) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **1024**  
Show in UI: **ShownByDefault**  

### Address

The primary address of the user. Can be specified with latin or local characters.

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### AlternateEmail

Alternate email of the user. Can be used for backup email for password restore.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### City

The state of residence of the user. Can be specified with latin or local letters.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### CompanyName

The name of the company, for which the user works, as specified by the user.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Country

The country of residence of the user, with latin letters.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### CreatedOn

The date and time when the user was created.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### Email

The primary email of the user. Used for notifications and password restore.

Type: **string (64)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### FirstName

First name of the user.

Type: **string (64)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### IsActive

Specifies whether the user account is active and access should be allowed.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### LastName

Last name of the user.

Type: **string (64)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this PublicUser.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### PasswordAlgorithm

Uniquely specifies the password storage algorithm among some system recognized algorithms. Usually specifies the hashing and the stretching functions. For example, 'PBKDF2-SHA1'.

Type: **string (16)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### PasswordHash

Actual password storage. The format of the contents is determined by Password Algorithm.

Type: **string (128)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### PasswordRecoveryCode

Automatically generated unique code for the last password recovery attempt

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PasswordRecoveryCreationTime

Date and time when the last password recovery code was created

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PhoneNumber

The primary phone number of the user.

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### PostalCode

The postal code of the default address of the user.

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### ProfilePicture

Profile picture of the user.

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### State

The state of residence of the user within the country. Can be specified with latin or local characters.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
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

### Company

Link to an internal company record, specified by internal employee.

Type: **[Companies](General.Contacts.Companies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Person

Link to an internal person record. Usually specified by internal employee, but can also be an automated process.

Type: **[Persons](General.Contacts.Persons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PublicUserList

**OBSOLETE! Do not use!** The list in which the user account is saved.

Type: **[PublicUserLists](Systems.External.PublicUserLists.md)**  
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

