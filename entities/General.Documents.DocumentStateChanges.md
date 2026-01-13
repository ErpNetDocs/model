---
uid: General.Documents.DocumentStateChanges
---
# General.Documents.DocumentStateChanges Entity

**Namespace:** [General.Documents](General.Documents.md)  

History of document state changes. Entity: Gen_Document_State_Changes

## Renames

Old name: **General.DocumentStateChanges**  
New name: **General.Documents.DocumentStateChanges**  
Version: **25.1.0.64**  
Case: **37169**  



## Default Visualization
Default Display Text Format:  
_{Id}. {Document.DocumentNo} {Document.DocumentType.TypeName:T}_  
Default Search Members:  
_Document.DocumentNo_  
Name Data Member:  
_Document.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _0 - Do not track changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Documents.Documents](General.Documents.Documents.md)  
Aggregate Root:  
[General.Documents.Documents](General.Documents.Documents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](General.Documents.DocumentStateChanges.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](General.Documents.DocumentStateChanges.md#id) | guid |  
| [NewState](General.Documents.DocumentStateChanges.md#newstate) | [NewState](General.Documents.DocumentStateChanges.md#newstate) | The new state after the change. `Required` `Filter(eq)` 
| [ObjectVersion](General.Documents.DocumentStateChanges.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [SystemInitiated](General.Documents.DocumentStateChanges.md#systeminitiated) | boolean | Specifies whether the state change was caused by system process or from user action. `Required` `Default(false)` `ReadOnly` 
| [UpdateTime](General.Documents.DocumentStateChanges.md#updatetime) | datetime | The time when the change took effect. `Required` `Filter(ge;le)` `ORD` 
| [UpdateUser](General.Documents.DocumentStateChanges.md#updateuser) | string (64) | The login name of the user, who made the status change. `Required` `Filter(eq)` 
| [Void](General.Documents.DocumentStateChanges.md#void) | boolean | True if the document is voided with this change. `Required` `Default(false)` `Filter(eq)` `Introduced in version 19.1` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](General.Documents.DocumentStateChanges.md#document) | [Documents](General.Documents.Documents.md) | The document which has changed state. `Required` `Filter(multi eq)` `Owner` |
| [UserStatus](General.Documents.DocumentStateChanges.md#userstatus) | [DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable) | The new user status after the change. `Filter(multi eq)` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
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

### NewState

The new state after the change. `Required` `Filter(eq)`

_Type_: **[NewState](General.Documents.DocumentStateChanges.md#newstate)**  
_Category_: **System**  
Allowed values for the `NewState`(General.Documents.DocumentStateChanges.md#newstate) data attribute  
_Allowed Values (General.Documents.DocumentStateChangesRepository.NewState Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| Corrective | Corrective value. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Corrective' |
| Planned | Planned value. Stored as 10. <br /> _Database Value:_ 10 <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'Planned' |
| FirmPlanned | FirmPlanned value. Stored as 20. <br /> _Database Value:_ 20 <br /> _Model Value:_ 20 <br /> _Domain API Value:_ 'FirmPlanned' |
| Released | Released value. Stored as 30. <br /> _Database Value:_ 30 <br /> _Model Value:_ 30 <br /> _Domain API Value:_ 'Released' |
| Completed | Completed value. Stored as 40. <br /> _Database Value:_ 40 <br /> _Model Value:_ 40 <br /> _Domain API Value:_ 'Completed' |
| Closed | Closed value. Stored as 50. <br /> _Database Value:_ 50 <br /> _Model Value:_ 50 <br /> _Domain API Value:_ 'Closed' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### SystemInitiated

Specifies whether the state change was caused by system process or from user action. `Required` `Default(false)` `ReadOnly`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### UpdateTime

The time when the change took effect. `Required` `Filter(ge;le)` `ORD`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### UpdateUser

The login name of the user, who made the status change. `Required` `Filter(eq)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Void

True if the document is voided with this change. `Required` `Default(false)` `Filter(eq)` `Introduced in version 19.1`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Document

The document which has changed state. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Documents](General.Documents.Documents.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **CannotBeShown**  

### UserStatus

The new user status after the change. `Filter(multi eq)`

_Type_: **[DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable)**  
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

