---
uid: Systems.Exchange.DataExchangeObjects
---
# Systems.Exchange.DataExchangeObjects Entity

**Namespace:** [Systems.Exchange](Systems.Exchange.md)  

Individual aggregate root objects transferred within the data exchange. Only aggregate root objects can be specified; sub-entities are specified as addresses within the root objects. Entity: Sys_Data_Exchange_Objects (Introduced in version 25.1.1.70)

## Default Visualization
Default Display Text Format:  
_{DataExchange.Name}_  
Default Search Members:  
_DataExchange.Name_  
Name Data Member:  
_DataExchange.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Exchange.DataExchanges](Systems.Exchange.DataExchanges.md)  
Aggregate Root:  
[Systems.Exchange.DataExchanges](Systems.Exchange.DataExchanges.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreatedOn](Systems.Exchange.DataExchangeObjects.md#createdon) | datetime | The time (in UTC) when the object is created. `Required` `Filter(ge;le)` `ReadOnly` 
| [DisplayText](Systems.Exchange.DataExchangeObjects.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExchangeMessage](Systems.Exchange.DataExchangeObjects.md#exchangemessage) | string (max) __nullable__ | Status message for this object after the last exchange attempt. `Filter(like)` 
| [ExchangeResult](Systems.Exchange.DataExchangeObjects.md#exchangeresult) | [ExchangeResult](Systems.Exchange.DataExchangeObjects.md#exchangeresult) | Transfer status. `Required` `Default("N")` `Filter(eq)` 
| [Id](Systems.Exchange.DataExchangeObjects.md#id) | guid |  
| [Mode](Systems.Exchange.DataExchangeObjects.md#mode) | [Mode](Systems.Exchange.DataExchangeObjects.md#mode) | Operation mode for the object when transferring. `Required` `Default("MER")` `Filter(eq)` 
| [Notes](Systems.Exchange.DataExchangeObjects.md#notes) | string (max) __nullable__ | Notes for the exchanged object. `Filter(like)` 
| [ObjectVersion](Systems.Exchange.DataExchangeObjects.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Reason](Systems.Exchange.DataExchangeObjects.md#reason) | [Reason](Systems.Exchange.DataExchangeObjects.md#reason) | Reason for adding the object. `Required` `Default("C")` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataExchange](Systems.Exchange.DataExchangeObjects.md#dataexchange) | [DataExchanges](Systems.Exchange.DataExchanges.md) | The exchange of the object. `Required` `Filter(multi eq)` `Owner` |
| [DataObject](Systems.Exchange.DataExchangeObjects.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The data object which will be transferred. `Required` `Filter(multi eq)` |


## Attribute Details

### CreatedOn

The time (in UTC) when the object is created. `Required` `Filter(ge;le)` `ReadOnly`

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

### ExchangeMessage

Status message for this object after the last exchange attempt. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ExchangeResult

Transfer status. `Required` `Default("N")` `Filter(eq)`

_Type_: **[ExchangeResult](Systems.Exchange.DataExchangeObjects.md#exchangeresult)**  
_Category_: **System**  
Allowed values for the `ExchangeResult`(Systems.Exchange.DataExchangeObjects.md#exchangeresult) data attribute  
_Allowed Values (Systems.Exchange.DataExchangeObjectsRepository.ExchangeResult Enum Members)_  

| Value | Description |
| ---- | --- |
| NotStarted | Not started. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NotStarted' |
| Success | Success. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Success' |
| Fail | Fail. Stored as 'F'. <br /> _Database Value:_ 'F' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Fail' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **NotStarted**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Mode

Operation mode for the object when transferring. `Required` `Default("MER")` `Filter(eq)`

_Type_: **[Mode](Systems.Exchange.DataExchangeObjects.md#mode)**  
_Category_: **System**  
Allowed values for the `Mode`(Systems.Exchange.DataExchangeObjects.md#mode) data attribute  
_Allowed Values (Systems.Exchange.DataExchangeObjectsRepository.Mode Enum Members)_  

| Value | Description |
| ---- | --- |
| Merge | Merge. Stored as 'MER'. <br /> _Database Value:_ 'MER' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Merge' |
| Add | Add. Stored as 'ADD'. <br /> _Database Value:_ 'ADD' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Add' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Merge**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for the exchanged object. `Filter(like)`

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

### Reason

Reason for adding the object. `Required` `Default("C")` `Filter(eq)`

_Type_: **[Reason](Systems.Exchange.DataExchangeObjects.md#reason)**  
_Category_: **System**  
Allowed values for the `Reason`(Systems.Exchange.DataExchangeObjects.md#reason) data attribute  
_Allowed Values (Systems.Exchange.DataExchangeObjectsRepository.Reason Enum Members)_  

| Value | Description |
| ---- | --- |
| CoreData | Core data. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'CoreData' |
| ByReference | By Reference. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ByReference' |
| Other | Other. Stored as 'O'. <br /> _Database Value:_ 'O' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Other' |
| Unknown | Unknown. Stored as 'U'. <br /> _Database Value:_ 'U' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Unknown' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **CoreData**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DataExchange

The exchange of the object. `Required` `Filter(multi eq)` `Owner`

_Type_: **[DataExchanges](Systems.Exchange.DataExchanges.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### DataObject

The data object which will be transferred. `Required` `Filter(multi eq)`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
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

[!list limit=1000 erp.entity=Systems.Exchange.DataExchangeObjects erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Exchange.DataExchangeObjects erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Exchange_DataExchangeObjects

Domain API Entity Type: 
Systems_Exchange_DataExchangeObject

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Exchange_DataExchangeObjects?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Exchange_DataExchangeObjects?$top=10>

