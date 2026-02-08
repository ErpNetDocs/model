---
uid: Systems.Security.AccessTokens
---
# Systems.Security.AccessTokens


It keeps track of "grants" issued by Identity Server - Personal Access Tokens (PATs), refresh tokens, device codes, and consents.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.AccessTokens  
Base Table: Sec_Access_Tokens  
Introduced In Version: 26.2.0.13  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {AccessTokenKey}  
Search Members:   
Category:  SystemData  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Security.AccessTokens](Systems.Security.AccessTokens.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessTokenKey](Systems.Security.AccessTokens.md#accesstokenkey) | string (256) | The unique key of the token`Required` `Filter(multi eq)` `ORD` 
| [Actor](Systems.Security.AccessTokens.md#actor) | string (128) __nullable__ | For whom the token was issued (might be user email)`Filter(multi eq)` 
| [Client](Systems.Security.AccessTokens.md#client) | string (128) __nullable__ | The client application`Filter(multi eq)` 
| [ConsumedTimestamp](Systems.Security.AccessTokens.md#consumedtimestamp) | datetime __nullable__ | When it was used up (for one-time grants).`Filter(ge;le)` 
| [CreationTimestamp](Systems.Security.AccessTokens.md#creationtimestamp) | datetime | When the token was created`Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` 
| [Data](Systems.Security.AccessTokens.md#data) | string (max) __nullable__ | Token contents 
| [Description](Systems.Security.AccessTokens.md#description) | string (128) __nullable__ | The description of this AccessToken. 
| [ExpireTimestamp](Systems.Security.AccessTokens.md#expiretimestamp) | datetime __nullable__ | When the token expires`Filter(ge;le)` 
| [LastUsedTimestamp](Systems.Security.AccessTokens.md#lastusedtimestamp) | datetime __nullable__ | Indicates when the token was last used.`Filter(ge;le)` `Introduced in version 26.2.0.18` 
| [Scopes](Systems.Security.AccessTokens.md#scopes) | string (256) __nullable__ | Space-separated list of permissions granted to this token.`Introduced in version 26.2.0.18` 
| [Session](Systems.Security.AccessTokens.md#session) | string (128) __nullable__ | Session parameter`Filter(multi eq)` 
| [Type](Systems.Security.AccessTokens.md#type) | string (64) | Type of the token - reference_token, refresh_token, etc.`Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [TrustedApplication](Systems.Security.AccessTokens.md#trustedapplication) | [TrustedApplications](Systems.Security.TrustedApplications.md) (nullable) | Sec_Trusted_Applications // Matched trusted application (from Client) |
| [User](Systems.Security.AccessTokens.md#user) | [Users](Systems.Security.Users.md) (nullable) | Matched user (from the actor) |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.AccessTokens.md#id) | guid |  
| [ObjectVersion](Systems.Security.AccessTokens.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Security.AccessTokens.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Security.AccessTokens.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Security.AccessTokens.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Security.AccessTokens.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AccessTokenKey

The unique key of the token`Required` `Filter(multi eq)` `ORD`

Type: **string (256)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### Actor

For whom the token was issued (might be user email)`Filter(multi eq)`

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### Client

The client application`Filter(multi eq)`

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### ConsumedTimestamp

When it was used up (for one-time grants).`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreationTimestamp

When the token was created`Required` `Default(NowUtc)` `Filter(ge;le)` `ORD`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### Data

Token contents

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Description

The description of this AccessToken.

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### ExpireTimestamp

When the token expires`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LastUsedTimestamp

Indicates when the token was last used.`Filter(ge;le)` `Introduced in version 26.2.0.18`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Scopes

Space-separated list of permissions granted to this token.`Introduced in version 26.2.0.18`

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### Session

Session parameter`Filter(multi eq)`

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### Type

Type of the token - reference_token, refresh_token, etc.`Required`

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

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

### TrustedApplication

Sec_Trusted_Applications // Matched trusted application (from Client)

Type: **[TrustedApplications](Systems.Security.TrustedApplications.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### User

Matched user (from the actor)

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Indexed: **True**  
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

