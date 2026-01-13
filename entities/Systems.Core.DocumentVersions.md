---
uid: Systems.Core.DocumentVersions
---
# Systems.Core.DocumentVersions Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

History of each saved version of each document. Entity: Gen_Document_Versions

## Renames

Old name: **General.DocumentVersions**  
New name: **Systems.Core.DocumentVersions**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{Id}: {DocumentId}_  
Default Search Members:  
__  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.DocumentVersions](Systems.Core.DocumentVersions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Core.DocumentVersions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DocumentData](Systems.Core.DocumentVersions.md#documentdata) | byte[] __nullable__ | Compressed representation of the document data. Valid when Document Data Format = D (deflate compressed). `ReadOnly` 
| [DocumentDataFormat](Systems.Core.DocumentVersions.md#documentdataformat) | string (1) | The format of the saved document data. 'U' - uncompressed and stored in Document Data XML; 'D' - Deflate compressed and stored in Document Data. `Required` `Default("U")` `ReadOnly` 
| [DocumentDataXML](Systems.Core.DocumentVersions.md#documentdataxml) | string (max) __nullable__ | The uncompressed XML representation of the document data, including the document row, the header row and all types of lines. Valid when Document Data Format = U (uncompressed). `ReadOnly` 
| [ExternalId](Systems.Core.DocumentVersions.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Core.DocumentVersions.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Core.DocumentVersions.md#id) | guid |  
| [ObjectVersion](Systems.Core.DocumentVersions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [State](Systems.Core.DocumentVersions.md#state) | [State](Systems.Core.DocumentVersions.md#state) | The state of the document by the time it was saved. `Required` `Default(0)` `Filter(multi eq)` `ReadOnly` 
| [UpdateTime](Systems.Core.DocumentVersions.md#updatetime) | datetime | The date and time when this version was saved. `Required` `Default(Now)` `Filter(ge;le)` `ORD` `ReadOnly` 
| [UpdateUser](Systems.Core.DocumentVersions.md#updateuser) | string (64) | The login name of the user that saved this version. `Required` `Filter(eq;like)` `ReadOnly` 
| [Version](Systems.Core.DocumentVersions.md#version) | int32 | The version number that is stored in this row. `Required` `Filter(eq;ge;le)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Systems.Core.DocumentVersions.md#document) | [Documents](General.Documents.Documents.md) | The document whoose version is stored in this row. `Required` `Filter(multi eq)` `ReadOnly` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DocumentData

Compressed representation of the document data. Valid when Document Data Format = D (deflate compressed). `ReadOnly`

_Type_: **byte[] __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **CannotBeShown**  

### DocumentDataFormat

The format of the saved document data. 'U' - uncompressed and stored in Document Data XML; 'D' - Deflate compressed and stored in Document Data. `Required` `Default("U")` `ReadOnly`

_Type_: **string (1)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **1**  
_Default Value_: **U**  
_Show in UI_: **CannotBeShown**  

### DocumentDataXML

The uncompressed XML representation of the document data, including the document row, the header row and all types of lines. Valid when Document Data Format = U (uncompressed). `ReadOnly`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **CannotBeShown**  

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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### State

The state of the document by the time it was saved. `Required` `Default(0)` `Filter(multi eq)` `ReadOnly`

_Type_: **[State](Systems.Core.DocumentVersions.md#state)**  
_Category_: **System**  
Allowed values for the `State`(Systems.Core.DocumentVersions.md#state) data attribute  
_Allowed Values (Systems.Core.DocumentVersionsRepository.State Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| Adjustment | Adjustment value. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Adjustment' |
| Planned | Planned value. Stored as 10. <br /> _Database Value:_ 10 <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'Planned' |
| FirmPlanned | FirmPlanned value. Stored as 20. <br /> _Database Value:_ 20 <br /> _Model Value:_ 20 <br /> _Domain API Value:_ 'FirmPlanned' |
| Released | Released value. Stored as 30. <br /> _Database Value:_ 30 <br /> _Model Value:_ 30 <br /> _Domain API Value:_ 'Released' |
| Completed | Completed value. Stored as 40. <br /> _Database Value:_ 40 <br /> _Model Value:_ 40 <br /> _Domain API Value:_ 'Completed' |
| Closed | Closed value. Stored as 50. <br /> _Database Value:_ 50 <br /> _Model Value:_ 50 <br /> _Domain API Value:_ 'Closed' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### UpdateTime

The date and time when this version was saved. `Required` `Default(Now)` `Filter(ge;le)` `ORD` `ReadOnly`

_Type_: **datetime**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

### UpdateUser

The login name of the user that saved this version. `Required` `Filter(eq;like)` `ReadOnly`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Version

The version number that is stored in this row. `Required` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Document

The document whoose version is stored in this row. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Documents](General.Documents.Documents.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  


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

[!list limit=1000 erp.entity=Systems.Core.DocumentVersions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.DocumentVersions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Core_DocumentVersions

Domain API Entity Type: 
Systems_Core_DocumentVersion

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_DocumentVersions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_DocumentVersions?$top=10>

