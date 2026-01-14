---
uid: Systems.Security.AccessTokens
---
# Systems.Security.AccessTokens Entity

**Namespace:** [Systems.Security](Systems.Security.md)  

It keeps track of "grants" issued by Identity Server - Personal Access Tokens (PATs), refresh tokens, device codes, and consents. Entity: Sec_Access_Tokens (Introduced in version 26.2.0.13)

## Default Visualization
Default Display Text Format:  
_{Id}: {AccessTokenKey}_  
Default Search Members:  
__  
Category:  _SystemData_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Security.AccessTokens](Systems.Security.AccessTokens.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessTokenKey](Systems.Security.AccessTokens.md#accesstokenkey) | string (256) | The unique key of the token. `Required` `Filter(multi eq)` `ORD` 
| [Actor](Systems.Security.AccessTokens.md#actor) | string (128) __nullable__ | For whom the token was issued (might be user email). `Filter(multi eq)` 
| [AggregateLastUpdateTimeUtc](Systems.Security.AccessTokens.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [Client](Systems.Security.AccessTokens.md#client) | string (128) __nullable__ | The client application. `Filter(multi eq)` 
| [ConsumedTimestamp](Systems.Security.AccessTokens.md#consumedtimestamp) | datetime __nullable__ | When it was used up (for one-time grants). `Filter(ge;le)` 
| [CreationTimestamp](Systems.Security.AccessTokens.md#creationtimestamp) | datetime | When the token was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` 
| [Data](Systems.Security.AccessTokens.md#data) | string (max) __nullable__ | Token contents. 
| [Description](Systems.Security.AccessTokens.md#description) | string (128) __nullable__ | The description of this AccessToken. 
| [DisplayText](Systems.Security.AccessTokens.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExpireTimestamp](Systems.Security.AccessTokens.md#expiretimestamp) | datetime __nullable__ | When the token expires. `Filter(ge;le)` 
| [ExternalId](Systems.Security.AccessTokens.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Security.AccessTokens.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Security.AccessTokens.md#id) | guid |  
| [LastUsedTimestamp](Systems.Security.AccessTokens.md#lastusedtimestamp) | datetime __nullable__ | Indicates when the token was last used. `Filter(ge;le)` `Introduced in version 26.2.0.18` 
| [ObjectVersion](Systems.Security.AccessTokens.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Scopes](Systems.Security.AccessTokens.md#scopes) | string (256) __nullable__ | Space-separated list of permissions granted to this token. `Introduced in version 26.2.0.18` 
| [Session](Systems.Security.AccessTokens.md#session) | string (128) __nullable__ | Session parameter. `Filter(multi eq)` 
| [Type](Systems.Security.AccessTokens.md#type) | string (64) | Type of the token - reference_token, refresh_token, etc. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [TrustedApplication](Systems.Security.AccessTokens.md#trustedapplication) | [TrustedApplications](Systems.Security.TrustedApplications.md) (nullable) | Sec_Trusted_Applications // Matched trusted application (from Client). `Filter(multi eq)` |
| [User](Systems.Security.AccessTokens.md#user) | [Users](Systems.Security.Users.md) (nullable) | Matched user (from the actor). `Filter(multi eq)` |


## Attribute Details

### AccessTokenKey

The unique key of the token. `Required` `Filter(multi eq)` `ORD`

_Type_: **string (256)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### Actor

For whom the token was issued (might be user email). `Filter(multi eq)`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

### Client

The client application. `Filter(multi eq)`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### ConsumedTimestamp

When it was used up (for one-time grants). `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CreationTimestamp

When the token was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### Data

Token contents.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### Description

The description of this AccessToken.

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExpireTimestamp

When the token expires. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
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
_Show in UI_: **ShownByDefault**  

### LastUsedTimestamp

Indicates when the token was last used. `Filter(ge;le)` `Introduced in version 26.2.0.18`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Scopes

Space-separated list of permissions granted to this token. `Introduced in version 26.2.0.18`

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### Session

Session parameter. `Filter(multi eq)`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### Type

Type of the token - reference_token, refresh_token, etc. `Required`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### TrustedApplication

Sec_Trusted_Applications // Matched trusted application (from Client). `Filter(multi eq)`

_Type_: **[TrustedApplications](Systems.Security.TrustedApplications.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### User

Matched user (from the actor). `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Systems.Security.AccessTokens erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.AccessTokens erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_AccessTokens

Domain API Entity Type: 
Systems_Security_AccessToken

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_AccessTokens?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_AccessTokens?$top=10>

