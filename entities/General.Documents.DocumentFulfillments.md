---
uid: General.Documents.DocumentFulfillments
---
# General.Documents.DocumentFulfillments Entity

**Namespace:** [General.Documents](General.Documents.md)  

Fulfillment ledger for documents. Entity: Gen_Document_Fulfillments (Introduced in version 20.1)

## Renames

Old name: **General.DocumentFulfillments**  
New name: **General.Documents.DocumentFulfillments**  
Version: **25.1.0.64**  
Case: **37169**  



## Default Visualization
Default Display Text Format:  
_{Id}. {Document.DocumentNo} {Document.DocumentType.TypeName:T}_  
Default Search Members:  
_Document.DocumentNo_  
Name Data Member:  
_DestinationEntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Documents.Documents](General.Documents.Documents.md)  
Aggregate Root:  
[General.Documents.Documents](General.Documents.Documents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](General.Documents.DocumentFulfillments.md#creationtimeutc) | datetime | The exact time in UTC, when the fulfillment was created in the system. `Required` `Default(NowUtc)` `Filter(multi eq;ge;le)` 
| [DestinationEntityName](General.Documents.DocumentFulfillments.md#destinationentityname) | string (64) | The name of the entity which fulfills the line. Used to differentiate between different fulfillment types. For example, sales order line can be fulfilled, for different purposes, by store order line and invoice order line. `Required` `Default("")` `Filter(eq)` `Introduced in version 22.1.4.7` 
| [DisplayText](General.Documents.DocumentFulfillments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DocumentLineId](General.Documents.DocumentFulfillments.md#documentlineid) | guid | The Id of the fulfilled line within the document. The attribute contains the Id and is not a reference, because it references different entities depending on document entity type and line type. `Required` `Filter(multi eq)` 
| [FulfillmentType](General.Documents.DocumentFulfillments.md#fulfillmenttype) | [FulfillmentType](General.Documents.DocumentFulfillments.md#fulfillmenttype) | Type of fulfillment: P=Planned; C=Completed. `Required` `Filter(multi eq)` `Introduced in version 21.1.1.26` 
| [Id](General.Documents.DocumentFulfillments.md#id) | guid |  
| [IsFinal](General.Documents.DocumentFulfillments.md#isfinal) | boolean | Specifies whether this fulfillment finalizes the line, regardless of any remaining quantities. `Required` `Filter(eq)` 
| [LineNo](General.Documents.DocumentFulfillments.md#lineno) | int32 __nullable__ | Line number. Used for human-readability of the fulfillment. null if the lines do not support line numbers or the line number is unknown. `Filter(multi eq;ge;le)` `Introduced in version 21.1.1.26` 
| [LineType](General.Documents.DocumentFulfillments.md#linetype) | string (1) | Detail (line) type, for example materials, services, etc. L=Line. Other values are defined by the document entity type. `Required` `Default("L")` `Filter(multi eq)` `Introduced in version 21.1.1.26` 
| [ObjectVersion](General.Documents.DocumentFulfillments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [QuantityBase](General.Documents.DocumentFulfillments.md#quantitybase) | decimal (12, 3) | Fulfilled quantity in the base measurement unit of the product. `Required` `Filter(multi eq;ge;le)` `Introduced in version 21.1.1.33` 
| [StandardQuantity](General.Documents.DocumentFulfillments.md#standardquantity) | decimal (12, 3) | The theoretical quantity according to the current measurement dimensions for the product. Used to measure the execution. `Required` `Introduced in version 22.1.4.52` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](General.Documents.DocumentFulfillments.md#creationuser) | [Users](Systems.Security.Users.md) | The user, who created the record. `Required` `Filter(multi eq)` |
| [Document](General.Documents.DocumentFulfillments.md#document) | [Documents](General.Documents.Documents.md) | The Document, which is fulfilled. `Required` `Filter(multi eq)` `ReadOnly` `Introduced in version 21.1.1.26` `Owner` |
| [Lot](General.Documents.DocumentFulfillments.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot, which was fulfilled. null when the fulfillment was not for a specific lot. `Filter(multi eq)` `Introduced in version 22.1.4.52` |
| [ParentFulfillment](General.Documents.DocumentFulfillments.md#parentfulfillment) | [DocumentFulfillments](General.Documents.DocumentFulfillments.md) (nullable) | The parent document fulfillment. Used when the information of the current fulfillment is inherited by another document fulfillment, usually created by another module. `Filter(multi eq)` `Introduced in version 22.1.5.85` |
| [Product](General.Documents.DocumentFulfillments.md#product) | [Products](General.Products.Products.md) (nullable) | The product, which is fulfilled. `Filter(multi eq)` `Introduced in version 22.1.4.52` |
| [ProductVariant](General.Documents.DocumentFulfillments.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | The product variant, which was fulfilled. null when the fulfillment was not for a product variant. `Filter(multi eq)` `Introduced in version 22.1.4.52` |
| [SerialNumber](General.Documents.DocumentFulfillments.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | The serial number, which was fulfilled. null when the fulfillment was not for a specific serial number. `Filter(multi eq)` `Introduced in version 22.1.4.52` |


## Attribute Details

### CreationTimeUtc

The exact time in UTC, when the fulfillment was created in the system. `Required` `Default(NowUtc)` `Filter(multi eq;ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### DestinationEntityName

The name of the entity which fulfills the line. Used to differentiate between different fulfillment types. For example, sales order line can be fulfilled, for different purposes, by store order line and invoice order line. `Required` `Default("")` `Filter(eq)` `Introduced in version 22.1.4.7`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Default Value_: ****  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DocumentLineId

The Id of the fulfilled line within the document. The attribute contains the Id and is not a reference, because it references different entities depending on document entity type and line type. `Required` `Filter(multi eq)`

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### FulfillmentType

Type of fulfillment: P=Planned; C=Completed. `Required` `Filter(multi eq)` `Introduced in version 21.1.1.26`

_Type_: **[FulfillmentType](General.Documents.DocumentFulfillments.md#fulfillmenttype)**  
_Category_: **System**  
Allowed values for the `FulfillmentType`(General.Documents.DocumentFulfillments.md#fulfillmenttype) data attribute  
_Allowed Values (General.Documents.DocumentFulfillmentsRepository.FulfillmentType Enum Members)_  

| Value | Description |
| ---- | --- |
| Planned | Planned value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Planned' |
| Completed | Completed value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Completed' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsFinal

Specifies whether this fulfillment finalizes the line, regardless of any remaining quantities. `Required` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LineNo

Line number. Used for human-readability of the fulfillment. null if the lines do not support line numbers or the line number is unknown. `Filter(multi eq;ge;le)` `Introduced in version 21.1.1.26`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LineType

Detail (line) type, for example materials, services, etc. L=Line. Other values are defined by the document entity type. `Required` `Default("L")` `Filter(multi eq)` `Introduced in version 21.1.1.26`

_Type_: **string (1)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **1**  
_Default Value_: **L**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### QuantityBase

Fulfilled quantity in the base measurement unit of the product. `Required` `Filter(multi eq;ge;le)` `Introduced in version 21.1.1.33`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StandardQuantity

The theoretical quantity according to the current measurement dimensions for the product. Used to measure the execution. `Required` `Introduced in version 22.1.4.52`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CreationUser

The user, who created the record. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Document

The Document, which is fulfilled. `Required` `Filter(multi eq)` `ReadOnly` `Introduced in version 21.1.1.26` `Owner`

_Type_: **[Documents](General.Documents.Documents.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **CannotBeShown**  

### Lot

The lot, which was fulfilled. null when the fulfillment was not for a specific lot. `Filter(multi eq)` `Introduced in version 22.1.4.52`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ParentFulfillment

The parent document fulfillment. Used when the information of the current fulfillment is inherited by another document fulfillment, usually created by another module. `Filter(multi eq)` `Introduced in version 22.1.5.85`

_Type_: **[DocumentFulfillments](General.Documents.DocumentFulfillments.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The product, which is fulfilled. `Filter(multi eq)` `Introduced in version 22.1.4.52`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductVariant

The product variant, which was fulfilled. null when the fulfillment was not for a product variant. `Filter(multi eq)` `Introduced in version 22.1.4.52`

_Type_: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SerialNumber

The serial number, which was fulfilled. null when the fulfillment was not for a specific serial number. `Filter(multi eq)` `Introduced in version 22.1.4.52`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
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

[!list limit=1000 erp.entity=General.Documents.DocumentFulfillments erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Documents.DocumentFulfillments erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Documents_DocumentFulfillments

Domain API Entity Type: 
General_Documents_DocumentFulfillment

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Documents_DocumentFulfillments?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Documents_DocumentFulfillments?$top=10>

