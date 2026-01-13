---
uid: Systems.Security.UserProviderLogins
---
# Systems.Security.UserProviderLogins Entity

**Namespace:** [Systems.Security](Systems.Security.md)  

External login providers. Entity: Sec_User_Provider_Logins (Introduced in version 18.2)

## Default Visualization
Default Display Text Format:  
_{User.Name:T}_  
Default Search Members:  
_User.Name_  
Name Data Member:  
_User.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Security.Users](Systems.Security.Users.md)  
Aggregate Root:  
[Systems.Security.Users](Systems.Security.Users.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Security.UserProviderLogins.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Security.UserProviderLogins.md#id) | guid |  
| [ObjectVersion](Systems.Security.UserProviderLogins.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProviderKey](Systems.Security.UserProviderLogins.md#providerkey) | string (450) | The key, which the provider provided for logging the user. `Required` `Filter(multi eq)` 
| [ProviderName](Systems.Security.UserProviderLogins.md#providername) | [ProviderName](Systems.Security.UserProviderLogins.md#providername) | The system name of the authentication provider. It should be already registered for the domain. `Required` `Filter(eq)` `Introduced in version 20.1` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [User](Systems.Security.UserProviderLogins.md#user) | [Users](Systems.Security.Users.md) | The user for which the login is defined. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ProviderKey

The key, which the provider provided for logging the user. `Required` `Filter(multi eq)`

_Type_: **string (450)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **450**  
_Show in UI_: **ShownByDefault**  

### ProviderName

The system name of the authentication provider. It should be already registered for the domain. `Required` `Filter(eq)` `Introduced in version 20.1`

_Type_: **[ProviderName](Systems.Security.UserProviderLogins.md#providername)**  
_Category_: **System**  
Allowed values for the `ProviderName`(Systems.Security.DomainProviders.md#providername) data attribute  
_Allowed Values (Systems.Security.DomainProvidersRepository.ProviderName Enum Members)_  

| Value | Description |
| ---- | --- |
| ERPNET | ERPNET value. Stored as 'ERPNET'. <br /> _Database Value:_ 'ERPNET' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'ERPNET' |
| AZUREAD | AZUREAD value. Stored as 'AZUREAD'. <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'AZUREAD' |
| GOOGLE | GOOGLE value. Stored as 'GOOGLE'. <br /> _Database Value:_ 'GOOGLE' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'GOOGLE' |
| FACEBOOK | FACEBOOK value. Stored as 'FACEBOOK'. <br /> _Database Value:_ 'FACEBOOK' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'FACEBOOK' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### User

The user for which the login is defined. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Users](Systems.Security.Users.md)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Systems.Security.UserProviderLogins erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.UserProviderLogins erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_UserProviderLogins

Domain API Entity Type: 
Systems_Security_UserProviderLogin

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_UserProviderLogins?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_UserProviderLogins?$top=10>

