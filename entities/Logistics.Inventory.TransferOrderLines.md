---
uid: Logistics.Inventory.TransferOrderLines
---
# Logistics.Inventory.TransferOrderLines


Details of Transfer Orders. Each line contains order for the movement of one product.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.TransferOrderLines  
Base Table: Inv_Transfer_Order_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineOrd}. {TransferOrder.DocumentNo} {TransferOrder.DocumentType.TypeName:T}  
Search Members: TransferOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Inventory.TransferOrders](Logistics.Inventory.TransferOrders.md)  
Aggregate Root:  
[Logistics.Inventory.TransferOrders](Logistics.Inventory.TransferOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrentBalanceBase](Logistics.Inventory.TransferOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DueDateIn](Logistics.Inventory.TransferOrderLines.md#duedatein) | datetime | The date, when the goods are expected to be received in the destination warehouse. Initially copied from the transfer header[Required] [Filter(ge;le)] 
| [DueDateOut](Logistics.Inventory.TransferOrderLines.md#duedateout) | datetime | When this line of the transfer is scheduled to issue the goods from the source warehouse. Initially copied from the transfer header[Required] [Filter(ge;le)] 
| [LineOrd](Logistics.Inventory.TransferOrderLines.md#lineord) | int32 | Line ordinal position within the transaction. Duplicates are allowed, but not advised[Required] 
| [Notes](Logistics.Inventory.TransferOrderLines.md#notes) | string (254) __nullable__ | Notes for this TransferOrderLine. 
| [Quantity](Logistics.Inventory.TransferOrderLines.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity ordered for transfer[Unit: QuantityUnit] [Required] [Default(1)] [Filter(ge;le)] 
| [QuantityBase](Logistics.Inventory.TransferOrderLines.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity in the base (default) measurement unit of the Item (calculated at the time of last update of the current store order line). Should be updated in parallel with each Quantity update[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Filter(ge;le)] 
| [StandardQuantityBase](Logistics.Inventory.TransferOrderLines.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [ReadOnly] [Introduced in version 18.2] 
| [StandardUnitPrice](Logistics.Inventory.TransferOrderLines.md#standardunitprice) | [Amount (14, 5)](../data-types.md#amount) __nullable__ | Standard unit price of the product during the creation of the transfer order line[Currency: TransferOrder.DocumentCurrency] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Inventory.TransferOrderLines.md#document) | [TransferOrders](Logistics.Inventory.TransferOrders.md) | The owner document. The parent transfer order. `Required` `Filter(multi eq)` |
| [FromStoreBin](Logistics.Inventory.TransferOrderLines.md#fromstorebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | From which store bin to issue/receive the products. NULL means that the store bin is unknown or not applicable |
| [Lot](Logistics.Inventory.TransferOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If non-null, contains the specific lot to use for the movement |
| [Product](Logistics.Inventory.TransferOrderLines.md#product) | [Products](General.Products.Products.md) | The product which will be transferred |
| [ProductCode](Logistics.Inventory.TransferOrderLines.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Selects the product through some of the product codes. |
| [ProductVariant](Logistics.Inventory.TransferOrderLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. |
| [QuantityUnit](Logistics.Inventory.TransferOrderLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity |
| [SerialNumber](Logistics.Inventory.TransferOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [ToStoreBin](Logistics.Inventory.TransferOrderLines.md#tostorebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | To which store bin to issue/receive the products. NULL means that the store bin is unknown or not applicable |
| [TransferOrder](Logistics.Inventory.TransferOrderLines.md#transferorder) | [TransferOrders](Logistics.Inventory.TransferOrders.md) | The parent transfer order |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.TransferOrderLines.md#id) | guid |  
| [ObjectVersion](Logistics.Inventory.TransferOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Inventory.TransferOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### DueDateIn

The date, when the goods are expected to be received in the destination warehouse. Initially copied from the transfer header[Required] [Filter(ge;le)]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.TransferOrder.DefaultDueDateIn`

Front-End Recalc Expressions:  
`obj.TransferOrder.DefaultDueDateIn`
### DueDateOut

When this line of the transfer is scheduled to issue the goods from the source warehouse. Initially copied from the transfer header[Required] [Filter(ge;le)]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.TransferOrder.DefaultDueDateOut`

Front-End Recalc Expressions:  
`obj.TransferOrder.DefaultDueDateOut`
### LineOrd

Line ordinal position within the transaction. Duplicates are allowed, but not advised[Required]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.TransferOrder.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.TransferOrder.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this TransferOrderLine.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### Quantity

Quantity ordered for transfer[Unit: QuantityUnit] [Required] [Default(1)] [Filter(ge;le)]

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### QuantityBase

Quantity in the base (default) measurement unit of the Item (calculated at the time of last update of the current store order line). Should be updated in parallel with each Quantity update[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Filter(ge;le)]

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

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [ReadOnly] [Introduced in version 18.2]

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardUnitPrice

Standard unit price of the product during the creation of the transfer order line[Currency: TransferOrder.DocumentCurrency]

Type: **[Amount (14, 5)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.Product != null) AndAlso ( obj.QuantityUnit != null)), obj.Product.GetStandardUnitPrice( obj.QuantityUnit, obj.TransferOrder.ToStore.Currency, obj.TransferOrder.CurrencyDirectory), obj.StandardUnitPrice)`
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

The owner document. The parent transfer order. `Required` `Filter(multi eq)`

Type: **[TransferOrders](Logistics.Inventory.TransferOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### FromStoreBin

From which store bin to issue/receive the products. NULL means that the store bin is unknown or not applicable

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Lot

If non-null, contains the specific lot to use for the movement

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The product which will be transferred

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.ProductCode.Product.IfNullThen( obj.Product)`
### ProductCode

Selects the product through some of the product codes.

Type: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Product != null) AndAlso ( obj.ProductCode != null)) AndAlso ( obj.Product != obj.ProductCode.Product)), null, obj.ProductCode)`
### ProductVariant

If specified determines which product variant of the current product in this line is used.

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
### SerialNumber

Serial number of the product. NULL means that the serial number is unknown or not applicable.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ToStoreBin

To which store bin to issue/receive the products. NULL means that the store bin is unknown or not applicable

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### TransferOrder

The parent transfer order

Type: **[TransferOrders](Logistics.Inventory.TransferOrders.md)**  
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

[!list limit=1000 erp.entity=Logistics.Inventory.TransferOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.TransferOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Inventory_TransferOrderLines

Domain API Entity Type: 
Logistics_Inventory_TransferOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_TransferOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_TransferOrderLines?$top=10>

