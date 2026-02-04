---
uid: Production.ShopFloor.WorkOrderDocumentTypesOptions
---
# Production.ShopFloor.WorkOrderDocumentTypesOptions


Options for user-defined Work Order document types

## General
Namespace: [Production.ShopFloor](Production.ShopFloor.md)  
Repository: Production.ShopFloor.WorkOrderDocumentTypesOptions  
Base Table: Prd_Work_Order_Document_Types_Options  
API access:  ReadWrite  

## Renames

Old name: Production.WorkOrderDocumentTypesOptions  
New name: Production.ShopFloor.WorkOrderDocumentTypesOptions  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {DocumentType.EntityName}  
Search Members: DocumentType.EntityName  
Name Member: DocumentType.EntityName  
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
| [ProductionМode](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#productionмode) | [ProductionМode](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#productionмode) | Specifies whether the document is for Production or Decomposition purposes. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletingOutput<br />OrderDocumentType](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#completingoutputorderdocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | User-defined Completing Output Order document type |
| [DocumentType](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | User-defined Work Order document type |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#id) | guid |  
| [ObjectVersion](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ProductionМode

Specifies whether the document is for Production or Decomposition purposes.

Type: **[ProductionМode](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#productionмode)**  
Category: **System**  
Allowed values for the `ProductionМode`(Production.ShopFloor.WorkOrderDocumentTypesOptions.md#productionмode) data attribute  
Allowed Values (Production.ShopFloor.WorkOrderDocumentTypesOptionsRepository.ProductionМode Enum Members)  

| Value | Description |
| ---- | --- |
| Production | Production. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 0 <br /> Domain API Value: 'Production' |
| Decomposition | Decomposition. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 1 <br /> Domain API Value: 'Decomposition' |
| ProductionOrDecomposition<br />DependsOnSign | Production or Decomposition (depends on sign) . Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 2 <br /> Domain API Value: 'ProductionOrDecomposition<br />DependsOnSign' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Production**  
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

### CompletingOutputOrderDocumentType

User-defined Completing Output Order document type

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DocumentType

User-defined Work Order document type

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

[!list limit=1000 erp.entity=Production.ShopFloor.WorkOrderDocumentTypesOptions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.ShopFloor.WorkOrderDocumentTypesOptions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_ShopFloor_WorkOrderDocumentTypesOptions

Domain API Entity Type: 
Production_ShopFloor_WorkOrderDocumentTypesOption

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_ShopFloor_WorkOrderDocumentTypesOptions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_ShopFloor_WorkOrderDocumentTypesOptions?$top=10>

