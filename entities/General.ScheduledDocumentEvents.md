---
uid: General.ScheduledDocumentEvents
---
# General.ScheduledDocumentEvents Entity

**Namespace:** [General](General.md)  

Contains postponed events, which will be executed later. Usually these are large number of recalculation events, resulting from other events. For example, releasing a cost correction, publishes postponed events for all affected documents. Entity: Gen_Scheduled_Document_Events

## Default Visualization
Default Display Text Format:  
_{Id}: {SourceDocumentId}_  
Default Search Members:  
__  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.ScheduledDocumentEvents](General.ScheduledDocumentEvents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Cancelled](General.ScheduledDocumentEvents.md#cancelled) | boolean | When true, specifies that this document event has been cancelled (either manually or in respect to another event) and will not be executed. `Required` `Default(false)` `Filter(eq)` 
| [CreationTime](General.ScheduledDocumentEvents.md#creationtime) | datetime | Date and time when the ScheduledDocumentEvent was created. `Required` `Default(Now)` `ReadOnly` 
| [DisplayText](General.ScheduledDocumentEvents.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DocumentEvent](General.ScheduledDocumentEvents.md#documentevent) | string (254) | The type of the document event that is scheduled to be processed. `Required` `ReadOnly` 
| [Id](General.ScheduledDocumentEvents.md#id) | guid |  
| [LastProcessStatus](General.ScheduledDocumentEvents.md#lastprocessstatus) | string (max) __nullable__ | Status/information of the last attemp to process the event. Usually shows the cause in case of failure. `ReadOnly` 
| [LastProcessTime](General.ScheduledDocumentEvents.md#lastprocesstime) | datetime __nullable__ | The time of the last attempt to process the event. `ReadOnly` 
| [ObjectVersion](General.ScheduledDocumentEvents.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Processed](General.ScheduledDocumentEvents.md#processed) | boolean | Indicates wheather the event is already processed or not. `Required` `Default(false)` `Filter(eq)` `ReadOnly` 
| [State](General.ScheduledDocumentEvents.md#state) | [State](General.ScheduledDocumentEvents.md#state) | The state of the document for which the event will be processed. `Required` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](General.ScheduledDocumentEvents.md#document) | [Documents](General.Documents.md) | The document for which the event will be processed. `Required` `Filter(multi eq)` `ReadOnly` |
| [SourceDocument](General.ScheduledDocumentEvents.md#sourcedocument) | [Documents](General.Documents.md) | The document that has caused this event to be scheduled. `Required` `Filter(multi eq)` `ReadOnly` |


## Attribute Details

### Cancelled

When true, specifies that this document event has been cancelled (either manually or in respect to another event) and will not be executed. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### CreationTime

Date and time when the ScheduledDocumentEvent was created. `Required` `Default(Now)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### DocumentEvent

The type of the document event that is scheduled to be processed. `Required` `ReadOnly`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### LastProcessStatus

Status/information of the last attemp to process the event. Usually shows the cause in case of failure. `ReadOnly`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

### LastProcessTime

The time of the last attempt to process the event. `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Processed

Indicates wheather the event is already processed or not. `Required` `Default(false)` `Filter(eq)` `ReadOnly`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### State

The state of the document for which the event will be processed. `Required` `ReadOnly`

_Type_: **[State](General.ScheduledDocumentEvents.md#state)**  
_Category_: **System**  
Allowed values for the `State`(General.ScheduledDocumentEvents.md#state) data attribute  
_Allowed Values (General.ScheduledDocumentEventsRepository.State Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| Corrective | Corrective value. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Corrective' |
| Planned | Planned value. Stored as 10. <br /> _Database Value:_ 10 <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'Planned' |
| FirmPlanned | FirmPlanned value. Stored as 20. <br /> _Database Value:_ 20 <br /> _Model Value:_ 20 <br /> _Domain API Value:_ 'FirmPlanned' |
| Released | Released value. Stored as 30. <br /> _Database Value:_ 30 <br /> _Model Value:_ 30 <br /> _Domain API Value:_ 'Released' |
| Completed | Completed value. Stored as 40. <br /> _Database Value:_ 40 <br /> _Model Value:_ 40 <br /> _Domain API Value:_ 'Completed' |
| Closed | Closed value. Stored as 50. <br /> _Database Value:_ 50 <br /> _Model Value:_ 50 <br /> _Domain API Value:_ 'Closed' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### Document

The document for which the event will be processed. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Documents](General.Documents.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### SourceDocument

The document that has caused this event to be scheduled. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Documents](General.Documents.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
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



## Business Rules

[!list limit=1000 erp.entity=General.ScheduledDocumentEvents erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.ScheduledDocumentEvents erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_ScheduledDocumentEvents?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_ScheduledDocumentEvents?$top=10>

