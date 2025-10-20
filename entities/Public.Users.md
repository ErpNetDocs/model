---
uid: Public.Users
---
# Public.Users View

**Namespace:** [Public](Public.md)  

Public users profile data. Entity: Public_Users (Introduced in version 22.1.4.22)

## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Category:  _Views_  
Show in UI:  _CannotBeShown_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Public.Users](Public.Users.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Email](Public.Users.md#email) | string (254) __nullable__ | Unique email of the user. Can be null because there may be login providers that don't use emails. `Filter(multi eq;like)` `Inherited from Sec_Users_Table.Email` 
| [IsAdmin](Public.Users.md#isadmin) | boolean | True if the user is administrator, otherwise 0. `Required` `Default(false)` `Filter(eq)` `Inherited from Sec_Users_Table.Is_Admin` 
| [Login](Public.Users.md#login) | string (64) | The login name of the user, which is usually the email. `Required` `Filter(multi eq;like)` `Inherited from Sec_Users_Table.Login` 
| [Name](Public.Users.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The full name of the user. `Required` `Filter(like)` `Inherited from Sec_Users_Table.User_Name` 
| [PhoneNumber](Public.Users.md#phonenumber) | string (64) __nullable__ | Used only for two-factor authentication. null when phone-based two-factor is not used. `Filter(eq;like)` `Inherited from Sec_Users_Table.Phone_Number` 
| [UserId](Public.Users.md#userid) | guid | The Id of the security user. `Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Domain](Public.Users.md#domain) | [Domains](Systems.Security.Domains.md) (nullable) | The domain, to which the user belongs. `Filter(multi eq)` `Inherited from Sec_Users_Table.Domain_Id` |
| [Person](Public.Users.md#person) | [Persons](General.Contacts.Persons.md) (nullable) | The person from within the system, which is authenticated with this login. null means that this user is not associated with a person record in the database. `Filter(multi eq)` `Inherited from Sec_Users_Table.Person_Id` |


## Attribute Details

### Email

Unique email of the user. Can be null because there may be login providers that don't use emails. `Filter(multi eq;like)` `Inherited from Sec_Users_Table.Email`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Inherited From_: **Sec_Users_Table.Email**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### IsAdmin

True if the user is administrator, otherwise 0. `Required` `Default(false)` `Filter(eq)` `Inherited from Sec_Users_Table.Is_Admin`

_Type_: **boolean**  
_Category_: **System**  
_Inherited From_: **Sec_Users_Table.Is_Admin**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Login

The login name of the user, which is usually the email. `Required` `Filter(multi eq;like)` `Inherited from Sec_Users_Table.Login`

_Type_: **string (64)**  
_Category_: **System**  
_Inherited From_: **Sec_Users_Table.Login**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Name

The full name of the user. `Required` `Filter(like)` `Inherited from Sec_Users_Table.User_Name`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Inherited From_: **Sec_Users_Table.User_Name**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### PhoneNumber

Used only for two-factor authentication. null when phone-based two-factor is not used. `Filter(eq;like)` `Inherited from Sec_Users_Table.Phone_Number`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Inherited From_: **Sec_Users_Table.Phone_Number**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### UserId

The Id of the security user. `Required` `Filter(multi eq)`

_Type_: **guid**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Domain

The domain, to which the user belongs. `Filter(multi eq)` `Inherited from Sec_Users_Table.Domain_Id`

_Type_: **[Domains](Systems.Security.Domains.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Sec_Users_Table.Domain_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Person

The person from within the system, which is authenticated with this login. null means that this user is not associated with a person record in the database. `Filter(multi eq)` `Inherited from Sec_Users_Table.Person_Id`

_Type_: **[Persons](General.Contacts.Persons.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Sec_Users_Table.Person_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAccessKeyPermissions

Gets the permissions this user has to access resources protected by the provided access key.  
_Return Type_: **[SecurityPermissions](../data-types.md#systems.security.securitypermissions)**  
_Declaring Type_: **[Users](Public.Users.md)**  
_Domain API Request_: **POST**  

**Parameters**  
  * **accessKeyId**  
    The access key id  
    _Type_: guid  

  * **userToken**  
                 A proof token, identifying the logged in user. E.g. It could be an id token, or an access token.             Required when the currently logged user is different from the public user.               
    _Type_: string  
     _Optional_: True  
    _Default Value_: null  


## API

Domain API Entity Set:
Public_Users

Domain API Entity Type:
Public_User

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Public_Users?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Public_Users?$top=10>

