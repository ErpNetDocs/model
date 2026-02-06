---
uid: Logistics.Procurement.ReceivingOrderLines
---
# Logistics.Procurement.ReceivingOrderLines


Contains detail records of Receiving Orders. Each line contains the receiving of a quantity of a product.

## General
Namespace: [Logistics.Procurement](Logistics.Procurement.md)  
Repository: Logistics.Procurement.ReceivingOrderLines  
Base Table: Scm_Receiving_Order_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {ReceivingOrder.DocumentNo} {ReceivingOrder.DocumentType.TypeName:T}  
Search Members: ReceivingOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Procurement.ReceivingOrders](Logistics.Procurement.ReceivingOrders.md)  
Aggregate Root:  
[Logistics.Procurement.ReceivingOrders](Logistics.Procurement.ReceivingOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConfirmedQuantity](Logistics.Procurement.ReceivingOrderLines.md#confirmedquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | The final confirmed received quantity, after adjustments. It is used in all calculations for the order. Usually changed with adjustments to the receivemnt order, in regard to the warehouse receipt or the invoice. When null, its value is equal to Quantity. 
| [ConfirmedQuantityBase](Logistics.Procurement.ReceivingOrderLines.md#confirmedquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | The theoretical equivalence of Confirmed Quantity in base measurement unit according to the current measurement dimensions of the product. 
| [ConfirmedStandard<br />QuantityBase](Logistics.Procurement.ReceivingOrderLines.md#confirmedstandardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. NULL means to convert the value from Confirmed Quantity using the measurement ratios. 
| [CurrentBalanceBase](Logistics.Procurement.ReceivingOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [Finished](Logistics.Procurement.ReceivingOrderLines.md#finished) | boolean | Checked if this receiving order should prohibit further receiving order for the purchase order line. 
| [LineAmount](Logistics.Procurement.ReceivingOrderLines.md#lineamount) | [Amount (14, 2)](../data-types.md#amount) | The total amount for the line. Equals to Quantity * Price_Per_Unit 
| [LineNo](Logistics.Procurement.ReceivingOrderLines.md#lineno) | int32 | Line number, unique within the ReceivingOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the ReceivingOrder (in order to allow insertions with adjustment documents). `Required` 
| [Notes](Logistics.Procurement.ReceivingOrderLines.md#notes) | string (254) __nullable__ | Notes for this ReceivingOrderLine. 
| [PricePerUnit](Logistics.Procurement.ReceivingOrderLines.md#priceperunit) | [Amount (14, 5)](../data-types.md#amount) __nullable__ | The unit price of the received products, in the documents currency. 
| [ProductDescription](Logistics.Procurement.ReceivingOrderLines.md#productdescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of the received product, initially copied from the name in the product definition. The field can be edited by the user. 
| [Quantity](Logistics.Procurement.ReceivingOrderLines.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The received quantity. 
| [QuantityBase](Logistics.Procurement.ReceivingOrderLines.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Quantity, in the base measurement category of the product. 
| [StandardQuantityBase](Logistics.Procurement.ReceivingOrderLines.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Procurement.ReceivingOrderLines.md#document) | [ReceivingOrders](Logistics.Procurement.ReceivingOrders.md) | The owner document. The <see cref="ReceivingOrder"/> to which this ReceivingOrderLine belongs. `Required` `Filter(multi eq)` |
| [LineStore](Logistics.Procurement.ReceivingOrderLines.md#linestore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | Store which will receive the product from this line. |
| [Lot](Logistics.Procurement.ReceivingOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot of the received goods. |
| [Product](Logistics.Procurement.ReceivingOrderLines.md#product) | [Products](General.Products.Products.md) | The received product. |
| [ProductCode](Logistics.Procurement.ReceivingOrderLines.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Selects the product through some of the product codes |
| [ProductVariant](Logistics.Procurement.ReceivingOrderLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. |
| [PurchaseOrderLine](Logistics.Procurement.ReceivingOrderLines.md#purchaseorderline) | [PurchaseOrderLines](Logistics.Procurement.PurchaseOrderLines.md) (nullable) | The purchase order line for which we are receiving quantity. |
| [PurchaseProductPrice](Logistics.Procurement.ReceivingOrderLines.md#purchaseproductprice) | [PurchaseProductPrices](Logistics.Procurement.PurchaseProductPrices.md) (nullable) | When not NULL, specifies that the purchase unit price is loaded automatically from the specified purchase price record. |
| [QuantityUnit](Logistics.Procurement.ReceivingOrderLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. Initially copied from the Default Measurement Unit of the Product. |
| [ReceivingOrder](Logistics.Procurement.ReceivingOrderLines.md#receivingorder) | [ReceivingOrders](Logistics.Procurement.ReceivingOrders.md) | The <see cref="ReceivingOrder"/> to which this ReceivingOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [SerialNumber](Logistics.Procurement.ReceivingOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [StoreBin](Logistics.Procurement.ReceivingOrderLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | The store bin in which to receive the goods. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Procurement.ReceivingOrderLines.md#id) | guid |  
| [ObjectVersion](Logistics.Procurement.ReceivingOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Procurement.ReceivingOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConfirmedQuantity

The final confirmed received quantity, after adjustments. It is used in all calculations for the order. Usually changed with adjustments to the receivemnt order, in regard to the warehouse receipt or the invoice. When null, its value is equal to Quantity.

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### ConfirmedQuantityBase

The theoretical equivalence of Confirmed Quantity in base measurement unit according to the current measurement dimensions of the product.

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.ConfirmedQuantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConfirmedQuantityBase, obj.ConfirmedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### ConfirmedStandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. NULL means to convert the value from Confirmed Quantity using the measurement ratios.

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.ConfirmedQuantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConfirmedStandardQuantityBase, obj.ConfirmedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### Finished

Checked if this receiving order should prohibit further receiving order for the purchase order line.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **HiddenByDefault**  

### LineAmount

The total amount for the line. Equals to Quantity * Price_Per_Unit

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.ConfirmedQuantity ?? obj.Quantity) == null) OrElse ( obj.PricePerUnit == null)), obj.LineAmount, ( ( obj.ConfirmedQuantity ?? obj.Quantity).Value * obj.PricePerUnit).Round( ))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.ConfirmedQuantity ?? obj.Quantity) == null) OrElse ( obj.PricePerUnit == null)), obj.LineAmount, ( ( obj.ConfirmedQuantity ?? obj.Quantity).Value * obj.PricePerUnit).Round( ))`
### LineNo

Line number, unique within the ReceivingOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the ReceivingOrder (in order to allow insertions with adjustment documents). `Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.ReceivingOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.ReceivingOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this ReceivingOrderLine.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### PricePerUnit

The unit price of the received products, in the documents currency.

Type: **[Amount (14, 5)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.PurchaseProductPrice.GetPurchasePrice( obj.QuantityUnit, obj.ReceivingOrder.CurrencyDirectory, obj.ReceivingOrder.DocumentCurrency)`
### ProductDescription

The name of the received product, initially copied from the name in the product definition. The field can be edited by the user.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Product.Name`

Front-End Recalc Expressions:  
`obj.Product.Name`
### Quantity

The received quantity.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### QuantityBase

The equivalence of Quantity, in the base measurement category of the product.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
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

The owner document. The <see cref="ReceivingOrder"/> to which this ReceivingOrderLine belongs. `Required` `Filter(multi eq)`

Type: **[ReceivingOrders](Logistics.Procurement.ReceivingOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LineStore

Store which will receive the product from this line.

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.ReceivingOrder.Store`

Front-End Recalc Expressions:  
`obj.ReceivingOrder.Store`
### Lot

The lot of the received goods.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The received product.

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductCode

Selects the product through some of the product codes

Type: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ProductVariant

If specified determines which product variant of the current product in this line is used.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### PurchaseOrderLine

The purchase order line for which we are receiving quantity.

Type: **[PurchaseOrderLines](Logistics.Procurement.PurchaseOrderLines.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### PurchaseProductPrice

When not NULL, specifies that the purchase unit price is loaded automatically from the specified purchase price record.

Type: **[PurchaseProductPrices](Logistics.Procurement.PurchaseProductPrices.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.DeterminePurchaseProductPrice( Convert( obj.ReceivingOrder.DocumentDate, Nullable`1), obj.ReceivingOrder.Supplier, obj.Product, ( obj.ConfirmedQuantity ?? obj.Quantity), obj.ReceivingOrder.EnterpriseCompany, obj.ReceivingOrder.PurchasePriceList)`
### QuantityUnit

The measurement unit of Quantity. Initially copied from the Default Measurement Unit of the Product.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.PurchaseMeasurementUnit).IfNullThen( obj.Product.MeasurementUnit).IfNullThen( obj.QuantityUnit)`

Front-End Recalc Expressions:  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.PurchaseMeasurementUnit).IfNullThen( obj.Product.MeasurementUnit).IfNullThen( obj.QuantityUnit)`
### ReceivingOrder

The <see cref="ReceivingOrder"/> to which this ReceivingOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ReceivingOrders](Logistics.Procurement.ReceivingOrders.md)**  
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

### StoreBin

The store bin in which to receive the goods.

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
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

[!list limit=1000 erp.entity=Logistics.Procurement.ReceivingOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Procurement.ReceivingOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Procurement_ReceivingOrderLines

Domain API Entity Type: 
Logistics_Procurement_ReceivingOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Procurement_ReceivingOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Procurement_ReceivingOrderLines?$top=10>

