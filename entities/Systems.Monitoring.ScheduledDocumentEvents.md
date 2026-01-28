---
uid: Systems.Monitoring.ScheduledDocumentEvents
---
# Systems.Monitoring.ScheduledDocumentEvents


Contains postponed events, which will be executed later. Usually these are large number of recalculation events, resulting from other events. For example, releasing a cost correction, publishes postponed events for all affected documents.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.ScheduledDocumentEvents  
Base Table: Gen_Scheduled_Document_Events  
API access:  ReadWrite  

## Renames

Old name: Systems.Core.ScheduledDocumentEvents  
New name: Systems.Monitoring.ScheduledDocumentEvents  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Id}: {SourceDocumentId}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.ScheduledDocumentEvents](Systems.Monitoring.ScheduledDocumentEvents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Cancelled](Systems.Monitoring.ScheduledDocumentEvents.md#cancelled) | boolean | When true, specifies that this document event has been cancelled (either manually or in respect to another event) and will not be executed. `Required` `Default(false)` `Filter(eq)` 
| [CreationTime](Systems.Monitoring.ScheduledDocumentEvents.md#creationtime) | datetime | Date and time when the ScheduledDocumentEvent was created. `Required` `Default(Now)` `Filter(ge;le)` `ReadOnly` 
| [DocumentEvent](Systems.Monitoring.ScheduledDocumentEvents.md#documentevent) | string (254) | The type of the document event that is scheduled to be processed. `Required` `ReadOnly` 
| [LastProcessStatus](Systems.Monitoring.ScheduledDocumentEvents.md#lastprocessstatus) | string (max) __nullable__ | Status/information of the last attemp to process the event. Usually shows the cause in case of failure. `ReadOnly` 
| [LastProcessTime](Systems.Monitoring.ScheduledDocumentEvents.md#lastprocesstime) | datetime __nullable__ | The time of the last attempt to process the event. `Filter(ge;le)` `ReadOnly` 
| [Processed](Systems.Monitoring.ScheduledDocumentEvents.md#processed) | boolean | Indicates wheather the event is already processed or not. `Required` `Default(false)` `Filter(eq)` `ReadOnly` 
| [State](Systems.Monitoring.ScheduledDocumentEvents.md#state) | [State](Systems.Monitoring.ScheduledDocumentEvents.md#state) | The state of the document for which the event will be processed. `Required` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Systems.Monitoring.ScheduledDocumentEvents.md#document) | [Documents](General.Documents.Documents.md) | The document for which the event will be processed. `Required` `Filter(multi eq)` `ReadOnly` |
| [SourceDocument](Systems.Monitoring.ScheduledDocumentEvents.md#sourcedocument) | [Documents](General.Documents.Documents.md) | The document that has caused this event to be scheduled. `Required` `Filter(multi eq)` `ReadOnly` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Monitoring.ScheduledDocumentEvents.md#id) | guid |  
| [ObjectVersion](Systems.Monitoring.ScheduledDocumentEvents.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Monitoring.ScheduledDocumentEvents.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Monitoring.ScheduledDocumentEvents.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Monitoring.ScheduledDocumentEvents.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Monitoring.ScheduledDocumentEvents.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Cancelled

When true, specifies that this document event has been cancelled (either manually or in respect to another event) and will not be executed. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### CreationTime

Date and time when the ScheduledDocumentEvent was created. `Required` `Default(Now)` `Filter(ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **HiddenByDefault**  

### DocumentEvent

The type of the document event that is scheduled to be processed. `Required` `ReadOnly`

Type: **string (254)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### LastProcessStatus

Status/information of the last attemp to process the event. Usually shows the cause in case of failure. `ReadOnly`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### LastProcessTime

The time of the last attempt to process the event. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Processed

Indicates wheather the event is already processed or not. `Required` `Default(false)` `Filter(eq)` `ReadOnly`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### State

The state of the document for which the event will be processed. `Required` `ReadOnly`

Type: **[State](Systems.Monitoring.ScheduledDocumentEvents.md#state)**  
Category: **System**  
Allowed values for the `State`(Systems.Monitoring.ScheduledDocumentEvents.md#state) data attribute  
Allowed Values (Systems.Monitoring.ScheduledDocumentEventsRepository.State Enum Members)  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 0. <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'New' |
| Corrective | Corrective value. Stored as 5. <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'Corrective' |
| Planned | Planned value. Stored as 10. <br /> Database Value: 10 <br /> Model Value: 10 <br /> Domain API Value: 'Planned' |
| FirmPlanned | FirmPlanned value. Stored as 20. <br /> Database Value: 20 <br /> Model Value: 20 <br /> Domain API Value: 'FirmPlanned' |
| Released | Released value. Stored as 30. <br /> Database Value: 30 <br /> Model Value: 30 <br /> Domain API Value: 'Released' |
| Completed | Completed value. Stored as 40. <br /> Database Value: 40 <br /> Model Value: 40 <br /> Domain API Value: 'Completed' |
| Closed | Closed value. Stored as 50. <br /> Database Value: 50 <br /> Model Value: 50 <br /> Domain API Value: 'Closed' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
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

### Document

The document for which the event will be processed. `Required` `Filter(multi eq)` `ReadOnly`

Type: **[Documents](General.Documents.Documents.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SourceDocument

The document that has caused this event to be scheduled. `Required` `Filter(multi eq)` `ReadOnly`

Type: **[Documents](General.Documents.Documents.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### Process

Processes this `ScheduledDocumentEvent`(Systems.Monitoring.ScheduledDocumentEvents.md).             The method returns true if the event is processed successfully and false if there is an error.             In case of failure the error message is saved in LastProcessStatus attribute of the event object.             The already processed or canceled events are not processed again but still the result value is true.  
Return Type: **boolean**  
Declaring Type: **[ScheduledDocumentEvents](Systems.Monitoring.ScheduledDocumentEvents.md)**  
Domain API Request: **POST**  

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

[!list limit=1000 erp.entity=Systems.Monitoring.ScheduledDocumentEvents erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Monitoring.ScheduledDocumentEvents erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Monitoring_ScheduledDocumentEvents

Domain API Entity Type: 
Systems_Monitoring_ScheduledDocumentEvent

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_ScheduledDocumentEvents?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_ScheduledDocumentEvents?$top=10>

