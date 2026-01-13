---
uid: Systems.Exchange.DataExchanges
---
# Systems.Exchange.DataExchanges Entity

**Namespace:** [Systems.Exchange](Systems.Exchange.md)  

Denotes a data exchange (import, export, etc.) operation with detailed info about objects, transfer status and more. Entity: Sys_Data_Exchanges (Introduced in version 25.1.1.70)

## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Exchange.DataExchanges](Systems.Exchange.DataExchanges.md)  
  * [Systems.Exchange.DataExchangeObjects](Systems.Exchange.DataExchangeObjects.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreatedOn](Systems.Exchange.DataExchanges.md#createdon) | datetime | The time (in UTC) when the exchange is created. `Required` `Filter(ge;le)` `ReadOnly` 
| [DisplayText](Systems.Exchange.DataExchanges.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DriverName](Systems.Exchange.DataExchanges.md#drivername) | string (64) __nullable__ | The name of the exchange program/procedure, which actuates the exchange operation. `Default("JSON_FILE")` `Filter(eq)` 
| [ExchangedOn](Systems.Exchange.DataExchanges.md#exchangedon) | datetime __nullable__ | The time (in UTC) of the exchange. `Filter(ge;le)` 
| [ExchangeLog](Systems.Exchange.DataExchanges.md#exchangelog) | string (max) __nullable__ | General log of the last transfer attempt. Messages for the individual objects are kept with the objects. `Filter(like)` 
| [ExternalAddress](Systems.Exchange.DataExchanges.md#externaladdress) | string (254) __nullable__ | Address of the external resource from/to which the date is transferred. The value is dependent on the exchange driver. `Filter(like)` 
| [ExternalId](Systems.Exchange.DataExchanges.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Exchange.DataExchanges.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Exchange.DataExchanges.md#id) | guid |  
| [KeepUntil](Systems.Exchange.DataExchanges.md#keepuntil) | date | Specify the date until which this package info will be kept. After the date, the package will be automatically purged (deleted). `Required` `Filter(ge;le)` 
| [Mode](Systems.Exchange.DataExchanges.md#mode) | [Mode](Systems.Exchange.DataExchanges.md#mode) | Operation mode of the exchange. `Required` `Default("E")` `Filter(eq)` 
| [Name](Systems.Exchange.DataExchanges.md#name) | string (64) __nullable__ | The name of the package. Can be empty if naming is not important. `Filter(eq;like)` 
| [Notes](Systems.Exchange.DataExchanges.md#notes) | string (max) __nullable__ | Notes for the exchange. `Filter(like)` 
| [ObjectVersion](Systems.Exchange.DataExchanges.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [State](Systems.Exchange.DataExchanges.md#state) | [State](Systems.Exchange.DataExchanges.md#state) | State of the exchange. `Required` `Default("PRE")` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreatedByUser](Systems.Exchange.DataExchanges.md#createdbyuser) | [Users](Systems.Security.Users.md) | The user who created the exchange. `Required` `Filter(multi eq)` `ReadOnly` |
| [ExchangedByUser](Systems.Exchange.DataExchanges.md#exchangedbyuser) | [Users](Systems.Security.Users.md) (nullable) | The user who made the exchange. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Objects | [DataExchangeObjects](Systems.Exchange.DataExchangeObjects.md) | List of `DataExchangeObject`(Systems.Exchange.DataExchangeObjects.md) child objects, based on the `Systems.Exchange.DataExchangeObject.DataExchange`(Systems.Exchange.DataExchangeObjects.md#dataexchange) back reference 


## Attribute Details

### CreatedOn

The time (in UTC) when the exchange is created. `Required` `Filter(ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`DateTime.UtcNow`

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DriverName

The name of the exchange program/procedure, which actuates the exchange operation. `Default("JSON_FILE")` `Filter(eq)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Default Value_: **JSON_FILE**  
_Show in UI_: **ShownByDefault**  

### ExchangedOn

The time (in UTC) of the exchange. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ExchangeLog

General log of the last transfer attempt. Messages for the individual objects are kept with the objects. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ExternalAddress

Address of the external resource from/to which the date is transferred. The value is dependent on the exchange driver. `Filter(like)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
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

### KeepUntil

Specify the date until which this package info will be kept. After the date, the package will be automatically purged (deleted). `Required` `Filter(ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`DateTime.Now.AddMonths( 3).Date`

### Mode

Operation mode of the exchange. `Required` `Default("E")` `Filter(eq)`

_Type_: **[Mode](Systems.Exchange.DataExchanges.md#mode)**  
_Category_: **System**  
Allowed values for the `Mode`(Systems.Exchange.DataExchanges.md#mode) data attribute  
_Allowed Values (Systems.Exchange.DataExchangesRepository.Mode Enum Members)_  

| Value | Description |
| ---- | --- |
| Export | Export. Stored as 'E'. <br /> _Database Value:_ 'E' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Export' |
| Import | Import. Stored as 'I'. <br /> _Database Value:_ 'I' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Import' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Export**  
_Show in UI_: **ShownByDefault**  

### Name

The name of the package. Can be empty if naming is not important. `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for the exchange. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
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

### State

State of the exchange. `Required` `Default("PRE")` `Filter(eq)`

_Type_: **[State](Systems.Exchange.DataExchanges.md#state)**  
_Category_: **System**  
Allowed values for the `State`(Systems.Exchange.DataExchanges.md#state) data attribute  
_Allowed Values (Systems.Exchange.DataExchangesRepository.State Enum Members)_  

| Value | Description |
| ---- | --- |
| Prepare | Prepare. Stored as 'PRE'. <br /> _Database Value:_ 'PRE' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Prepare' |
| Ready | Ready. Stored as 'RED'. <br /> _Database Value:_ 'RED' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Ready' |
| FinishedSuccess | Finished Success. Stored as 'FSC'. <br /> _Database Value:_ 'FSC' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'FinishedSuccess' |
| FinishedFail | Finished Fail. Stored as 'FFL'. <br /> _Database Value:_ 'FFL' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'FinishedFail' |
| ClosedSuccess | Closed Success. Stored as 'CSC'. <br /> _Database Value:_ 'CSC' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'ClosedSuccess' |
| ClosedFail | Closed Fail. Stored as 'CFL'. <br /> _Database Value:_ 'CFL' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'ClosedFail' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Prepare**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CreatedByUser

The user who created the exchange. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Users](Systems.Security.Users.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.Transaction.CurrentUser.ToSecurityUser( )`

### ExchangedByUser

The user who made the exchange. `Filter(multi eq)`

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

