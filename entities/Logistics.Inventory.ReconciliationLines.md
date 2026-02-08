---
uid: Logistics.Inventory.ReconciliationLines
---
# Logistics.Inventory.ReconciliationLines


Store reconciliations (physical counting) detail lines. Each line contains the reconciliation for one combination of product, lot, bin and serial number.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.ReconciliationLines  
Base Table: Inv_Reconciliation_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineOrd}. {Reconciliation.DocumentNo} {Reconciliation.DocumentType.TypeName:T}  
Search Members: Reconciliation.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Inventory.Reconciliations](Logistics.Inventory.Reconciliations.md)  
Aggregate Root:  
[Logistics.Inventory.Reconciliations](Logistics.Inventory.Reconciliations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AvailableQuantityBase](Logistics.Inventory.ReconciliationLines.md#availablequantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Available quantity (in base measurement unit) to the date of the reconciliation.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` 
| [CurrentBalanceBase](Logistics.Inventory.ReconciliationLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [LineOrd](Logistics.Inventory.ReconciliationLines.md#lineord) | int32 | The ordinal position of the line within the document. Duplicates are allowed, but not suggested`Required` 
| [Notes](Logistics.Inventory.ReconciliationLines.md#notes) | string (254) __nullable__ | Notes for this ReconciliationLine. 
| [Quantity](Logistics.Inventory.ReconciliationLines.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity found at the reconciliation, `Unit: QuantityUnit` `Required` `Filter(ge;le)` 
| [QuantityBase](Logistics.Inventory.ReconciliationLines.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity found at the reconciliation, expressed in base measurement units`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(ge;le)` 
| [StandardQuantityBase](Logistics.Inventory.ReconciliationLines.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [TransactionTimestamp](Logistics.Inventory.ReconciliationLines.md#transactiontimestamp) | datetime __nullable__ | Exact time when the transaction changes the cost of the product.`Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Inventory.ReconciliationLines.md#document) | [Reconciliations](Logistics.Inventory.Reconciliations.md) | The owner document. Parent reconciliation Id. `Required` `Filter(multi eq)` |
| [Lot](Logistics.Inventory.ReconciliationLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot, which was reconciled. |
| [Product](Logistics.Inventory.ReconciliationLines.md#product) | [Products](General.Products.Products.md) | The id of the reconciled product |
| [ProductCode](Logistics.Inventory.ReconciliationLines.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Selects the product thru some of the product codes. |
| [ProductVariant](Logistics.Inventory.ReconciliationLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | The product variant, which was reconciled. |
| [QuantityUnit](Logistics.Inventory.ReconciliationLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity |
| [Reconciliation](Logistics.Inventory.ReconciliationLines.md#reconciliation) | [Reconciliations](Logistics.Inventory.Reconciliations.md) | Parent reconciliation Id |
| [SerialNumber](Logistics.Inventory.ReconciliationLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [Store](Logistics.Inventory.ReconciliationLines.md#store) | [Stores](Logistics.Inventory.Stores.md) | The store, containing the reconciled product |
| [StoreBin](Logistics.Inventory.ReconciliationLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | The store bin, that was counted |
| [WarehouseTransaction](Logistics.Inventory.ReconciliationLines.md#warehousetransaction) | [WarehouseTransactions](Logistics.Wms.WarehouseTransactions.md) (nullable) | The warehouse operation, whose result is reflected in the current line. Null when the reconciliation line is not a result of the counting warehouse operations in the Warehouse Management module. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.ReconciliationLines.md#id) | guid |  
| [ObjectVersion](Logistics.Inventory.ReconciliationLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Inventory.ReconciliationLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AvailableQuantityBase

Available quantity (in base measurement unit) to the date of the reconciliation.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### LineOrd

The ordinal position of the line within the document. Duplicates are allowed, but not suggested`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Reconciliation.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.Reconciliation.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this ReconciliationLine.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### Quantity

Quantity found at the reconciliation, `Unit: QuantityUnit` `Required` `Filter(ge;le)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### QuantityBase

Quantity found at the reconciliation, expressed in base measurement units`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(ge;le)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### TransactionTimestamp

Exact time when the transaction changes the cost of the product.`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

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

The owner document. Parent reconciliation Id. `Required` `Filter(multi eq)`

Type: **[Reconciliations](Logistics.Inventory.Reconciliations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

The lot, which was reconciled.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The id of the reconciled product

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.ProductCode.Product.IfNullThen( obj.Product)`
### ProductCode

Selects the product thru some of the product codes.

Type: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Product != null) AndAlso ( obj.ProductCode != null)) AndAlso ( obj.Product != obj.ProductCode.Product)), null, obj.ProductCode)`
### ProductVariant

The product variant, which was reconciled.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### QuantityUnit

The measurement unit of Quantity

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.MeasurementUnit.IfNullThen( obj.QuantityUnit))`
### Reconciliation

Parent reconciliation Id

Type: **[Reconciliations](Logistics.Inventory.Reconciliations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### SerialNumber

Serial number of the product. NULL means that the serial number is unknown or not applicable.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( Not( obj.Product.IsSerialized) OrElse ( ( obj.SerialNumber != null) AndAlso ( obj.Product != obj.SerialNumber.Product))), null, obj.SerialNumber)`
### Store

The store, containing the reconciled product

Type: **[Stores](Logistics.Inventory.Stores.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Reconciliation.DefaultStore.IfNullThen( obj.Store)`
### StoreBin

The store bin, that was counted

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Reconciliation.DefaultStoreBin.IfNullThen( obj.StoreBin)`
### WarehouseTransaction

The warehouse operation, whose result is reflected in the current line. Null when the reconciliation line is not a result of the counting warehouse operations in the Warehouse Management module.

Type: **[WarehouseTransactions](Logistics.Wms.WarehouseTransactions.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  


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

[!list limit=1000 erp.entity=Logistics.Inventory.ReconciliationLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.ReconciliationLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Inventory_ReconciliationLines

Domain API Entity Type: 
Logistics_Inventory_ReconciliationLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_ReconciliationLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_ReconciliationLines?$top=10>

