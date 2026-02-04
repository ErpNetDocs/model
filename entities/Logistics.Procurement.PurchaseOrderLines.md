---
uid: Logistics.Procurement.PurchaseOrderLines
---
# Logistics.Procurement.PurchaseOrderLines


Contains detail lines of purchase orders.

## General
Namespace: [Logistics.Procurement](Logistics.Procurement.md)  
Repository: Logistics.Procurement.PurchaseOrderLines  
Base Table: Scm_Purchase_Order_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {PurchaseOrder.DocumentNo} {PurchaseOrder.DocumentType.TypeName:T}  
Search Members: PurchaseOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Procurement.PurchaseOrders](Logistics.Procurement.PurchaseOrders.md)  
Aggregate Root:  
[Logistics.Procurement.PurchaseOrders](Logistics.Procurement.PurchaseOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConfirmedPricePerUnit](Logistics.Procurement.PurchaseOrderLines.md#confirmedpriceperunit) | [Amount (14, 5)](../data-types.md#amount) __nullable__ | The unit price that is confirmed by the supplier. Not to be entered if there was no order confirmation. 
| [ConfirmedQuantity](Logistics.Procurement.PurchaseOrderLines.md#confirmedquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | The quantity that is confirmed by the supplier. NULL if there was no order confirmation. 
| [ConfirmedQuantityBase](Logistics.Procurement.PurchaseOrderLines.md#confirmedquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | The theoretical equivalence of Confirmed Quantity in base measurement unit according to the current measurement dimensions of the product. 
| [ConfirmedStandard<br />QuantityBase](Logistics.Procurement.PurchaseOrderLines.md#confirmedstandardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. NULL means to convert the value from Confirmed Quantity using the measurement ratios. 
| [CurrentBalanceBase](Logistics.Procurement.PurchaseOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [LineNo](Logistics.Procurement.PurchaseOrderLines.md#lineno) | int32 | Line number, unique within the PurchaseOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the PurchaseOrder (in order to allow insertions with adjustment documents). `Required` 
| [Notes](Logistics.Procurement.PurchaseOrderLines.md#notes) | string (254) __nullable__ | Notes for this PurchaseOrderLine. 
| [ParentLineNo](Logistics.Procurement.PurchaseOrderLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. NULL when the current line does not execute line. 
| [PlannedDeliveryDate](Logistics.Procurement.PurchaseOrderLines.md#planneddeliverydate) | datetime | The planned delivery date for this line. 
| [PricePerUnit](Logistics.Procurement.PurchaseOrderLines.md#priceperunit) | [Amount (14, 5)](../data-types.md#amount) __nullable__ | The expected unit price of the ordered products, in the document currency. 
| [ProductDescription](Logistics.Procurement.PurchaseOrderLines.md#productdescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of the ordered product, initially copied from the name in the product definition. The field can be edited by the user. 
| [Quantity](Logistics.Procurement.PurchaseOrderLines.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity ordered. 
| [QuantityBase](Logistics.Procurement.PurchaseOrderLines.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Quantity, in the base measurement category of the product. 
| [StandardQuantityBase](Logistics.Procurement.PurchaseOrderLines.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Procurement.PurchaseOrderLines.md#document) | [PurchaseOrders](Logistics.Procurement.PurchaseOrders.md) | The owner document. The <see cref="PurchaseOrder"/> to which this PurchaseOrderLine belongs. `Required` `Filter(multi eq)` |
| [Lot](Logistics.Procurement.PurchaseOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | When not null, indicates that a specific lot is required to be delivered. |
| [ParentDocument](Logistics.Procurement.PurchaseOrderLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. NULL when the current line does not execute another line. |
| [Product](Logistics.Procurement.PurchaseOrderLines.md#product) | [Products](General.Products.Products.md) | The ordered product. |
| [ProductCode](Logistics.Procurement.PurchaseOrderLines.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Selects the product through some of the product codes |
| [ProductVariant](Logistics.Procurement.PurchaseOrderLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. |
| [PurchaseOrder](Logistics.Procurement.PurchaseOrderLines.md#purchaseorder) | [PurchaseOrders](Logistics.Procurement.PurchaseOrders.md) | The <see cref="PurchaseOrder"/> to which this PurchaseOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [PurchaseProductPrice](Logistics.Procurement.PurchaseOrderLines.md#purchaseproductprice) | [PurchaseProductPrices](Logistics.Procurement.PurchaseProductPrices.md) (nullable) | When not NULL, specifies that the purchase unit price is loaded automatically from the specified purchase price record. |
| [QuantityUnit](Logistics.Procurement.PurchaseOrderLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. |
| [RequisitionLine](Logistics.Procurement.PurchaseOrderLines.md#requisitionline) | [RequisitionLines](Logistics.Procurement.RequisitionLines.md) (nullable) | When not NULL, specifies that the current line is based on the specified requisition line. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Procurement.PurchaseOrderLines.md#id) | guid |  
| [ObjectVersion](Logistics.Procurement.PurchaseOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Procurement.PurchaseOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConfirmedPricePerUnit

The unit price that is confirmed by the supplier. Not to be entered if there was no order confirmation.

Type: **[Amount (14, 5)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### ConfirmedQuantity

The quantity that is confirmed by the supplier. NULL if there was no order confirmation.

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
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
`IIF( ( obj.ConfirmedQuantity == null), null, IIF( ( ( obj.QuantityUnit == null) OrElse ( obj.Product == null)), obj.ConfirmedQuantityBase, obj.ConfirmedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product)))`
### ConfirmedStandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. NULL means to convert the value from Confirmed Quantity using the measurement ratios.

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ConfirmedQuantity == null), null, IIF( ( ( obj.QuantityUnit == null) OrElse ( obj.Product == null)), obj.ConfirmedStandardQuantityBase, obj.ConfirmedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product)))`
### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### LineNo

Line number, unique within the PurchaseOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the PurchaseOrder (in order to allow insertions with adjustment documents). `Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.PurchaseOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.PurchaseOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this PurchaseOrderLine.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. NULL when the current line does not execute line.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### PlannedDeliveryDate

The planned delivery date for this line.

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.PurchaseOrder.PlannedDeliveryDate`

Front-End Recalc Expressions:  
`obj.PurchaseOrder.PlannedDeliveryDate`
### PricePerUnit

The expected unit price of the ordered products, in the document currency.

Type: **[Amount (14, 5)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.GetPurchasePriceForProductPriceUnit( obj.PurchaseProductPrice, obj.QuantityUnit)`
### ProductDescription

The name of the ordered product, initially copied from the name in the product definition. The field can be edited by the user.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Product.Name`

Front-End Recalc Expressions:  
`obj.Product.Name`
### Quantity

The quantity ordered.

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
Default Value: **Constant**  
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

The owner document. The <see cref="PurchaseOrder"/> to which this PurchaseOrderLine belongs. `Required` `Filter(multi eq)`

Type: **[PurchaseOrders](Logistics.Procurement.PurchaseOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

When not null, indicates that a specific lot is required to be delivered.

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

The ordered product.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.ProductCode.Product`
### ProductCode

Selects the product through some of the product codes

Type: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.ProductCode != null) AndAlso ( obj.Product != obj.ProductCode.Product)), null, obj.ProductCode)`
### ProductVariant

If specified determines which product variant of the current product in this line is used.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### PurchaseOrder

The <see cref="PurchaseOrder"/> to which this PurchaseOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[PurchaseOrders](Logistics.Procurement.PurchaseOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### PurchaseProductPrice

When not NULL, specifies that the purchase unit price is loaded automatically from the specified purchase price record.

Type: **[PurchaseProductPrices](Logistics.Procurement.PurchaseProductPrices.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.DeterminePurchaseProductPrice( Convert( obj.PurchaseOrder.DocumentDate, Nullable`1), obj.PurchaseOrder.Supplier, obj.Product, obj.Quantity, obj.PurchaseOrder.EnterpriseCompany, obj.PurchaseOrder.PurchasePriceList)`
### QuantityUnit

The measurement unit of Quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.PurchaseMeasurementUnit).IfNullThen( obj.Product.MeasurementUnit).IfNullThen( obj.QuantityUnit)`
### RequisitionLine

When not NULL, specifies that the current line is based on the specified requisition line.

Type: **[RequisitionLines](Logistics.Procurement.RequisitionLines.md) (nullable)**  
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

[!list limit=1000 erp.entity=Logistics.Procurement.PurchaseOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Procurement.PurchaseOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Procurement_PurchaseOrderLines

Domain API Entity Type: 
Logistics_Procurement_PurchaseOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Procurement_PurchaseOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Procurement_PurchaseOrderLines?$top=10>

