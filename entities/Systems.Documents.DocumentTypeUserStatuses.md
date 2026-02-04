---
uid: Systems.Documents.DocumentTypeUserStatuses
---
# Systems.Documents.DocumentTypeUserStatuses


User-defined document statuses.

## General
Namespace: [Systems.Documents](Systems.Documents.md)  
Repository: Systems.Documents.DocumentTypeUserStatuses  
Base Table: Gen_Document_Type_User_Statuses  
API access:  ReadWrite  

## Renames

Old name: General.DocumentTypeUserStatuses  
New name: Systems.Documents.DocumentTypeUserStatuses  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {UserStatusName:T}  
Search Members: UserStatusName  
Name Member: UserStatusName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Systems.Documents.DocumentTypeUserStatuses.md#active) | boolean | Is the user status active for applying to documents. `Required` `Default(true)` `Filter(eq)` 
| [DisplayOrder](Systems.Documents.DocumentTypeUserStatuses.md#displayorder) | int32 | Consecutive display order of the status, with regard to other statuses within the same document type. `Required` `Filter(ge;le)` 
| [Instructions](Systems.Documents.DocumentTypeUserStatuses.md#instructions) | [MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__ | Instructions what should be done when this user status is active (Rich Text). 
| [IsExitStatus](Systems.Documents.DocumentTypeUserStatuses.md#isexitstatus) | boolean | True when the status allows going to the next system status, false otherwise. For example for system status Firm Planned, only user status Approved might allow going to Released. `Required` `Default(true)` `Filter(eq)` 
| [State](Systems.Documents.DocumentTypeUserStatuses.md#state) | [DocumentState](Systems.Documents.DocumentTypeUserStatuses.md#state) | The system state to which this user status is bound. `Required` `Filter(eq)` 
| [UserStatusName](Systems.Documents.DocumentTypeUserStatuses.md#userstatusname) | [MultilanguageString (128)](../data-types.md#multilanguagestring) | Multi-language name of the user status. `Required` `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](Systems.Documents.DocumentTypeUserStatuses.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type, to which this user status is bound. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Documents.DocumentTypeUserStatuses.md#id) | guid |  
| [ObjectVersion](Systems.Documents.DocumentTypeUserStatuses.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Documents.DocumentTypeUserStatuses.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Active

Is the user status active for applying to documents. `Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### DisplayOrder

Consecutive display order of the status, with regard to other statuses within the same document type. `Required` `Filter(ge;le)`

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.DocumentType.UserStatuses.Select( c => c.DisplayOrder).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.DocumentType.UserStatuses.Select( c => c.DisplayOrder).DefaultIfEmpty( 0).Max( ) + 1)`
### Instructions

Instructions what should be done when this user status is active (Rich Text).

Type: **[MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsExitStatus

True when the status allows going to the next system status, false otherwise. For example for system status Firm Planned, only user status Approved might allow going to Released. `Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### State

The system state to which this user status is bound. `Required` `Filter(eq)`

Type: **[DocumentState](Systems.Documents.DocumentTypeUserStatuses.md#state)**  
Category: **System**  
Enumeration of document system states  
Allowed Values (General.Documents.DocumentState Enum Members)  

| Value | Description |
| ---- | --- |
| New | New document, just created. Can be edited. (Stored as 0). <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'New' |
| Adjustment | Document which adjusts other released documents. (Stored as 5). <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'Adjustment' |
| Planned | Planned by the system for future releasing. (Stored as 10). <br /> Database Value: 10 <br /> Model Value: 10 <br /> Domain API Value: 'Planned' |
| FirmPlanned | Planned by operator for future releasing. (Stored as 20). <br /> Database Value: 20 <br /> Model Value: 20 <br /> Domain API Value: 'FirmPlanned' |
| Released | Released document. Changes can be applied only through adjustment documents. (Stored as 30). <br /> Database Value: 30 <br /> Model Value: 30 <br /> Domain API Value: 'Released' |
| Completed | Work has completed. (Stored as 40). <br /> Database Value: 40 <br /> Model Value: 40 <br /> Domain API Value: 'Completed' |
| Closed | The document is audited and closed. Adjustments are not allowed, but reopening is allowed. (Stored as 50). <br /> Database Value: 50 <br /> Model Value: 50 <br /> Domain API Value: 'Closed' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UserStatusName

Multi-language name of the user status. `Required` `Filter(eq;like)`

Type: **[MultilanguageString (128)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### DocumentType

The document type, to which this user status is bound. `Required` `Filter(multi eq)` `Owner`

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Systems.Documents.DocumentTypeUserStatuses erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.DocumentTypeUserStatuses erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_DocumentTypeUserStatuses

Domain API Entity Type: 
Systems_Documents_DocumentTypeUserStatus

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_DocumentTypeUserStatuses?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_DocumentTypeUserStatuses?$top=10>

