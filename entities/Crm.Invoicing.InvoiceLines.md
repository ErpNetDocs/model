---
uid: Crm.Invoicing.InvoiceLines
---
# Crm.Invoicing.InvoiceLines


Detail records (lines) of the invoices

## General
Namespace: [Crm.Invoicing](Crm.Invoicing.md)  
Repository: Crm.Invoicing.InvoiceLines  
Base Table: Crm_Invoice_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {Invoice.DocumentNo} {Invoice.DocumentType.TypeName:T}  
Search Members: Invoice.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Invoicing.Invoices](Crm.Invoicing.Invoices.md)  
Aggregate Root:  
[Crm.Invoicing.Invoices](Crm.Invoicing.Invoices.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BusinessReason](Crm.Invoicing.InvoiceLines.md#businessreason) | [InvoicingBusinessReason](Crm.Invoicing.InvoiceLines.md#businessreason) | Business reason for invoicing of this product or service. 
| [CurrentBalanceBase](Crm.Invoicing.InvoiceLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DeliveryTermsCode](Crm.Invoicing.InvoiceLines.md#deliverytermscode) | [DeliveryTerms](Crm.Invoicing.InvoiceLines.md#deliverytermscode) __nullable__ | Mode of delivery, like CIF, FOB, etc. Used also in Intrastat reporting 
| [IntrastatApplyDate](Crm.Invoicing.InvoiceLines.md#intrastatapplydate) | datetime __nullable__ | Specifies in which period for Intrastat declaration must be included the current operation. Used only when the invoice is issued in different period than the one, that the operation must be included. If not set the document date is used. 
| [IntrastatTransaction<br />NatureCode](Crm.Invoicing.InvoiceLines.md#intrastattransactionnaturecode) | [TransactionNature](Crm.Invoicing.InvoiceLines.md#intrastattransactionnaturecode) __nullable__ | Transaction nature; used for Intrastat reporting 
| [IntrastatTransportModeCode](Crm.Invoicing.InvoiceLines.md#intrastattransportmodecode) | [TransportMode](Crm.Invoicing.InvoiceLines.md#intrastattransportmodecode) __nullable__ | Transport mode; used for Intrastat reporting 
| [LineAmount](Crm.Invoicing.InvoiceLines.md#lineamount) | [Amount (14, 2)](../data-types.md#amount) | Amount for the line in the currency of the parent document. Usually equals Quantity * Unit_Price. When Quantity = 0, Unit Price is undefined and this contains the total line amount. 
| [LineCustomDiscountPercent](Crm.Invoicing.InvoiceLines.md#linecustomdiscountpercent) | decimal (7, 6) | User-defined discount for the line 
| [LineNo](Crm.Invoicing.InvoiceLines.md#lineno) | int32 | Consecutive line number, unique within the invoice. Usually is increasing in steps of 10, like in 10, 20, 30, etc. 
| [LineStandardDiscount<br />Percent](Crm.Invoicing.InvoiceLines.md#linestandarddiscountpercent) | decimal (7, 6) | Standard discount for the line. This is automatically computed according to discount conditions 
| [Notes](Crm.Invoicing.InvoiceLines.md#notes) | string (254) __nullable__ | Notes for this InvoiceLine. 
| [ParentLineNo](Crm.Invoicing.InvoiceLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. NULL when the current line does not execute line. 
| [ProductDescription](Crm.Invoicing.InvoiceLines.md#productdescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The description of the invoiced product. Initially copied from the name of the invoiced Product or from the generating document 
| [Quantity](Crm.Invoicing.InvoiceLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity of the invoiced product 
| [QuantityBase](Crm.Invoicing.InvoiceLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The equivalent of Quantity in the base measurement unit of the Product 
| [SalesOrderAmount](Crm.Invoicing.InvoiceLines.md#salesorderamount) | decimal (14, 2) __nullable__ | Specifies what portion of the amount of the sales order is invoiced with this line. The amount is calculated with respect to the trade conditions (prices, discounts, etc.) from the sales order. Can be different from the total amount of the line when the trade conditions from the sales order have changed before invoicing. 
| [StandardQuantityBase](Crm.Invoicing.InvoiceLines.md#standardquantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. 
| [UnitPrice](Crm.Invoicing.InvoiceLines.md#unitprice) | [Amount (14, 5)](../data-types.md#amount) | The unit selling price of Quantity 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Crm.Invoicing.InvoiceLines.md#document) | [Invoices](Crm.Invoicing.Invoices.md) | The owner document. The <see cref="Invoice"/> to which this InvoiceLine belongs. `Required` `Filter(multi eq)` |
| [IntrastatTransportCountry](Crm.Invoicing.InvoiceLines.md#intrastattransportcountry) | [Countries](General.Geography.Countries.md) (nullable) | Country of origin of the transport company; used for Intrastat reporting |
| [Invoice](Crm.Invoicing.InvoiceLines.md#invoice) | [Invoices](Crm.Invoicing.Invoices.md) | The <see cref="Invoice"/> to which this InvoiceLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [InvoiceOrderLine](Crm.Invoicing.InvoiceLines.md#invoiceorderline) | [InvoiceOrderLines](Crm.Invoicing.InvoiceOrderLines.md) (nullable) | Invoice order line which is invoiced by this line |
| [LineDealType](Crm.Invoicing.InvoiceLines.md#linedealtype) | [DealTypes](Regulatory.Vat.DealTypes.md) (nullable) | Deal type for this line. If deal type in the line is different from deal type in the header another VAT entry is created. |
| [LineDiscount](Crm.Invoicing.InvoiceLines.md#linediscount) | [LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable) | The line discount type used to form the Line_Standard_<br />Discount_Percent |
| [ParentDocument](Crm.Invoicing.InvoiceLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. NULL when the current line does not execute another line. |
| [ParentSalesOrderLine](Crm.Invoicing.InvoiceLines.md#parentsalesorderline) | [SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable) | When not NULL specifies the Sales Order line that is invoiced by this invoice line |
| [PaymentTransaction](Crm.Invoicing.InvoiceLines.md#paymenttransaction) | [PaymentTransactions](Finance.Payments.PaymentTransactions.md) (nullable) | The payment transaction, which is invoiced by this line, when Business Reason = P. Used to reconcile the invoice with the payments in the case of advance payment. |
| [Product](Crm.Invoicing.InvoiceLines.md#product) | [Products](General.Products.Products.md) (nullable) | The invoiced product. When NULL, although rarely used, the invoice line is still valid and the Product Description contains the invoiced item. |
| [QuantityUnit](Crm.Invoicing.InvoiceLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity |
| [SalesOrder](Crm.Invoicing.InvoiceLines.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) (nullable) | When not NULL specifies the Sales Order that is invoiced by this line |
| [SerialNumber](Crm.Invoicing.InvoiceLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [TransactionLine](Crm.Invoicing.InvoiceLines.md#transactionline) | [StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable) | The store transaction line that is invoiced by this line, for Business Reason = S |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Invoicing.InvoiceLines.md#id) | guid |  
| [ObjectVersion](Crm.Invoicing.InvoiceLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Invoicing.InvoiceLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BusinessReason

Business reason for invoicing of this product or service.

Type: **[InvoicingBusinessReason](Crm.Invoicing.InvoiceLines.md#businessreason)**  
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

### DeliveryTermsCode

Mode of delivery, like CIF, FOB, etc. Used also in Intrastat reporting

Type: **[DeliveryTerms](Crm.Invoicing.InvoiceLines.md#deliverytermscode) __nullable__**  
Category: **System**  
Generic enum type for DeliveryTerms properties  
Allowed Values (Regulatory.Intrastat.DeliveryTerms Enum Members)  

| Value | Description |
| ---- | --- |
| ExWorks | ExWorks value. Stored as 'EXW'. <br /> Database Value: 'EXW' <br /> Model Value: 0 <br /> Domain API Value: 'ExWorks' |
| FrancoCarrier | FrancoCarrier value. Stored as 'FCA'. <br /> Database Value: 'FCA' <br /> Model Value: 1 <br /> Domain API Value: 'FrancoCarrier' |
| FreeAlongsideShip | FreeAlongsideShip value. Stored as 'FAS'. <br /> Database Value: 'FAS' <br /> Model Value: 2 <br /> Domain API Value: 'FreeAlongsideShip' |
| FreeOnBoard | FreeOnBoard value. Stored as 'FOB'. <br /> Database Value: 'FOB' <br /> Model Value: 3 <br /> Domain API Value: 'FreeOnBoard' |
| CostAndFreightCF | CostAndFreightCF value. Stored as 'CFR'. <br /> Database Value: 'CFR' <br /> Model Value: 4 <br /> Domain API Value: 'CostAndFreightCF' |
| CostInsuranceAndFreight | CostInsuranceAndFreight value. Stored as 'CIF'. <br /> Database Value: 'CIF' <br /> Model Value: 5 <br /> Domain API Value: 'CostInsuranceAndFreight' |
| CarriagePaidTo | CarriagePaidTo value. Stored as 'CPT'. <br /> Database Value: 'CPT' <br /> Model Value: 6 <br /> Domain API Value: 'CarriagePaidTo' |
| CarriageAndInsurancePaidTo | CarriageAndInsurancePaidTo value. Stored as 'CIP'. <br /> Database Value: 'CIP' <br /> Model Value: 7 <br /> Domain API Value: 'CarriageAndInsurancePaidTo' |
| DeliveredAtPlace | DeliveredAtPlace value. Stored as 'DAP'. <br /> Database Value: 'DAP' <br /> Model Value: 8 <br /> Domain API Value: 'DeliveredAtPlace' |
| DeliveredAtTerminal | DeliveredAtTerminal value. Stored as 'DAT'. <br /> Database Value: 'DAT' <br /> Model Value: 9 <br /> Domain API Value: 'DeliveredAtTerminal' |
| DeliveredDutyPaid | DeliveredDutyPaid value. Stored as 'DDP'. <br /> Database Value: 'DDP' <br /> Model Value: 10 <br /> Domain API Value: 'DeliveredDutyPaid' |
| DeliveredAtPlaceUnloaded | DeliveredAtPlaceUnloaded value. Stored as 'DPU'. <br /> Database Value: 'DPU' <br /> Model Value: 11 <br /> Domain API Value: 'DeliveredAtPlaceUnloaded' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Invoice.DeliveryTermsCode`

Front-End Recalc Expressions:  
`obj.Invoice.DeliveryTermsCode`
### IntrastatApplyDate

Specifies in which period for Intrastat declaration must be included the current operation. Used only when the invoice is issued in different period than the one, that the operation must be included. If not set the document date is used.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### IntrastatTransactionNatureCode

Transaction nature; used for Intrastat reporting

Type: **[TransactionNature](Crm.Invoicing.InvoiceLines.md#intrastattransactionnaturecode) __nullable__**  
Category: **System**  
Generic enum type for TransactionNature properties  
Allowed Values (Regulatory.Intrastat.TransactionNature Enum Members)  

| Value | Description |
| ---- | --- |
| OutrightPurchaseOrSale | OutrightPurchaseOrSale value. Stored as '11'. <br /> Database Value: '11' <br /> Model Value: 0 <br /> Domain API Value: 'OutrightPurchaseOrSale' |
| SupplyForSale | SupplyForSale value. Stored as '12'. <br /> Database Value: '12' <br /> Model Value: 1 <br /> Domain API Value: 'SupplyForSale' |
| BarterTrade | BarterTrade value. Stored as '13'. <br /> Database Value: '13' <br /> Model Value: 2 <br /> Domain API Value: 'BarterTrade' |
| FinancialLeasing | FinancialLeasing value. Stored as '14'. <br /> Database Value: '14' <br /> Model Value: 3 <br /> Domain API Value: 'FinancialLeasing' |
| OtherTransactions | OtherTransactions value. Stored as '19'. <br /> Database Value: '19' <br /> Model Value: 4 <br /> Domain API Value: 'OtherTransactions' |
| ReturnStokilizing | ReturnStokilizing value. Stored as '21'. <br /> Database Value: '21' <br /> Model Value: 5 <br /> Domain API Value: 'ReturnStokilizing' |
| ReplacementFor<br />ReturnedGoods | ReplacementFor<br />ReturnedGoods value. Stored as '22'. <br /> Database Value: '22' <br /> Model Value: 6 <br /> Domain API Value: 'ReplacementFor<br />ReturnedGoods' |
| ReplacementOfGoods<br />NotBeingReturned | ReplacementOfGoods<br />NotBeingReturned value. Stored as '23'. <br /> Database Value: '23' <br /> Model Value: 7 <br /> Domain API Value: 'ReplacementOfGoods<br />NotBeingReturned' |
| ReturnOrExchange<br />OfOtherGoods | ReturnOrExchange<br />OfOtherGoods value. Stored as '29'. <br /> Database Value: '29' <br /> Model Value: 8 <br /> Domain API Value: 'ReturnOrExchange<br />OfOtherGoods' |
| SpecificTransactions | SpecificTransactions value. Stored as '60'. <br /> Database Value: '60' <br /> Model Value: 9 <br /> Domain API Value: 'SpecificTransactions' |
| OperationsOnJointProjects | OperationsOnJointProjects value. Stored as '70'. <br /> Database Value: '70' <br /> Model Value: 10 <br /> Domain API Value: 'OperationsOnJointProjects' |
| TransactionsOf<br />ConstructionMaterials<br />AndEquipment | TransactionsOf<br />ConstructionMaterials<br />AndEquipment value. Stored as '80'. <br /> Database Value: '80' <br /> Model Value: 11 <br /> Domain API Value: 'TransactionsOf<br />ConstructionMaterials<br />AndEquipment' |
| OtherTransactionsLeasing | OtherTransactionsLeasing value. Stored as '91'. <br /> Database Value: '91' <br /> Model Value: 12 <br /> Domain API Value: 'OtherTransactionsLeasing' |
| OtherTransactionsOther | OtherTransactionsOther value. Stored as '99'. <br /> Database Value: '99' <br /> Model Value: 13 <br /> Domain API Value: 'OtherTransactionsOther' |
| DealsThatInclude<br />PropertyTransfers<br />WithoutFinancial<br />CompensationOr<br />CompensationIn<br />Kind | DealsThatInclude<br />PropertyTransfers<br />WithoutFinancial<br />CompensationOr<br />CompensationIn<br />Kind value. Stored as '30'. <br /> Database Value: '30' <br /> Model Value: 14 <br /> Domain API Value: 'DealsThatInclude<br />PropertyTransfers<br />WithoutFinancial<br />CompensationOr<br />CompensationIn<br />Kind' |
| GoodsThatAreExpected<br />ToBeReturnedTo<br />Sender | GoodsThatAreExpected<br />ToBeReturnedTo<br />Sender value. Stored as '41'. <br /> Database Value: '41' <br /> Model Value: 15 <br /> Domain API Value: 'GoodsThatAreExpected<br />ToBeReturnedTo<br />Sender' |
| GoodsThatAreNot<br />ExpectedToBeReturned<br />ToSender | GoodsThatAreNot<br />ExpectedToBeReturned<br />ToSender value. Stored as '42'. <br /> Database Value: '42' <br /> Model Value: 16 <br /> Domain API Value: 'GoodsThatAreNot<br />ExpectedToBeReturned<br />ToSender' |
| GoodsThatAreReturned<br />ToSender | GoodsThatAreReturned<br />ToSender value. Stored as '51'. <br /> Database Value: '51' <br /> Model Value: 17 <br /> Domain API Value: 'GoodsThatAreReturned<br />ToSender' |
| GoodsThatAreNot<br />ReturnedToSender | GoodsThatAreNot<br />ReturnedToSender value. Stored as '52'. <br /> Database Value: '52' <br /> Model Value: 18 <br /> Domain API Value: 'GoodsThatAreNot<br />ReturnedToSender' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Invoice.IntrastatTransactionNatureCode`

Front-End Recalc Expressions:  
`obj.Invoice.IntrastatTransactionNatureCode`
### IntrastatTransportModeCode

Transport mode; used for Intrastat reporting

Type: **[TransportMode](Crm.Invoicing.InvoiceLines.md#intrastattransportmodecode) __nullable__**  
Category: **System**  
Generic enum type for TransportMode properties  
Allowed Values (Regulatory.Intrastat.TransportMode Enum Members)  

| Value | Description |
| ---- | --- |
| Shipping | Shipping value. Stored as '1'. <br /> Database Value: '1' <br /> Model Value: 0 <br /> Domain API Value: 'Shipping' |
| RailwayTransport | RailwayTransport value. Stored as '2'. <br /> Database Value: '2' <br /> Model Value: 1 <br /> Domain API Value: 'RailwayTransport' |
| RoadTransport | RoadTransport value. Stored as '3'. <br /> Database Value: '3' <br /> Model Value: 2 <br /> Domain API Value: 'RoadTransport' |
| AirTransport | AirTransport value. Stored as '4'. <br /> Database Value: '4' <br /> Model Value: 3 <br /> Domain API Value: 'AirTransport' |
| Mail | Mail value. Stored as '5'. <br /> Database Value: '5' <br /> Model Value: 4 <br /> Domain API Value: 'Mail' |
| FixedTransport<br />Installations | FixedTransport<br />Installations value. Stored as '7'. <br /> Database Value: '7' <br /> Model Value: 5 <br /> Domain API Value: 'FixedTransport<br />Installations' |
| RiverTransport | RiverTransport value. Stored as '8'. <br /> Database Value: '8' <br /> Model Value: 6 <br /> Domain API Value: 'RiverTransport' |
| SelfPropelled | SelfPropelled value. Stored as '9'. <br /> Database Value: '9' <br /> Model Value: 7 <br /> Domain API Value: 'SelfPropelled' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Invoice.IntrastatTransportModeCode`

Front-End Recalc Expressions:  
`obj.Invoice.IntrastatTransportModeCode`
### LineAmount

Amount for the line in the currency of the parent document. Usually equals Quantity * Unit_Price. When Quantity = 0, Unit Price is undefined and this contains the total line amount.

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.CalculateLineAmount( obj.Quantity, obj.UnitPrice, Convert( obj.LineStandardDiscountPercent, Nullable`1), Convert( obj.LineCustomDiscountPercent, Nullable`1), obj.Invoice.DocumentCurrency)`
### LineCustomDiscountPercent

User-defined discount for the line

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive line number, unique within the invoice. Usually is increasing in steps of 10, like in 10, 20, 30, etc.

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Invoice.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.Invoice.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineStandardDiscountPercent

Standard discount for the line. This is automatically computed according to discount conditions

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.LineDiscount != null), obj.LineDiscount.DiscountPercent, 0)`
### Notes

Notes for this InvoiceLine.

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
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### ProductDescription

The description of the invoiced product. Initially copied from the name of the invoiced Product or from the generating document

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Product.Name`
### Quantity

The quantity of the invoiced product

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### QuantityBase

The equivalent of Quantity in the base measurement unit of the Product

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### SalesOrderAmount

Specifies what portion of the amount of the sales order is invoiced with this line. The amount is calculated with respect to the trade conditions (prices, discounts, etc.) from the sales order. Can be different from the total amount of the line when the trade conditions from the sales order have changed before invoicing.

Type: **decimal (14, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.

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

The unit selling price of Quantity

Type: **[Amount (14, 5)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

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

The owner document. The <see cref="Invoice"/> to which this InvoiceLine belongs. `Required` `Filter(multi eq)`

Type: **[Invoices](Crm.Invoicing.Invoices.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### IntrastatTransportCountry

Country of origin of the transport company; used for Intrastat reporting

Type: **[Countries](General.Geography.Countries.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Invoice.IntrastatTransportCountry`

Front-End Recalc Expressions:  
`obj.Invoice.IntrastatTransportCountry`
### Invoice

The <see cref="Invoice"/> to which this InvoiceLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Invoices](Crm.Invoicing.Invoices.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### InvoiceOrderLine

Invoice order line which is invoiced by this line

Type: **[InvoiceOrderLines](Crm.Invoicing.InvoiceOrderLines.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### LineDealType

Deal type for this line. If deal type in the line is different from deal type in the header another VAT entry is created.

Type: **[DealTypes](Regulatory.Vat.DealTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Invoice.DealType`

Front-End Recalc Expressions:  
`obj.Invoice.DealType`
### LineDiscount

The line discount type used to form the Line_Standard_Discount_Percent

Type: **[LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.DetermineLineDiscount( Convert( ( obj.Invoice.DeliveryDate ?? obj.Invoice.DocumentDate), Nullable`1), obj.Invoice.Customer, obj.Product, obj.Quantity, obj.Invoice.EnterpriseCompany, obj.Invoice.EnterpriseCompanyLocation, IIF( ( obj.SalesOrder == null), null, obj.SalesOrder.DistributionChannel), IIF( ( obj.SalesOrder == null), null, obj.SalesOrder.PriceList))`
### ParentDocument

The document, which the current line executes. NULL when the current line does not execute another line.

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ParentSalesOrderLine

When not NULL specifies the Sales Order line that is invoiced by this invoice line

Type: **[SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### PaymentTransaction

The payment transaction, which is invoiced by this line, when Business Reason = P. Used to reconcile the invoice with the payments in the case of advance payment.

Type: **[PaymentTransactions](Finance.Payments.PaymentTransactions.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The invoiced product. When NULL, although rarely used, the invoice line is still valid and the Product Description contains the invoiced item.

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

When not NULL specifies the Sales Order that is invoiced by this line

Type: **[SalesOrders](Crm.Sales.SalesOrders.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ParentSalesOrderLine != null), obj.ParentSalesOrderLine.SalesOrder, null)`
### SerialNumber

Serial number of the product. NULL means that the serial number is unknown or not applicable.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### TransactionLine

The store transaction line that is invoiced by this line, for Business Reason = S

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

[!list limit=1000 erp.entity=Crm.Invoicing.InvoiceLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Invoicing.InvoiceLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Invoicing_InvoiceLines

Domain API Entity Type: 
Crm_Invoicing_InvoiceLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Invoicing_InvoiceLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Invoicing_InvoiceLines?$top=10>

