---
uid: Logistics.Wms.WarehouseRequisitionLines
---
# Logistics.Wms.WarehouseRequisitionLines


Request for one product with a warehouse requisition.

## General
Namespace: [Logistics.Wms](Logistics.Wms.md)  
Repository: Logistics.Wms.WarehouseRequisitionLines  
Base Table: Wms_Warehouse_Requisition_Lines  
Introduced In Version: 20.1  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {WarehouseRequisition.DocumentNo} {WarehouseRequisition.DocumentType.TypeName:T}  
Search Members: WarehouseRequisition.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Wms.WarehouseRequisitions](Logistics.Wms.WarehouseRequisitions.md)  
Aggregate Root:  
[Logistics.Wms.WarehouseRequisitions](Logistics.Wms.WarehouseRequisitions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrentBalanceBase](Logistics.Wms.WarehouseRequisitionLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [LineNo](Logistics.Wms.WarehouseRequisitionLines.md#lineno) | int32 | The unique, consecutive line number within the requisition. 
| [Notes](Logistics.Wms.WarehouseRequisitionLines.md#notes) | string (max) __nullable__ | Notes for this WarehouseRequisitionLine. 
| [ParentLineNo](Logistics.Wms.WarehouseRequisitionLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. NULL when the current line does not execute line. 
| [Quantity](Logistics.Wms.WarehouseRequisitionLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The requested quantity. 
| [QuantityBase](Logistics.Wms.WarehouseRequisitionLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | Quantity in the base measurement unit of the product. 
| [StandardQuantity](Logistics.Wms.WarehouseRequisitionLines.md#standardquantity) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Wms.WarehouseRequisitionLines.md#document) | [WarehouseRequisitions](Logistics.Wms.WarehouseRequisitions.md) | The owner document. The <see cref="Warehouse<br />Requisition"/> to which this WarehouseRequisitionLine belongs. `Required` `Filter(multi eq)` |
| [Lot](Logistics.Wms.WarehouseRequisitionLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The requested lot. NULL means that any lot can be used or the product does not use lots at all. |
| [ParentDocument](Logistics.Wms.WarehouseRequisitionLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. NULL when the current line does not execute another line. |
| [Product](Logistics.Wms.WarehouseRequisitionLines.md#product) | [Products](General.Products.Products.md) | The requested product. |
| [ProductVariant](Logistics.Wms.WarehouseRequisitionLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | The requested product variant. |
| [QuantityUnit](Logistics.Wms.WarehouseRequisitionLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. |
| [SerialNumber](Logistics.Wms.WarehouseRequisitionLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [WarehouseRequisition](Logistics.Wms.WarehouseRequisitionLines.md#warehouserequisition) | [WarehouseRequisitions](Logistics.Wms.WarehouseRequisitions.md) | The <see cref="Warehouse<br />Requisition"/> to which this WarehouseRequisitionLine belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Wms.WarehouseRequisitionLines.md#id) | guid |  
| [ObjectVersion](Logistics.Wms.WarehouseRequisitionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Wms.WarehouseRequisitionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### LineNo

The unique, consecutive line number within the requisition.

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.WarehouseRequisition.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.WarehouseRequisition.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this WarehouseRequisitionLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. NULL when the current line does not execute line.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Quantity

The requested quantity.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### QuantityBase

Quantity in the base measurement unit of the product.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantity

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantity, IIF( obj.Product.AllowVariableMeasurementRatios, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.QuantityBase))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantity, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
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

The owner document. The <see cref="WarehouseRequisition"/> to which this WarehouseRequisitionLine belongs. `Required` `Filter(multi eq)`

Type: **[WarehouseRequisitions](Logistics.Wms.WarehouseRequisitions.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

The requested lot. NULL means that any lot can be used or the product does not use lots at all.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ParentDocument

The document, which the current line executes. NULL when the current line does not execute another line.

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The requested product.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductVariant

The requested product variant.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### QuantityUnit

The measurement unit of Quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Product.MeasurementUnit`
### SerialNumber

Serial number of the product. NULL means that the serial number is unknown or not applicable.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### WarehouseRequisition

The <see cref="WarehouseRequisition"/> to which this WarehouseRequisitionLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[WarehouseRequisitions](Logistics.Wms.WarehouseRequisitions.md)**  
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

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseRequisitionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseRequisitionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Wms_WarehouseRequisitionLines

Domain API Entity Type: 
Logistics_Wms_WarehouseRequisitionLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseRequisitionLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseRequisitionLines?$top=10>

