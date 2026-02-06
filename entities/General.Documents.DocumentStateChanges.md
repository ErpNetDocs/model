---
uid: General.Documents.DocumentStateChanges
---
# General.Documents.DocumentStateChanges


History of document state changes.

## General
Namespace: [General.Documents](General.Documents.md)  
Repository: General.Documents.DocumentStateChanges  
Base Table: Gen_Document_State_Changes  
API access:  ReadWrite  

## Renames

Old name: General.DocumentStateChanges  
New name: General.Documents.DocumentStateChanges  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {Id}. {Document.DocumentNo} {Document.DocumentType.TypeName:T}  
Search Members: Document.DocumentNo  
Name Member: Document.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  0 - Do not track changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Documents.Documents](General.Documents.Documents.md)  
Aggregate Root:  
[General.Documents.Documents](General.Documents.Documents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [NewState](General.Documents.DocumentStateChanges.md#newstate) | [NewState](General.Documents.DocumentStateChanges.md#newstate) | The new state after the change.[Required] [Filter(eq)] 
| [SystemInitiated](General.Documents.DocumentStateChanges.md#systeminitiated) | boolean | Specifies whether the state change was caused by system process or from user action.[Required] [Default(false)] [ReadOnly] 
| [UpdateTime](General.Documents.DocumentStateChanges.md#updatetime) | datetime | The time when the change took effect.[Required] [Filter(ge;le)] [ORD] 
| [UpdateUser](General.Documents.DocumentStateChanges.md#updateuser) | string (64) | The login name of the user, who made the status change[Required] [Filter(eq)] 
| [Void](General.Documents.DocumentStateChanges.md#void) | boolean | 1 if the document is voided with this change[Required] [Default(false)] [Filter(eq)] [Introduced in version 19.1] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](General.Documents.DocumentStateChanges.md#document) | [Documents](General.Documents.Documents.md) | The document which has changed state. |
| [UserStatus](General.Documents.DocumentStateChanges.md#userstatus) | [DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable) | The new user status after the change. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Documents.DocumentStateChanges.md#id) | guid |  
| [ObjectVersion](General.Documents.DocumentStateChanges.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Documents.DocumentStateChanges.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### NewState

The new state after the change.[Required] [Filter(eq)]

Type: **[NewState](General.Documents.DocumentStateChanges.md#newstate)**  
Category: **System**  
Allowed values for the `NewState`(General.Documents.DocumentStateChanges.md#newstate) data attribute  
Allowed Values (General.Documents.DocumentStateChangesRepository.NewState Enum Members)  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 0. <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'New' |
| Corrective | Corrective value. Stored as 5. <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'Corrective' |
| Planned | Planned value. Stored as 10. <br /> Database Value: 10 <br /> Model Value: 10 <br /> Domain API Value: 'Planned' |
| FirmPlanned | FirmPlanned value. Stored as 20. <br /> Database Value: 20 <br /> Model Value: 20 <br /> Domain API Value: 'FirmPlanned' |
| Released | Released value. Stored as 30. <br /> Database Value: 30 <br /> Model Value: 30 <br /> Domain API Value: 'Released' |
| Completed | Completed value. Stored as 40. <br /> Database Value: 40 <br /> Model Value: 40 <br /> Domain API Value: 'Completed' |
| Closed | Closed value. Stored as 50. <br /> Database Value: 50 <br /> Model Value: 50 <br /> Domain API Value: 'Closed' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SystemInitiated

Specifies whether the state change was caused by system process or from user action.[Required] [Default(false)] [ReadOnly]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### UpdateTime

The time when the change took effect.[Required] [Filter(ge;le)] [ORD]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### UpdateUser

The login name of the user, who made the status change[Required] [Filter(eq)]

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Void

1 if the document is voided with this change[Required] [Default(false)] [Filter(eq)] [Introduced in version 19.1]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
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

### Document

The document which has changed state.

Type: **[Documents](General.Documents.Documents.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **CannotBeShown**  

### UserStatus

The new user status after the change.

Type: **[DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable)**  
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

[!list limit=1000 erp.entity=General.Documents.DocumentStateChanges erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Documents.DocumentStateChanges erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Documents_DocumentStateChanges

Domain API Entity Type: 
General_Documents_DocumentStateChange

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Documents_DocumentStateChanges?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Documents_DocumentStateChanges?$top=10>

