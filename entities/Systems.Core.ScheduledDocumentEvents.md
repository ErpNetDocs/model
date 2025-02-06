---
uid: Systems.Core.ScheduledDocumentEvents
---
# Systems.Core.ScheduledDocumentEvents Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Contains postponed events, which will be executed later. Usually these are large number of recalculation events, resulting from other events. For example, releasing a cost correction, publishes postponed events for all affected documents. Entity: Gen_Scheduled_Document_Events
## Renamed
**New name:** [Systems.Monitoring.ScheduledDocumentEvents](Systems.Monitoring.ScheduledDocumentEvents.md)  



## Default Visualization
Default Display Text Format:  
_{Id}: {SourceDocumentId}_  
Default Search Members:  
__  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.ScheduledDocumentEvents](Systems.Core.ScheduledDocumentEvents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Cancelled](Systems.Core.ScheduledDocumentEvents.md#cancelled) | boolean | When true, specifies that this document event has been cancelled (either manually or in respect to another event) and will not be executed. `Required` `Default(false)` `Filter(eq)` 
| [CreationTime](Systems.Core.ScheduledDocumentEvents.md#creationtime) | datetime | Date and time when the ScheduledDocumentEvent was created. `Required` `Default(Now)` `Filter(ge;le)` `ReadOnly` 
| [DisplayText](Systems.Core.ScheduledDocumentEvents.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DocumentEvent](Systems.Core.ScheduledDocumentEvents.md#documentevent) | string (254) | The type of the document event that is scheduled to be processed. `Required` `ReadOnly` 
| [Id](Systems.Core.ScheduledDocumentEvents.md#id) | guid |  
| [LastProcessStatus](Systems.Core.ScheduledDocumentEvents.md#lastprocessstatus) | string (max) __nullable__ | Status/information of the last attemp to process the event. Usually shows the cause in case of failure. `ReadOnly` 
| [LastProcessTime](Systems.Core.ScheduledDocumentEvents.md#lastprocesstime) | datetime __nullable__ | The time of the last attempt to process the event. `Filter(ge;le)` `ReadOnly` 
| [ObjectVersion](Systems.Core.ScheduledDocumentEvents.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Processed](Systems.Core.ScheduledDocumentEvents.md#processed) | boolean | Indicates wheather the event is already processed or not. `Required` `Default(false)` `Filter(eq)` `ReadOnly` 
| [State](Systems.Core.ScheduledDocumentEvents.md#state) | [State](Systems.Core.ScheduledDocumentEvents.md#state) | The state of the document for which the event will be processed. `Required` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Systems.Core.ScheduledDocumentEvents.md#document) | [Documents](General.Documents.md) | The document for which the event will be processed. `Required` `Filter(multi eq)` `ReadOnly` |
| [SourceDocument](Systems.Core.ScheduledDocumentEvents.md#sourcedocument) | [Documents](General.Documents.md) | The document that has caused this event to be scheduled. `Required` `Filter(multi eq)` `ReadOnly` |


## Attribute Details

### Cancelled

When true, specifies that this document event has been cancelled (either manually or in respect to another event) and will not be executed. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### CreationTime

Date and time when the ScheduledDocumentEvent was created. `Required` `Default(Now)` `Filter(ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DocumentEvent

The type of the document event that is scheduled to be processed. `Required` `ReadOnly`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LastProcessStatus

Status/information of the last attemp to process the event. Usually shows the cause in case of failure. `ReadOnly`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### LastProcessTime

The time of the last attempt to process the event. `Filter(ge;le)` `ReadOnly`

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

### Processed

Indicates wheather the event is already processed or not. `Required` `Default(false)` `Filter(eq)` `ReadOnly`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### State

The state of the document for which the event will be processed. `Required` `ReadOnly`

_Type_: **[State](Systems.Core.ScheduledDocumentEvents.md#state)**  
_Category_: **System**  
Allowed values for the `State`(Systems.Core.ScheduledDocumentEvents.md#state) data attribute  
_Allowed Values (Systems.Core.ScheduledDocumentEventsRepository.State Enum Members)_  

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
_Show in UI_: **ShownByDefault**  


## Reference Details

### Document

The document for which the event will be processed. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Documents](General.Documents.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SourceDocument

The document that has caused this event to be scheduled. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Documents](General.Documents.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### Process

Processes this `ScheduledDocumentEvent`(Systems.Core.ScheduledDocumentEvents.md).             The method returns true if the event is processed successfully and false if there is an error.             In case of failure the error message is saved in LastProcessStatus attribute of the event object.             The already processed or canceled events are not processed again but still the result value is true.  
_Return Type_: **boolean**  
_Declaring Type_: **[ScheduledDocumentEvents](Systems.Core.ScheduledDocumentEvents.md)**  
_Domain API Request_: **POST**  

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


### CreateNotification

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Systems.Core.ScheduledDocumentEvents erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.ScheduledDocumentEvents erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Core_ScheduledDocumentEvents?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Core_ScheduledDocumentEvents?$top=10>

