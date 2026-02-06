---
uid: Systems.Exchange.DataExchangeObjects
---
# Systems.Exchange.DataExchangeObjects


Individual aggregate root objects transferred within the data exchange. Only aggregate root objects can be specified; sub-entities are specified as addresses within the root objects.

## General
Namespace: [Systems.Exchange](Systems.Exchange.md)  
Repository: Systems.Exchange.DataExchangeObjects  
Base Table: Sys_Data_Exchange_Objects  
Introduced In Version: 25.1.1.70  
API access:  ReadWrite  

## Visualization
Display Format: {DataExchange.Name}  
Search Members: DataExchange.Name  
Name Member: DataExchange.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Exchange.DataExchanges](Systems.Exchange.DataExchanges.md)  
Aggregate Root:  
[Systems.Exchange.DataExchanges](Systems.Exchange.DataExchanges.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreatedOn](Systems.Exchange.DataExchangeObjects.md#createdon) | datetime | The time (in UTC) when the object is created.[Required] [Filter(ge;le)] [ReadOnly] 
| [ExchangeMessage](Systems.Exchange.DataExchangeObjects.md#exchangemessage) | string (max) __nullable__ | Status message for this object after the last exchange attempt.[Filter(like)] 
| [ExchangeResult](Systems.Exchange.DataExchangeObjects.md#exchangeresult) | [ExchangeResult](Systems.Exchange.DataExchangeObjects.md#exchangeresult) | Transfer status.[Required] [Default(&quot;N&quot;)] [Filter(eq)] 
| [Mode](Systems.Exchange.DataExchangeObjects.md#mode) | [Mode](Systems.Exchange.DataExchangeObjects.md#mode) | Operation mode for the object when transferring.[Required] [Default(&quot;MER&quot;)] [Filter(eq)] 
| [Notes](Systems.Exchange.DataExchangeObjects.md#notes) | string (max) __nullable__ | Notes for the exchanged object[Filter(like)] 
| [Reason](Systems.Exchange.DataExchangeObjects.md#reason) | [Reason](Systems.Exchange.DataExchangeObjects.md#reason) | Reason for adding the object.[Required] [Default(&quot;C&quot;)] [Filter(eq)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataExchange](Systems.Exchange.DataExchangeObjects.md#dataexchange) | [DataExchanges](Systems.Exchange.DataExchanges.md) | The exchange of the object. |
| [DataObject](Systems.Exchange.DataExchangeObjects.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The data object which will be transferred. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Exchange.DataExchangeObjects.md#id) | guid |  
| [ObjectVersion](Systems.Exchange.DataExchangeObjects.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Exchange.DataExchangeObjects.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CreatedOn

The time (in UTC) when the object is created.[Required] [Filter(ge;le)] [ReadOnly]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`DateTime.UtcNow`

### ExchangeMessage

Status message for this object after the last exchange attempt.[Filter(like)]

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ExchangeResult

Transfer status.[Required] [Default(&quot;N&quot;)] [Filter(eq)]

Type: **[ExchangeResult](Systems.Exchange.DataExchangeObjects.md#exchangeresult)**  
Category: **System**  
Allowed values for the `ExchangeResult`(Systems.Exchange.DataExchangeObjects.md#exchangeresult) data attribute  
Allowed Values (Systems.Exchange.DataExchangeObjectsRepository.ExchangeResult Enum Members)  

| Value | Description |
| ---- | --- |
| NotStarted | Not started. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 0 <br /> Domain API Value: 'NotStarted' |
| Success | Success. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 1 <br /> Domain API Value: 'Success' |
| Fail | Fail. Stored as 'F'. <br /> Database Value: 'F' <br /> Model Value: 2 <br /> Domain API Value: 'Fail' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **NotStarted**  
Show in UI: **ShownByDefault**  

### Mode

Operation mode for the object when transferring.[Required] [Default(&quot;MER&quot;)] [Filter(eq)]

Type: **[Mode](Systems.Exchange.DataExchangeObjects.md#mode)**  
Category: **System**  
Allowed values for the `Mode`(Systems.Exchange.DataExchangeObjects.md#mode) data attribute  
Allowed Values (Systems.Exchange.DataExchangeObjectsRepository.Mode Enum Members)  

| Value | Description |
| ---- | --- |
| Merge | Merge. Stored as 'MER'. <br /> Database Value: 'MER' <br /> Model Value: 0 <br /> Domain API Value: 'Merge' |
| Add | Add. Stored as 'ADD'. <br /> Database Value: 'ADD' <br /> Model Value: 1 <br /> Domain API Value: 'Add' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Merge**  
Show in UI: **ShownByDefault**  

### Notes

Notes for the exchanged object[Filter(like)]

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Reason

Reason for adding the object.[Required] [Default(&quot;C&quot;)] [Filter(eq)]

Type: **[Reason](Systems.Exchange.DataExchangeObjects.md#reason)**  
Category: **System**  
Allowed values for the `Reason`(Systems.Exchange.DataExchangeObjects.md#reason) data attribute  
Allowed Values (Systems.Exchange.DataExchangeObjectsRepository.Reason Enum Members)  

| Value | Description |
| ---- | --- |
| CoreData | Core data. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 0 <br /> Domain API Value: 'CoreData' |
| ByReference | By Reference. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 1 <br /> Domain API Value: 'ByReference' |
| Other | Other. Stored as 'O'. <br /> Database Value: 'O' <br /> Model Value: 2 <br /> Domain API Value: 'Other' |
| Unknown | Unknown. Stored as 'U'. <br /> Database Value: 'U' <br /> Model Value: 3 <br /> Domain API Value: 'Unknown' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **CoreData**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### DataExchange

The exchange of the object.

Type: **[DataExchanges](Systems.Exchange.DataExchanges.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### DataObject

The data object which will be transferred.

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
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

