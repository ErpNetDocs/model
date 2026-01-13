---
uid: Systems.Security.TrustedApplicationAuthorizations
---
# Systems.Security.TrustedApplicationAuthorizations Entity

**Namespace:** [Systems.Security](Systems.Security.md)  

Authorization of a trusted application to access the data on behalf of a context user. Entity: Sec_Trusted_Application_Authorizations (Introduced in version 20.1)

## Default Visualization
Default Display Text Format:  
_{TrustedApplication.Name}_  
Default Search Members:  
_TrustedApplication.Name_  
Name Data Member:  
_TrustedApplication.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Security.TrustedApplications](Systems.Security.TrustedApplications.md)  
Aggregate Root:  
[Systems.Security.TrustedApplications](Systems.Security.TrustedApplications.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Security.TrustedApplicationAuthorizations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [GrantTimeUtc](Systems.Security.TrustedApplicationAuthorizations.md#granttimeutc) | datetime | The time (in UTC) when the authorization was granted. `Required` `Default(NowUtc)` `Filter(ge;le)` 
| [Id](Systems.Security.TrustedApplicationAuthorizations.md#id) | guid |  
| [IsRevoked](Systems.Security.TrustedApplicationAuthorizations.md#isrevoked) | boolean | Specifies whether the grant is explicitly revoked. `Required` `Default(false)` 
| [Notes](Systems.Security.TrustedApplicationAuthorizations.md#notes) | string (max) __nullable__ | Notes for this TrustedApplication<br />Authorization. 
| [ObjectVersion](Systems.Security.TrustedApplicationAuthorizations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ValidFromUtc](Systems.Security.TrustedApplicationAuthorizations.md#validfromutc) | datetime __nullable__ | The start of the validitiy of the authorization. null means that there is no restriction. `Filter(ge;le)` 
| [ValidUntilUtc](Systems.Security.TrustedApplicationAuthorizations.md#validuntilutc) | datetime __nullable__ | The time (in UTC) when the grant expires. null means that there is no time restriction. `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ContextUser](Systems.Security.TrustedApplicationAuthorizations.md#contextuser) | [Users](Systems.Security.Users.md) | The user, whose permissions are granted to the application. `Required` `Filter(multi eq)` |
| [GrantingUser](Systems.Security.TrustedApplicationAuthorizations.md#grantinguser) | [Users](Systems.Security.Users.md) | The user, who authorized the application. `Required` `Filter(multi eq)` |
| [TrustedApplication](Systems.Security.TrustedApplicationAuthorizations.md#trustedapplication) | [TrustedApplications](Systems.Security.TrustedApplications.md) | The application, which is authorized. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### GrantTimeUtc

The time (in UTC) when the authorization was granted. `Required` `Default(NowUtc)` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### IsRevoked

Specifies whether the grant is explicitly revoked. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this TrustedApplicationAuthorization.

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

### ValidFromUtc

The start of the validitiy of the authorization. null means that there is no restriction. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ValidUntilUtc

The time (in UTC) when the grant expires. null means that there is no time restriction. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### ContextUser

The user, whose permissions are granted to the application. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### GrantingUser

The user, who authorized the application. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### TrustedApplication

The application, which is authorized. `Required` `Filter(multi eq)` `Owner`

_Type_: **[TrustedApplications](Systems.Security.TrustedApplications.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

