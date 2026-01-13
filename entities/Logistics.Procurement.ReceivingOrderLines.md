---
uid: Logistics.Procurement.ReceivingOrderLines
---
# Logistics.Procurement.ReceivingOrderLines Entity

**Namespace:** [Logistics.Procurement](Logistics.Procurement.md)  

Contains detail records of Receiving Orders. Each line contains the receiving of a quantity of a product. Entity: Scm_Receiving_Order_Lines

## Default Visualization
Default Display Text Format:  
_{LineNo}. {ReceivingOrder.DocumentNo} {ReceivingOrder.DocumentType.TypeName:T}_  
Default Search Members:  
_ReceivingOrder.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Procurement.ReceivingOrders](Logistics.Procurement.ReceivingOrders.md)  
Aggregate Root:  
[Logistics.Procurement.ReceivingOrders](Logistics.Procurement.ReceivingOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConfirmedQuantity](Logistics.Procurement.ReceivingOrderLines.md#confirmedquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | The final confirmed received quantity, after adjustments. It is used in all calculations for the order. Usually changed with adjustments to the receivemnt order, in regard to the warehouse receipt or the invoice. When null, its value is equal to Quantity. `Unit: QuantityUnit` 
| [ConfirmedQuantityBase](Logistics.Procurement.ReceivingOrderLines.md#confirmedquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | The theoretical equivalence of Confirmed Quantity in base measurement unit according to the current measurement dimensions of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` 
| [ConfirmedStandard<br />QuantityBase](Logistics.Procurement.ReceivingOrderLines.md#confirmedstandardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. null means to convert the value from Confirmed Quantity using the measurement ratios. `Unit: Product.BaseMeasurementCategory.BaseUnit` `ReadOnly` `Introduced in version 18.2` 
| [CurrentBalanceBase](Logistics.Procurement.ReceivingOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DisplayText](Logistics.Procurement.ReceivingOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Finished](Logistics.Procurement.ReceivingOrderLines.md#finished) | boolean | When true, denotes that this is the last receivement for this purchase order line and further receivements are not expected. `Required` `Default(false)` 
| [Id](Logistics.Procurement.ReceivingOrderLines.md#id) | guid |  
| [LineAmount](Logistics.Procurement.ReceivingOrderLines.md#lineamount) | [Amount (14, 2)](../data-types.md#amount) | The total amount for the line. Equals to Quantity * Price_Per_Unit. `Currency: ReceivingOrder.DocumentCurrency` `Required` `Default(0)` 
| [LineNo](Logistics.Procurement.ReceivingOrderLines.md#lineno) | int32 | Line number, unique within the ReceivingOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the ReceivingOrder (in order to allow insertions with adjustment documents). `Required` 
| [Notes](Logistics.Procurement.ReceivingOrderLines.md#notes) | string (254) __nullable__ | Notes for this ReceivingOrderLine. 
| [ObjectVersion](Logistics.Procurement.ReceivingOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PricePerUnit](Logistics.Procurement.ReceivingOrderLines.md#priceperunit) | [Amount (14, 5)](../data-types.md#amount) __nullable__ | The unit price of the received products, in the documents currency. `Currency: ReceivingOrder.DocumentCurrency` `Default(0)` 
| [ProductDescription](Logistics.Procurement.ReceivingOrderLines.md#productdescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of the received product, initially copied from the name in the product definition. The field can be edited by the user. `Required` 
| [Quantity](Logistics.Procurement.ReceivingOrderLines.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The received quantity. `Unit: QuantityUnit` `Required` `Default(1)` `Filter(ge;le)` 
| [QuantityBase](Logistics.Procurement.ReceivingOrderLines.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Quantity, in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` 
| [StandardQuantityBase](Logistics.Procurement.ReceivingOrderLines.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Procurement.ReceivingOrderLines.md#document) | [ReceivingOrders](Logistics.Procurement.ReceivingOrders.md) | The owner document. The <see cref="ReceivingOrder"/> to which this ReceivingOrderLine belongs. `Required` `Filter(multi eq)` |
| [LineStore](Logistics.Procurement.ReceivingOrderLines.md#linestore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store in which the goods are received. `Filter(multi eq)` |
| [Lot](Logistics.Procurement.ReceivingOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot of the received goods. `Filter(multi eq)` |
| [Product](Logistics.Procurement.ReceivingOrderLines.md#product) | [Products](General.Products.Products.md) | The received product. `Required` `Filter(multi eq)` |
| [ProductCode](Logistics.Procurement.ReceivingOrderLines.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | When not null, specifies that the product was selected using the specified product code record. `Filter(multi eq)` |
| [ProductVariant](Logistics.Procurement.ReceivingOrderLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. `Filter(multi eq)` |
| [PurchaseOrderLine](Logistics.Procurement.ReceivingOrderLines.md#purchaseorderline) | [PurchaseOrderLines](Logistics.Procurement.PurchaseOrderLines.md) (nullable) | The purchase order line for which we are receiving quantity. `Filter(multi eq)` |
| [PurchaseProductPrice](Logistics.Procurement.ReceivingOrderLines.md#purchaseproductprice) | [PurchaseProductPrices](Logistics.Procurement.PurchaseProductPrices.md) (nullable) | When not null, specifies that the purchase unit price is loaded automatically from the specified purchase price record. `Filter(multi eq)` |
| [QuantityUnit](Logistics.Procurement.ReceivingOrderLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. Initially copied from the Default Measurement Unit of the Product. `Required` `Filter(multi eq)` |
| [ReceivingOrder](Logistics.Procurement.ReceivingOrderLines.md#receivingorder) | [ReceivingOrders](Logistics.Procurement.ReceivingOrders.md) | The <see cref="ReceivingOrder"/> to which this ReceivingOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [SerialNumber](Logistics.Procurement.ReceivingOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Which serial number to receive/issue. null means that serial number is unknown or not applicable. `Filter(multi eq)` |
| [StoreBin](Logistics.Procurement.ReceivingOrderLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | The store bin in which to receive the goods. `Filter(multi eq)` |


## Attribute Details

### ConfirmedQuantity

The final confirmed received quantity, after adjustments. It is used in all calculations for the order. Usually changed with adjustments to the receivemnt order, in regard to the warehouse receipt or the invoice. When null, its value is equal to Quantity. `Unit: QuantityUnit`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### ConfirmedQuantityBase

The theoretical equivalence of Confirmed Quantity in base measurement unit according to the current measurement dimensions of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.ConfirmedQuantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConfirmedQuantityBase, obj.ConfirmedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### ConfirmedStandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. null means to convert the value from Confirmed Quantity using the measurement ratios. `Unit: Product.BaseMeasurementCategory.BaseUnit` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.ConfirmedQuantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConfirmedStandardQuantityBase, obj.ConfirmedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

_Type_: **[Quantity](../data-types.md#quantity)**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Finished

When true, denotes that this is the last receivement for this purchase order line and further receivements are not expected. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineAmount

The total amount for the line. Equals to Quantity * Price_Per_Unit. `Currency: ReceivingOrder.DocumentCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.ConfirmedQuantity ?? obj.Quantity) == null) OrElse ( obj.PricePerUnit == null)), obj.LineAmount, ( ( obj.ConfirmedQuantity ?? obj.Quantity).Value * obj.PricePerUnit).Round( ))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.ConfirmedQuantity ?? obj.Quantity) == null) OrElse ( obj.PricePerUnit == null)), obj.LineAmount, ( ( obj.ConfirmedQuantity ?? obj.Quantity).Value * obj.PricePerUnit).Round( ))`
### LineNo

Line number, unique within the ReceivingOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the ReceivingOrder (in order to allow insertions with adjustment documents). `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.ReceivingOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.ReceivingOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this ReceivingOrderLine.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PricePerUnit

The unit price of the received products, in the documents currency. `Currency: ReceivingOrder.DocumentCurrency` `Default(0)`

_Type_: **[Amount (14, 5)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.PurchaseProductPrice.GetPurchasePrice( obj.QuantityUnit, obj.ReceivingOrder.CurrencyDirectory, obj.ReceivingOrder.DocumentCurrency)`
### ProductDescription

The name of the received product, initially copied from the name in the product definition. The field can be edited by the user. `Required`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.Product.Name`

_Front-End Recalc Expressions:_  
`obj.Product.Name`
### Quantity

The received quantity. `Unit: QuantityUnit` `Required` `Default(1)` `Filter(ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

The equivalence of Quantity, in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

## Reference Details

### Document

The owner document. The <see cref="ReceivingOrder"/> to which this ReceivingOrderLine belongs. `Required` `Filter(multi eq)`

_Type_: **[ReceivingOrders](Logistics.Procurement.ReceivingOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LineStore

The store in which the goods are received. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.ReceivingOrder.Store`

_Front-End Recalc Expressions:_  
`obj.ReceivingOrder.Store`
### Lot

The lot of the received goods. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Product

The received product. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductCode

When not null, specifies that the product was selected using the specified product code record. `Filter(multi eq)`

_Type_: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### ProductVariant

If specified determines which product variant of the current product in this line is used. `Filter(multi eq)`

_Type_: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### PurchaseOrderLine

The purchase order line for which we are receiving quantity. `Filter(multi eq)`

_Type_: **[PurchaseOrderLines](Logistics.Procurement.PurchaseOrderLines.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### PurchaseProductPrice

When not null, specifies that the purchase unit price is loaded automatically from the specified purchase price record. `Filter(multi eq)`

_Type_: **[PurchaseProductPrices](Logistics.Procurement.PurchaseProductPrices.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.DeterminePurchaseProductPrice( Convert( obj.ReceivingOrder.DocumentDate, Nullable`1), obj.ReceivingOrder.Supplier, obj.Product, ( obj.ConfirmedQuantity ?? obj.Quantity), obj.ReceivingOrder.EnterpriseCompany, obj.ReceivingOrder.PurchasePriceList)`
### QuantityUnit

The measurement unit of Quantity. Initially copied from the Default Measurement Unit of the Product. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.PurchaseMeasurementUnit).IfNullThen( obj.Product.MeasurementUnit).IfNullThen( obj.QuantityUnit)`

_Front-End Recalc Expressions:_  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.PurchaseMeasurementUnit).IfNullThen( obj.Product.MeasurementUnit).IfNullThen( obj.QuantityUnit)`
### ReceivingOrder

The <see cref="ReceivingOrder"/> to which this ReceivingOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ReceivingOrders](Logistics.Procurement.ReceivingOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### SerialNumber

Which serial number to receive/issue. null means that serial number is unknown or not applicable. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### StoreBin

The store bin in which to receive the goods. `Filter(multi eq)`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  


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

