---
uid: Crm.Invoicing.InvoiceOrderLines
---
# Crm.Invoicing.InvoiceOrderLines Entity

**Namespace:** [Crm.Invoicing](Crm.Invoicing.md)  

Detail records (lines) of Invoice Orders. Entity: Crm_Invoice_Order_Lines

## Default Visualization
Default Display Text Format:  
_{LineNo}. {InvoiceOrder.DocumentNo} {InvoiceOrder.DocumentType.TypeName:T}_  
Default Search Members:  
_InvoiceOrder.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Invoicing.InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)  
Aggregate Root:  
[Crm.Invoicing.InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BusinessReason](Crm.Invoicing.InvoiceOrderLines.md#businessreason) | [InvoicingBusinessReason](Crm.Invoicing.InvoiceOrderLines.md#businessreason) | Business reason for invoicing of this product or service. S=Shipment, P=Payment. `Required` `Default("S")` 
| [CurrentBalanceBase](Crm.Invoicing.InvoiceOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DisplayText](Crm.Invoicing.InvoiceOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Invoicing.InvoiceOrderLines.md#id) | guid |  
| [LineAmount](Crm.Invoicing.InvoiceOrderLines.md#lineamount) | [Amount (14, 2)](../data-types.md#amount) | Amount for the line in the currency of the parent document. Usually equals Quantity * Unit_Price. When Quantity = 0, Unit Price is undefined and this contains the total line amount. `Currency: InvoiceOrder.DocumentCurrency` `Required` `Default(0)` 
| [LineCustomDiscountPercent](Crm.Invoicing.InvoiceOrderLines.md#linecustomdiscountpercent) | decimal (7, 6) | User-defined discount for the line. `Required` `Default(0)` 
| [LineNo](Crm.Invoicing.InvoiceOrderLines.md#lineno) | int32 | Line number, unique within the InvoiceOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the InvoiceOrder (in order to allow insertions with adjustment documents). `Required` 
| [LineStandardDiscount<br />Percent](Crm.Invoicing.InvoiceOrderLines.md#linestandarddiscountpercent) | decimal (7, 6) | Standard discount for the line. This is automatically computed according to discount conditions. `Required` `Default(0)` 
| [ObjectVersion](Crm.Invoicing.InvoiceOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProductDescription](Crm.Invoicing.InvoiceOrderLines.md#productdescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The description of Product. Initially copied from the name of the Product or from the generating document. `Required` 
| [Quantity](Crm.Invoicing.InvoiceOrderLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity of the product to invoice. `Unit: QuantityUnit` `Required` `Default(1)` `Filter(ge;le)` 
| [QuantityBase](Crm.Invoicing.InvoiceOrderLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The equivalent of Quantity in the base measurement unit of the Product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` 
| [StandardQuantityBase](Crm.Invoicing.InvoiceOrderLines.md#standardquantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [UnitPrice](Crm.Invoicing.InvoiceOrderLines.md#unitprice) | [Amount (14, 5)](../data-types.md#amount) | Unit selling price in the unit of measure, specified in Quantity Unit. `Currency: InvoiceOrder.DocumentCurrency` `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Crm.Invoicing.InvoiceOrderLines.md#document) | [InvoiceOrders](Crm.Invoicing.InvoiceOrders.md) | The owner document. The <see cref="InvoiceOrder"/> to which this InvoiceOrderLine belongs. `Required` `Filter(multi eq)` |
| [InvoiceOrder](Crm.Invoicing.InvoiceOrderLines.md#invoiceorder) | [InvoiceOrders](Crm.Invoicing.InvoiceOrders.md) | The <see cref="InvoiceOrder"/> to which this InvoiceOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [LineDealType](Crm.Invoicing.InvoiceOrderLines.md#linedealtype) | [DealTypes](Regulatory.Vat.DealTypes.md) (nullable) | Deal type to be passed to the invoice line. If deal type in the line is different from deal type in the header another VAT entry is created from the invoice. `Filter(multi eq)` |
| [LineDiscount](Crm.Invoicing.InvoiceOrderLines.md#linediscount) | [LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable) | The line discount type used to form the Line_Standard_<br />Discount_Percent. `Filter(multi eq)` |
| [PaymentTransaction](Crm.Invoicing.InvoiceOrderLines.md#paymenttransaction) | [PaymentTransactions](Finance.Payments.PaymentTransactions.md) (nullable) | The payment transaction, which is to be invoiced by this line, when Business Reason = P. Used to reconcile the invoice with the payments in the case of advance payment. `Filter(multi eq)` |
| [Product](Crm.Invoicing.InvoiceOrderLines.md#product) | [Products](General.Products.Products.md) (nullable) | The product, which is ordered for invoicing. `Filter(multi eq)` |
| [QuantityUnit](Crm.Invoicing.InvoiceOrderLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. `Required` `Filter(multi eq)` |
| [SalesOrder](Crm.Invoicing.InvoiceOrderLines.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) (nullable) | When not null specifies the Sales Order that is ordered to be invoiced by this line. `Filter(multi eq)` |
| [SalesOrderLine](Crm.Invoicing.InvoiceOrderLines.md#salesorderline) | [SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable) | When not null specifies the Sales Order line that is ordered to be invoiced by this line. `Filter(multi eq)` |
| [SerialNumber](Crm.Invoicing.InvoiceOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Which serial number to receive/issue. null means that serial number is unknown or not applicable. `Filter(multi eq)` |
| [TransactionLine](Crm.Invoicing.InvoiceOrderLines.md#transactionline) | [StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable) | The store transaction line that is to be invoiced by this line, for Business Reason = S. `Filter(multi eq)` |


## Attribute Details

### BusinessReason

Business reason for invoicing of this product or service. S=Shipment, P=Payment. `Required` `Default("S")`

_Type_: **[InvoicingBusinessReason](Crm.Invoicing.InvoiceOrderLines.md#businessreason)**  
_Category_: **System**  
Generic enum type for InvoicingBusinessReason properties  
_Allowed Values (Crm.Invoicing.InvoicingBusinessReason Enum Members)_  

| Value | Description |
| ---- | --- |
| Payment | Payment value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Payment' |
| Shipment | Shipment value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Shipment' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Shipment**  
_Show in UI_: **HiddenByDefault**  

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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineAmount

Amount for the line in the currency of the parent document. Usually equals Quantity * Unit_Price. When Quantity = 0, Unit Price is undefined and this contains the total line amount. `Currency: InvoiceOrder.DocumentCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.CalculateLineAmount( obj.Quantity, obj.UnitPrice, Convert( obj.LineCustomDiscountPercent, Nullable`1), Convert( obj.LineStandardDiscountPercent, Nullable`1), obj.InvoiceOrder.DocumentCurrency)`
### LineCustomDiscountPercent

User-defined discount for the line. `Required` `Default(0)`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### LineNo

Line number, unique within the InvoiceOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the InvoiceOrder (in order to allow insertions with adjustment documents). `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.InvoiceOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.InvoiceOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineStandardDiscountPercent

Standard discount for the line. This is automatically computed according to discount conditions. `Required` `Default(0)`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.LineDiscount != null), obj.LineDiscount.DiscountPercent, 0)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ProductDescription

The description of Product. Initially copied from the name of the Product or from the generating document. `Required`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.Name`
### Quantity

The quantity of the product to invoice. `Unit: QuantityUnit` `Required` `Default(1)` `Filter(ge;le)`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

The equivalent of Quantity in the base measurement unit of the Product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
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

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### UnitPrice

Unit selling price in the unit of measure, specified in Quantity Unit. `Currency: InvoiceOrder.DocumentCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 5)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.CalculateUnitPrice( obj.InvoiceOrder, obj.Product)`

## Reference Details

### Document

The owner document. The <see cref="InvoiceOrder"/> to which this InvoiceOrderLine belongs. `Required` `Filter(multi eq)`

_Type_: **[InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### InvoiceOrder

The <see cref="InvoiceOrder"/> to which this InvoiceOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### LineDealType

Deal type to be passed to the invoice line. If deal type in the line is different from deal type in the header another VAT entry is created from the invoice. `Filter(multi eq)`

_Type_: **[DealTypes](Regulatory.Vat.DealTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.InvoiceOrder.DealType`

_Front-End Recalc Expressions:_  
`obj.InvoiceOrder.DealType`
### LineDiscount

The line discount type used to form the Line_Standard_Discount_Percent. `Filter(multi eq)`

_Type_: **[LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.DetermineLineDiscount( Convert( ( obj.InvoiceOrder.DeliveryDate ?? obj.InvoiceOrder.DocumentDate), Nullable`1), obj.InvoiceOrder.Customer, obj.Product, obj.Quantity, obj.InvoiceOrder.EnterpriseCompany, obj.InvoiceOrder.EnterpriseCompanyLocation, IIF( ( obj.SalesOrder == null), null, obj.SalesOrder.DistributionChannel), IIF( ( obj.SalesOrder == null), null, obj.SalesOrder.PriceList))`
### PaymentTransaction

The payment transaction, which is to be invoiced by this line, when Business Reason = P. Used to reconcile the invoice with the payments in the case of advance payment. `Filter(multi eq)`

_Type_: **[PaymentTransactions](Finance.Payments.PaymentTransactions.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Product

The product, which is ordered for invoicing. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### QuantityUnit

The measurement unit of Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.MeasurementUnit`
### SalesOrder

When not null specifies the Sales Order that is ordered to be invoiced by this line. `Filter(multi eq)`

_Type_: **[SalesOrders](Crm.Sales.SalesOrders.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.InvoiceOrder.SalesOrder`

_Front-End Recalc Expressions:_  
`obj.InvoiceOrder.SalesOrder`
### SalesOrderLine

When not null specifies the Sales Order line that is ordered to be invoiced by this line. `Filter(multi eq)`

_Type_: **[SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### SerialNumber

Which serial number to receive/issue. null means that serial number is unknown or not applicable. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### TransactionLine

The store transaction line that is to be invoiced by this line, for Business Reason = S. `Filter(multi eq)`

_Type_: **[StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable)**  
_Indexed_: **True**  
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

