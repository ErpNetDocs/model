---
uid: Logistics.Procurement.PurchaseInvoiceLines
---
# Logistics.Procurement.PurchaseInvoiceLines


Contains detail lines for purchase invoice documents.

## General
Namespace: [Logistics.Procurement](Logistics.Procurement.md)  
Repository: Logistics.Procurement.PurchaseInvoiceLines  
Base Table: Scm_Purchase_Invoice_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {PurchaseInvoice.DocumentNo} {PurchaseInvoice.DocumentType.TypeName:T}  
Search Members: PurchaseInvoice.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Procurement.PurchaseInvoices](Logistics.Procurement.PurchaseInvoices.md)  
Aggregate Root:  
[Logistics.Procurement.PurchaseInvoices](Logistics.Procurement.PurchaseInvoices.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrentBalanceBase](Logistics.Procurement.PurchaseInvoiceLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DeliveryTermsCode](Logistics.Procurement.PurchaseInvoiceLines.md#deliverytermscode) | [DeliveryTerms](Logistics.Procurement.PurchaseInvoiceLines.md#deliverytermscode) __nullable__ | Mode of delivery, like CIF, FOB, etc. Used also in Intrastat reporting 
| [IntrastatApplyDate](Logistics.Procurement.PurchaseInvoiceLines.md#intrastatapplydate) | datetime __nullable__ | Specifies in which period for Intrastat declaration must be included the current operation. Used only when the invoice is issued in different period than the one, that the operation must be included. If not set the document date is used. 
| [IntrastatTransaction<br />NatureCode](Logistics.Procurement.PurchaseInvoiceLines.md#intrastattransactionnaturecode) | [TransactionNature](Logistics.Procurement.PurchaseInvoiceLines.md#intrastattransactionnaturecode) __nullable__ | Transaction nature; used for Intrastat reporting 
| [IntrastatTransportModeCode](Logistics.Procurement.PurchaseInvoiceLines.md#intrastattransportmodecode) | [TransportMode](Logistics.Procurement.PurchaseInvoiceLines.md#intrastattransportmodecode) __nullable__ | Transport mode; used for Intrastat reporting 
| [LineAmount](Logistics.Procurement.PurchaseInvoiceLines.md#lineamount) | [Amount (14, 2)](../data-types.md#amount) | The total invoiced amount for this line in the document currency of the invoice. 
| [LineNo](Logistics.Procurement.PurchaseInvoiceLines.md#lineno) | int32 | Consecutive line number within the invoice. 
| [Notes](Logistics.Procurement.PurchaseInvoiceLines.md#notes) | string (254) __nullable__ | Notes for this PurchaseInvoiceLine. 
| [ProductName](Logistics.Procurement.PurchaseInvoiceLines.md#productname) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of the invoiced product, initially copied from the name in the product definition. The field can be edited by the user. 
| [Quantity](Logistics.Procurement.PurchaseInvoiceLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The invoiced quantity. 
| [QuantityBase](Logistics.Procurement.PurchaseInvoiceLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The equivalence of Quantity in the base measurement category of the product. 
| [StandardQuantityBase](Logistics.Procurement.PurchaseInvoiceLines.md#standardquantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. 
| [UnitPrice](Logistics.Procurement.PurchaseInvoiceLines.md#unitprice) | [Amount (14, 5)](../data-types.md#amount) | The unit price of the invoiced item in the document currency of the invoice. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Procurement.PurchaseInvoiceLines.md#document) | [PurchaseInvoices](Logistics.Procurement.PurchaseInvoices.md) | The owner document. The <see cref="PurchaseInvoice"/> to which this PurchaseInvoiceLine belongs. `Required` `Filter(multi eq)` |
| [IntrastatDestinationRegion](Logistics.Procurement.PurchaseInvoiceLines.md#intrastatdestinationregion) | [AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable) | Region, which is the final destination of the goods. Used for Intrastat reporting. |
| [IntrastatTransportCountry](Logistics.Procurement.PurchaseInvoiceLines.md#intrastattransportcountry) | [Countries](General.Geography.Countries.md) (nullable) | Country of origin of the transport company; used for Intrastat reporting |
| [LineCostCenter](Logistics.Procurement.PurchaseInvoiceLines.md#linecostcenter) | [CostCenters](Finance.Accounting.CostCenters.md) (nullable) | Cost center for which the amount from this row will be accounted. |
| [LineDealType](Logistics.Procurement.PurchaseInvoiceLines.md#linedealtype) | [DealTypes](Regulatory.Vat.DealTypes.md) (nullable) | Deal type for this line. If deal type in the line is different from deal type in the header another VAT entry is created. |
| [OriginCountry](Logistics.Procurement.PurchaseInvoiceLines.md#origincountry) | [Countries](General.Geography.Countries.md) (nullable) | Country of origin for the product. Specified when the country of origin for the current purchase is different that the country of origin from the product's definition. |
| [Product](Logistics.Procurement.PurchaseInvoiceLines.md#product) | [Products](General.Products.Products.md) | The invoiced product. |
| [PurchaseInvoice](Logistics.Procurement.PurchaseInvoiceLines.md#purchaseinvoice) | [PurchaseInvoices](Logistics.Procurement.PurchaseInvoices.md) | The <see cref="PurchaseInvoice"/> to which this PurchaseInvoiceLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [QuantityUnit](Logistics.Procurement.PurchaseInvoiceLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. |
| [ReceivingOrderLine](Logistics.Procurement.PurchaseInvoiceLines.md#receivingorderline) | [ReceivingOrderLines](Logistics.Procurement.ReceivingOrderLines.md) (nullable) | The receiving order line, which is invoiced by the current line. NULL means that this line is not directly related to receiving order line. |
| [SaleLineDealType](Logistics.Procurement.PurchaseInvoiceLines.md#salelinedealtype) | [DealTypes](Regulatory.Vat.DealTypes.md) (nullable) | Sale deal type for this line. If sale deal type in the line is different from sale deal type in the header another Sales VAT entry is created. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Procurement.PurchaseInvoiceLines.md#id) | guid |  
| [ObjectVersion](Logistics.Procurement.PurchaseInvoiceLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Procurement.PurchaseInvoiceLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### DeliveryTermsCode

Mode of delivery, like CIF, FOB, etc. Used also in Intrastat reporting

Type: **[DeliveryTerms](Logistics.Procurement.PurchaseInvoiceLines.md#deliverytermscode) __nullable__**  
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
`obj.PurchaseInvoice.DeliveryTermsCode`

Front-End Recalc Expressions:  
`obj.PurchaseInvoice.DeliveryTermsCode`
### IntrastatApplyDate

Specifies in which period for Intrastat declaration must be included the current operation. Used only when the invoice is issued in different period than the one, that the operation must be included. If not set the document date is used.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### IntrastatTransactionNatureCode

Transaction nature; used for Intrastat reporting

Type: **[TransactionNature](Logistics.Procurement.PurchaseInvoiceLines.md#intrastattransactionnaturecode) __nullable__**  
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
`obj.PurchaseInvoice.IntrastatTransactionNatureCode`

Front-End Recalc Expressions:  
`obj.PurchaseInvoice.IntrastatTransactionNatureCode`
### IntrastatTransportModeCode

Transport mode; used for Intrastat reporting

Type: **[TransportMode](Logistics.Procurement.PurchaseInvoiceLines.md#intrastattransportmodecode) __nullable__**  
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
`obj.PurchaseInvoice.IntrastatTransportModeCode`

Front-End Recalc Expressions:  
`obj.PurchaseInvoice.IntrastatTransportModeCode`
### LineAmount

The total invoiced amount for this line in the document currency of the invoice.

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive line number within the invoice.

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.PurchaseInvoice.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.PurchaseInvoice.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this PurchaseInvoiceLine.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### ProductName

The name of the invoiced product, initially copied from the name in the product definition. The field can be edited by the user.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Product.Name`

Front-End Recalc Expressions:  
`IIF( ( obj.ReceivingOrderLine != null), obj.ReceivingOrderLine.ProductDescription, obj.Product.Name)`
### Quantity

The invoiced quantity.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ReceivingOrderLine != null), obj.ReceivingOrderLine.ConfirmedQuantity.IfNullThen( obj.ReceivingOrderLine.Quantity), obj.Quantity)`
### QuantityBase

The equivalence of Quantity in the base measurement category of the product.

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

The unit price of the invoiced item in the document currency of the invoice.

Type: **[Amount (14, 5)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ReceivingOrderLine != null), obj.ReceivingOrderLine.PricePerUnit, obj.GetDefaultProductPrice( obj.Product))`
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

The owner document. The <see cref="PurchaseInvoice"/> to which this PurchaseInvoiceLine belongs. `Required` `Filter(multi eq)`

Type: **[PurchaseInvoices](Logistics.Procurement.PurchaseInvoices.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### IntrastatDestinationRegion

Region, which is the final destination of the goods. Used for Intrastat reporting.

Type: **[AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.PurchaseInvoice.IntrastatDestinationRegion`

Front-End Recalc Expressions:  
`obj.PurchaseInvoice.IntrastatDestinationRegion`
### IntrastatTransportCountry

Country of origin of the transport company; used for Intrastat reporting

Type: **[Countries](General.Geography.Countries.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.PurchaseInvoice.IntrastatTransportCountry`

Front-End Recalc Expressions:  
`obj.PurchaseInvoice.IntrastatTransportCountry`
### LineCostCenter

Cost center for which the amount from this row will be accounted.

Type: **[CostCenters](Finance.Accounting.CostCenters.md) (nullable)**  
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
`obj.PurchaseInvoice.DealType`

Front-End Recalc Expressions:  
`obj.PurchaseInvoice.DealType`
### OriginCountry

Country of origin for the product. Specified when the country of origin for the current purchase is different that the country of origin from the product's definition.

Type: **[Countries](General.Geography.Countries.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The invoiced product.

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ReceivingOrderLine != null), obj.ReceivingOrderLine.Product, obj.Product)`
### PurchaseInvoice

The <see cref="PurchaseInvoice"/> to which this PurchaseInvoiceLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[PurchaseInvoices](Logistics.Procurement.PurchaseInvoices.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit of Quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ReceivingOrderLine != null), obj.ReceivingOrderLine.QuantityUnit, IIF( ( obj.Product != null), obj.Product.MeasurementUnit, obj.QuantityUnit))`
### ReceivingOrderLine

The receiving order line, which is invoiced by the current line. NULL means that this line is not directly related to receiving order line.

Type: **[ReceivingOrderLines](Logistics.Procurement.ReceivingOrderLines.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### SaleLineDealType

Sale deal type for this line. If sale deal type in the line is different from sale deal type in the header another Sales VAT entry is created.

Type: **[DealTypes](Regulatory.Vat.DealTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.PurchaseInvoice.SaleDealType`

Front-End Recalc Expressions:  
`obj.PurchaseInvoice.SaleDealType`

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

[!list limit=1000 erp.entity=Logistics.Procurement.PurchaseInvoiceLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Procurement.PurchaseInvoiceLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Procurement_PurchaseInvoiceLines

Domain API Entity Type: 
Logistics_Procurement_PurchaseInvoiceLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Procurement_PurchaseInvoiceLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Procurement_PurchaseInvoiceLines?$top=10>

