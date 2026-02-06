---
uid: Public.Users
---
# Public.Users (View)


Virtual view returning profile data for the logged in user

## General
Namespace: [Public](Public.md)  
Repository: Public.Users  
Introduced In Version: 22.1.4.22  
API access:  ReadWrite  

## Visualization
Display Format: {Name}  
Search Members: Name  
Category:  Views  
Show in UI:  CannotBeShown  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Public.Users](Public.Users.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Email](Public.Users.md#email) | string (254) __nullable__ | Unique email of the user. Can be NULL because there may be login providers that don't use emails. 
| [IsAdmin](Public.Users.md#isadmin) | boolean | 1 if the user is administrator, otherwise 0. 
| [Login](Public.Users.md#login) | string (64) | The login name of the user, which is usually the email 
| [Name](Public.Users.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The full name of the user 
| [PhoneNumber](Public.Users.md#phonenumber) | string (64) __nullable__ | Used only for two-factor authentication. NULL when phone-based two-factor is not used. 
| [UserId](Public.Users.md#userid) | guid | The Id of the security user. `Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Domain](Public.Users.md#domain) | [Domains](Systems.Security.Domains.md) (nullable) | The domain, to which the user belongs. |
| [Person](Public.Users.md#person) | [Persons](General.Contacts.Persons.md) (nullable) | The person from within the system, which is authenticated with this login. NULL means that this user is not associated with a person record in the database. |


## Attribute Details

### Email

Unique email of the user. Can be NULL because there may be login providers that don't use emails.

Type: **string (254) __nullable__**  
Category: **System**  
Inherited From: **Sec_Users_Table.Email**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### IsAdmin

1 if the user is administrator, otherwise 0.

Type: **boolean**  
Category: **System**  
Inherited From: **Sec_Users_Table.Is_Admin**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Login

The login name of the user, which is usually the email

Type: **string (64)**  
Category: **System**  
Inherited From: **Sec_Users_Table.Login**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Name

The full name of the user

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Inherited From: **Sec_Users_Table.User_Name**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PhoneNumber

Used only for two-factor authentication. NULL when phone-based two-factor is not used.

Type: **string (64) __nullable__**  
Category: **System**  
Inherited From: **Sec_Users_Table.Phone_Number**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### UserId

The Id of the security user. `Required` `Filter(multi eq)`

Type: **guid**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## Reference Details

### Domain

The domain, to which the user belongs.

Type: **[Domains](Systems.Security.Domains.md) (nullable)**  
Category: **System**  
Inherited From: **Sec_Users_Table.Domain_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Person

The person from within the system, which is authenticated with this login. NULL means that this user is not associated with a person record in the database.

Type: **[Persons](General.Contacts.Persons.md) (nullable)**  
Category: **System**  
Inherited From: **Sec_Users_Table.Person_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAccessKeyPermissions

Gets the permissions this user has to access resources protected by the provided access key.  
Return Type: **[SecurityPermissions](../data-types.md#systems.security.securitypermissions)**  
Declaring Type: **[Users](Public.Users.md)**  
Domain API Request: **POST**  

**Parameters**  
  * **accessKeyId**  
    The access key id  
    Type: guid  

  * **userToken**  
                 A proof token, identifying the logged in user. E.g. It could be an id token, or an access token.             Required when the currently logged user is different from the public user.               
    Type: string  
     Optional: True  
    Default Value: null  


## API

Domain API Entity Set: 
Public_Users

Domain API Entity Type: 
Public_User

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Public_Users?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Public_Users?$top=10>

