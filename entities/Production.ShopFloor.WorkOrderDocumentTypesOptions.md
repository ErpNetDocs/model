---
uid: Production.ShopFloor.WorkOrderDocumentTypesOptions
---
# Production.ShopFloor.WorkOrderDocumentTypesOptions Entity

**Namespace:** [Production.ShopFloor](Production.ShopFloor.md)  

Options for user-defined Work Order document types. Entity: Prd_Work_Order_Document_Types_Options

## Renames

Old name: **Production.WorkOrderDocumentTypesOptions**  
New name: **Production.ShopFloor.WorkOrderDocumentTypesOptions**  
Version: **25.1.0.64**  
Case: **37169**  



## Default Visualization
Default Display Text Format:  
_{DocumentType.EntityName}_  
Default Search Members:  
_DocumentType.EntityName_  
Name Data Member:  
_DocumentType.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#id) | guid |  
| [ObjectVersion](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProductionМode](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#productionмode) | [ProductionМode](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#productionмode) | Specifies whether the document is for Production or Decomposition purposes. `Required` `Default("P")` `Filter(eq)` `Introduced in version 25.1.0.76` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletingOutput<br />OrderDocumentType](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#completingoutputorderdocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | User-defined Completing Output Order document type. `Filter(multi eq)` |
| [DocumentType](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | User-defined Work Order document type. `Required` `Filter(multi eq)` `Owner` |


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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ProductionМode

Specifies whether the document is for Production or Decomposition purposes. `Required` `Default("P")` `Filter(eq)` `Introduced in version 25.1.0.76`

_Type_: **[ProductionМode](Production.ShopFloor.WorkOrderDocumentTypesOptions.md#productionмode)**  
_Category_: **System**  
Allowed values for the `ProductionМode`(Production.ShopFloor.WorkOrderDocumentTypesOptions.md#productionмode) data attribute  
_Allowed Values (Production.ShopFloor.WorkOrderDocumentTypesOptionsRepository.ProductionМode Enum Members)_  

| Value | Description |
| ---- | --- |
| Production | Production. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Production' |
| Decomposition | Decomposition. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Decomposition' |
| ProductionOrDecomposition<br />DependsOnSign | Production or Decomposition (depends on sign) . Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'ProductionOrDecomposition<br />DependsOnSign' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Production**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CompletingOutputOrderDocumentType

User-defined Completing Output Order document type. `Filter(multi eq)`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DocumentType

User-defined Work Order document type. `Required` `Filter(multi eq)` `Owner`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

