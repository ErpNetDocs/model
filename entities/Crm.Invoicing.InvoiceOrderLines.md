---
uid: Crm.Invoicing.InvoiceOrderLines
---
# Crm.Invoicing.InvoiceOrderLines


Detail records (lines) of Invoice Orders

## General
Namespace: [Crm.Invoicing](Crm.Invoicing.md)  
Repository: Crm.Invoicing.InvoiceOrderLines  
Base Table: Crm_Invoice_Order_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {InvoiceOrder.DocumentNo} {InvoiceOrder.DocumentType.TypeName:T}  
Search Members: InvoiceOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Invoicing.InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)  
Aggregate Root:  
[Crm.Invoicing.InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BusinessReason](Crm.Invoicing.InvoiceOrderLines.md#businessreason) | [InvoicingBusinessReason](Crm.Invoicing.InvoiceOrderLines.md#businessreason) | Business reason for invoicing of this product or service. S=Shipment, P=Payment[Required] [Default(&quot;S&quot;)] 
| [CurrentBalanceBase](Crm.Invoicing.InvoiceOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [LineAmount](Crm.Invoicing.InvoiceOrderLines.md#lineamount) | [Amount (14, 2)](../data-types.md#amount) | Amount for the line in the currency of the parent document. Usually equals Quantity * Unit_Price. When Quantity = 0, Unit Price is undefined and this contains the total line amount.[Currency: InvoiceOrder.DocumentCurrency] [Required] [Default(0)] 
| [LineCustomDiscountPercent](Crm.Invoicing.InvoiceOrderLines.md#linecustomdiscountpercent) | decimal (7, 6) | User-defined discount for the line[Required] [Default(0)] 
| [LineNo](Crm.Invoicing.InvoiceOrderLines.md#lineno) | int32 | Line number, unique within the InvoiceOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the InvoiceOrder (in order to allow insertions with adjustment documents). `Required` 
| [LineStandardDiscount<br />Percent](Crm.Invoicing.InvoiceOrderLines.md#linestandarddiscountpercent) | decimal (7, 6) | Standard discount for the line. This is automatically computed according to discount conditions[Required] [Default(0)] 
| [ProductDescription](Crm.Invoicing.InvoiceOrderLines.md#productdescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The description of Product. Initially copied from the name of the Product or from the generating document.[Required] 
| [Quantity](Crm.Invoicing.InvoiceOrderLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity of the product to invoice[Unit: QuantityUnit] [Required] [Default(1)] [Filter(ge;le)] 
| [QuantityBase](Crm.Invoicing.InvoiceOrderLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The equivalent of Quantity in the base measurement unit of the Product[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] 
| [StandardQuantityBase](Crm.Invoicing.InvoiceOrderLines.md#standardquantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [ReadOnly] [Introduced in version 18.2] 
| [UnitPrice](Crm.Invoicing.InvoiceOrderLines.md#unitprice) | [Amount (14, 5)](../data-types.md#amount) | Unit selling price in the unit of measure, specified in Quantity Unit[Currency: InvoiceOrder.DocumentCurrency] [Required] [Default(0)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Crm.Invoicing.InvoiceOrderLines.md#document) | [InvoiceOrders](Crm.Invoicing.InvoiceOrders.md) | The owner document. The <see cref="InvoiceOrder"/> to which this InvoiceOrderLine belongs. `Required` `Filter(multi eq)` |
| [InvoiceOrder](Crm.Invoicing.InvoiceOrderLines.md#invoiceorder) | [InvoiceOrders](Crm.Invoicing.InvoiceOrders.md) | The <see cref="InvoiceOrder"/> to which this InvoiceOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [LineDealType](Crm.Invoicing.InvoiceOrderLines.md#linedealtype) | [DealTypes](Regulatory.Vat.DealTypes.md) (nullable) | Deal type to be passed to the invoice line. If deal type in the line is different from deal type in the header another VAT entry is created from the invoice. |
| [LineDiscount](Crm.Invoicing.InvoiceOrderLines.md#linediscount) | [LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable) | The line discount type used to form the Line_Standard_<br />Discount_Percent |
| [PaymentTransaction](Crm.Invoicing.InvoiceOrderLines.md#paymenttransaction) | [PaymentTransactions](Finance.Payments.PaymentTransactions.md) (nullable) | The payment transaction, which is to be invoiced by this line, when Business Reason = P. Used to reconcile the invoice with the payments in the case of advance payment. |
| [Product](Crm.Invoicing.InvoiceOrderLines.md#product) | [Products](General.Products.Products.md) (nullable) | The product, which is ordered for invoicing |
| [QuantityUnit](Crm.Invoicing.InvoiceOrderLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity |
| [SalesOrder](Crm.Invoicing.InvoiceOrderLines.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) (nullable) | When not NULL specifies the Sales Order that is ordered to be invoiced by this line |
| [SalesOrderLine](Crm.Invoicing.InvoiceOrderLines.md#salesorderline) | [SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable) | When not NULL specifies the Sales Order line that is ordered to be invoiced by this line |
| [SerialNumber](Crm.Invoicing.InvoiceOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [TransactionLine](Crm.Invoicing.InvoiceOrderLines.md#transactionline) | [StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable) | The store transaction line that is to be invoiced by this line, for Business Reason = S |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Invoicing.InvoiceOrderLines.md#id) | guid |  
| [ObjectVersion](Crm.Invoicing.InvoiceOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Invoicing.InvoiceOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BusinessReason

Business reason for invoicing of this product or service. S=Shipment, P=Payment[Required] [Default(&quot;S&quot;)]

Type: **[InvoicingBusinessReason](Crm.Invoicing.InvoiceOrderLines.md#businessreason)**  
Category: **System**  
Generic enum type for InvoicingBusinessReason properties  
Allowed Values (Crm.Invoicing.InvoicingBusinessReason Enum Members)  

| Value | Description |
| ---- | --- |
| Payment | Payment value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 0 <br /> Domain API Value: 'Payment' |
| Shipment | Shipment value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 1 <br /> Domain API Value: 'Shipment' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Shipment**  
Show in UI: **HiddenByDefault**  

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### LineAmount

Amount for the line in the currency of the parent document. Usually equals Quantity * Unit_Price. When Quantity = 0, Unit Price is undefined and this contains the total line amount.[Currency: InvoiceOrder.DocumentCurrency] [Required] [Default(0)]

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.CalculateLineAmount( obj.Quantity, obj.UnitPrice, Convert( obj.LineCustomDiscountPercent, Nullable`1), Convert( obj.LineStandardDiscountPercent, Nullable`1), obj.InvoiceOrder.DocumentCurrency)`
### LineCustomDiscountPercent

User-defined discount for the line[Required] [Default(0)]

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### LineNo

Line number, unique within the InvoiceOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the InvoiceOrder (in order to allow insertions with adjustment documents). `Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.InvoiceOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.InvoiceOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineStandardDiscountPercent

Standard discount for the line. This is automatically computed according to discount conditions[Required] [Default(0)]

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.LineDiscount != null), obj.LineDiscount.DiscountPercent, 0)`
### ProductDescription

The description of Product. Initially copied from the name of the Product or from the generating document.[Required]

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Product.Name`
### Quantity

The quantity of the product to invoice[Unit: QuantityUnit] [Required] [Default(1)] [Filter(ge;le)]

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### QuantityBase

The equivalent of Quantity in the base measurement unit of the Product[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required]

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [ReadOnly] [Introduced in version 18.2]

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### UnitPrice

Unit selling price in the unit of measure, specified in Quantity Unit[Currency: InvoiceOrder.DocumentCurrency] [Required] [Default(0)]

Type: **[Amount (14, 5)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.CalculateUnitPrice( obj.InvoiceOrder, obj.Product)`
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

The owner document. The <see cref="InvoiceOrder"/> to which this InvoiceOrderLine belongs. `Required` `Filter(multi eq)`

Type: **[InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### InvoiceOrder

The <see cref="InvoiceOrder"/> to which this InvoiceOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### LineDealType

Deal type to be passed to the invoice line. If deal type in the line is different from deal type in the header another VAT entry is created from the invoice.

Type: **[DealTypes](Regulatory.Vat.DealTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.InvoiceOrder.DealType`

Front-End Recalc Expressions:  
`obj.InvoiceOrder.DealType`
### LineDiscount

The line discount type used to form the Line_Standard_Discount_Percent

Type: **[LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.DetermineLineDiscount( Convert( ( obj.InvoiceOrder.DeliveryDate ?? obj.InvoiceOrder.DocumentDate), Nullable`1), obj.InvoiceOrder.Customer, obj.Product, obj.Quantity, obj.InvoiceOrder.EnterpriseCompany, obj.InvoiceOrder.EnterpriseCompanyLocation, IIF( ( obj.SalesOrder == null), null, obj.SalesOrder.DistributionChannel), IIF( ( obj.SalesOrder == null), null, obj.SalesOrder.PriceList))`
### PaymentTransaction

The payment transaction, which is to be invoiced by this line, when Business Reason = P. Used to reconcile the invoice with the payments in the case of advance payment.

Type: **[PaymentTransactions](Finance.Payments.PaymentTransactions.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The product, which is ordered for invoicing

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit of Quantity

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Product.MeasurementUnit`
### SalesOrder

When not NULL specifies the Sales Order that is ordered to be invoiced by this line

Type: **[SalesOrders](Crm.Sales.SalesOrders.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.InvoiceOrder.SalesOrder`

Front-End Recalc Expressions:  
`obj.InvoiceOrder.SalesOrder`
### SalesOrderLine

When not NULL specifies the Sales Order line that is ordered to be invoiced by this line

Type: **[SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### SerialNumber

Serial number of the product. NULL means that the serial number is unknown or not applicable.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### TransactionLine

The store transaction line that is to be invoiced by this line, for Business Reason = S

Type: **[StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Invoicing.InvoiceOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Invoicing.InvoiceOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Invoicing_InvoiceOrderLines

Domain API Entity Type: 
Crm_Invoicing_InvoiceOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Invoicing_InvoiceOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Invoicing_InvoiceOrderLines?$top=10>

