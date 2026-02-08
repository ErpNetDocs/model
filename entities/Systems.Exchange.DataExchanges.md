---
uid: Systems.Exchange.DataExchanges
---
# Systems.Exchange.DataExchanges


Denotes a data exchange (import, export, etc.) operation with detailed info about objects, transfer status and more.

## General
Namespace: [Systems.Exchange](Systems.Exchange.md)  
Repository: Systems.Exchange.DataExchanges  
Base Table: Sys_Data_Exchanges  
Introduced In Version: 25.1.1.70  
API access:  ReadWrite  

## Visualization
Display Format: {Name}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Exchange.DataExchanges](Systems.Exchange.DataExchanges.md)  
  * [Systems.Exchange.DataExchangeObjects](Systems.Exchange.DataExchangeObjects.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreatedOn](Systems.Exchange.DataExchanges.md#createdon) | datetime | The time when the exchange is created.`Required` `Filter(ge;le)` `ReadOnly` 
| [DriverName](Systems.Exchange.DataExchanges.md#drivername) | string (64) __nullable__ | The name of the exchange program/procedure, which actuates the exchange operation.`Default(&quot;JSON_FILE&quot;)` `Filter(eq)` 
| [ExchangedOn](Systems.Exchange.DataExchanges.md#exchangedon) | datetime __nullable__ | The time (in UTC) of the exchange.`Filter(ge;le)` 
| [ExchangeLog](Systems.Exchange.DataExchanges.md#exchangelog) | string (max) __nullable__ | General log of the last transfer attempt. Messages for the individual objects are kept with the objects.`Filter(like)` 
| [ExternalAddress](Systems.Exchange.DataExchanges.md#externaladdress) | string (254) __nullable__ | Address of the external resource from/to which the date is transferred. The value is dependent on the exchange driver.`Filter(like)` 
| [KeepUntil](Systems.Exchange.DataExchanges.md#keepuntil) | date | Specify the date until which this package info will be kept. After the date, the package will be automatically purged (deleted).`Required` `Filter(ge;le)` 
| [Mode](Systems.Exchange.DataExchanges.md#mode) | [Mode](Systems.Exchange.DataExchanges.md#mode) | Operation mode of the exchange.`Required` `Default(&quot;E&quot;)` `Filter(eq)` 
| [Name](Systems.Exchange.DataExchanges.md#name) | string (64) __nullable__ | The name of the package. Can be empty if naming is not important.`Filter(eq;like)` 
| [Notes](Systems.Exchange.DataExchanges.md#notes) | string (max) __nullable__ | Notes for the exchange.`Filter(like)` 
| [State](Systems.Exchange.DataExchanges.md#state) | [State](Systems.Exchange.DataExchanges.md#state) | State of the exchange.`Required` `Default(&quot;PRE&quot;)` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreatedByUser](Systems.Exchange.DataExchanges.md#createdbyuser) | [Users](Systems.Security.Users.md) | The user who created the exchange. |
| [ExchangedByUser](Systems.Exchange.DataExchanges.md#exchangedbyuser) | [Users](Systems.Security.Users.md) (nullable) | The user who made the exchange. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Exchange.DataExchanges.md#id) | guid |  
| [ObjectVersion](Systems.Exchange.DataExchanges.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Exchange.DataExchanges.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Exchange.DataExchanges.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Exchange.DataExchanges.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Exchange.DataExchanges.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Objects | [DataExchangeObjects](Systems.Exchange.DataExchangeObjects.md) | List of `DataExchangeObject`(Systems.Exchange.DataExchangeObjects.md) child objects, based on the `Systems.Exchange.DataExchangeObject.DataExchange`(Systems.Exchange.DataExchangeObjects.md#dataexchange) back reference 


## Attribute Details

### CreatedOn

The time when the exchange is created.`Required` `Filter(ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`DateTime.UtcNow`

### DriverName

The name of the exchange program/procedure, which actuates the exchange operation.`Default(&quot;JSON_FILE&quot;)` `Filter(eq)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Default Value: **JSON_FILE**  
Show in UI: **ShownByDefault**  

### ExchangedOn

The time (in UTC) of the exchange.`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExchangeLog

General log of the last transfer attempt. Messages for the individual objects are kept with the objects.`Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ExternalAddress

Address of the external resource from/to which the date is transferred. The value is dependent on the exchange driver.`Filter(like)`

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### KeepUntil

Specify the date until which this package info will be kept. After the date, the package will be automatically purged (deleted).`Required` `Filter(ge;le)`

Type: **date**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`DateTime.Now.AddMonths( 3).Date`

### Mode

Operation mode of the exchange.`Required` `Default(&quot;E&quot;)` `Filter(eq)`

Type: **[Mode](Systems.Exchange.DataExchanges.md#mode)**  
Category: **System**  
Allowed values for the `Mode`(Systems.Exchange.DataExchanges.md#mode) data attribute  
Allowed Values (Systems.Exchange.DataExchangesRepository.Mode Enum Members)  

| Value | Description |
| ---- | --- |
| Export | Export. Stored as 'E'. <br /> Database Value: 'E' <br /> Model Value: 0 <br /> Domain API Value: 'Export' |
| Import | Import. Stored as 'I'. <br /> Database Value: 'I' <br /> Model Value: 1 <br /> Domain API Value: 'Import' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Export**  
Show in UI: **ShownByDefault**  

### Name

The name of the package. Can be empty if naming is not important.`Filter(eq;like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Notes

Notes for the exchange.`Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### State

State of the exchange.`Required` `Default(&quot;PRE&quot;)` `Filter(eq)`

Type: **[State](Systems.Exchange.DataExchanges.md#state)**  
Category: **System**  
Allowed values for the `State`(Systems.Exchange.DataExchanges.md#state) data attribute  
Allowed Values (Systems.Exchange.DataExchangesRepository.State Enum Members)  

| Value | Description |
| ---- | --- |
| Prepare | Prepare. Stored as 'PRE'. <br /> Database Value: 'PRE' <br /> Model Value: 0 <br /> Domain API Value: 'Prepare' |
| Ready | Ready. Stored as 'RED'. <br /> Database Value: 'RED' <br /> Model Value: 1 <br /> Domain API Value: 'Ready' |
| FinishedSuccess | Finished Success. Stored as 'FSC'. <br /> Database Value: 'FSC' <br /> Model Value: 2 <br /> Domain API Value: 'FinishedSuccess' |
| FinishedFail | Finished Fail. Stored as 'FFL'. <br /> Database Value: 'FFL' <br /> Model Value: 3 <br /> Domain API Value: 'FinishedFail' |
| ClosedSuccess | Closed Success. Stored as 'CSC'. <br /> Database Value: 'CSC' <br /> Model Value: 4 <br /> Domain API Value: 'ClosedSuccess' |
| ClosedFail | Closed Fail. Stored as 'CFL'. <br /> Database Value: 'CFL' <br /> Model Value: 5 <br /> Domain API Value: 'ClosedFail' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Prepare**  
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

### CreatedByUser

The user who created the exchange.

Type: **[Users](Systems.Security.Users.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.Transaction.CurrentUser.ToSecurityUser( )`

### ExchangedByUser

The user who made the exchange.

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

[!list limit=1000 erp.entity=Systems.Exchange.DataExchanges erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Exchange.DataExchanges erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Exchange_DataExchanges

Domain API Entity Type: 
Systems_Exchange_DataExchange

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Exchange_DataExchanges?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Exchange_DataExchanges?$top=10>

