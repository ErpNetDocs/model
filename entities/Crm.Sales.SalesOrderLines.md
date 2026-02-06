---
uid: Crm.Sales.SalesOrderLines
---
# Crm.Sales.SalesOrderLines


Sales Order Lines represent the individual items or services ordered by a customer within a Sales Order.
    
This data type defines the detailed line-level information of sales order documents, including product or service, ordered quantity, unit of measure, unit price, discounts, taxes, delivery requirements, and fulfillment-related settings.

Sales Order Lines specify what is being sold and in what quantity and conditions, and are used as the operational basis for reservation, picking, delivery, invoicing, costing, and sales analysis.

## General
Namespace: [Crm.Sales](Crm.Sales.md)  
Repository: Crm.Sales.SalesOrderLines  
Base Table: Crm_Sales_Order_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {SalesOrder.DocumentNo} {SalesOrder.DocumentType.TypeName:T}  
Search Members: SalesOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Sales.SalesOrders](Crm.Sales.SalesOrders.md)  
Aggregate Root:  
[Crm.Sales.SalesOrders](Crm.Sales.SalesOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ApplyTradeConditions](Crm.Sales.SalesOrderLines.md#applytradeconditions) | boolean | Specifies whether the system should apply standard pricing and discounts to this line.[Required] [Default(true)] [Filter(eq)] [Introduced in version 25.1.2.53] 
| [BonusProgramAmount](Crm.Sales.SalesOrderLines.md#bonusprogramamount) | [Amount](../data-types.md#amount) | The amount of the discount from the bonus program. 
| [CurrentBalanceBase](Crm.Sales.SalesOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DeliveryTermsCode](Crm.Sales.SalesOrderLines.md#deliverytermscode) | [DeliveryTerms](Crm.Sales.SalesOrderLines.md#deliverytermscode) __nullable__ | Mode of delivery, like CIF, FOB, etc. Used also in Intrastat reporting 
| [GuaranteePeriodDays](Crm.Sales.SalesOrderLines.md#guaranteeperioddays) | int32 __nullable__ | Guarantee period in days for the offered product. NULL for non-serviced products 
| [HistoricalDataJson](Crm.Sales.SalesOrderLines.md#historicaldatajson) | string (max) __nullable__ | Used only for lines, which are returns. It is a JSON-formatted string, containing data from the original sale.[Introduced in version 19.1] 
| [HistoricalUnitCost](Crm.Sales.SalesOrderLines.md#historicalunitcost) | [Amount (14, 5)](../data-types.md#amount) __nullable__ | Used for returning of goods that are sold before the exploitation of the system[Currency: SalesOrder.DocumentCurrency] [Filter(eq;ge;le)] 
| [IntrastatApplyDate](Crm.Sales.SalesOrderLines.md#intrastatapplydate) | datetime __nullable__ | Specifies in which period for Intrastat declaration must be included the current operation. Used only when the invoice is issued in different period than the one, that the operation must be included. If not set the document date is used.[Filter(ge;le)] [Introduced in version 21.1.3.83] 
| [IntrastatTransaction<br />NatureCode](Crm.Sales.SalesOrderLines.md#intrastattransactionnaturecode) | [TransactionNature](Crm.Sales.SalesOrderLines.md#intrastattransactionnaturecode) __nullable__ | Transaction nature; used for Intrastat reporting 
| [IntrastatTransportModeCode](Crm.Sales.SalesOrderLines.md#intrastattransportmodecode) | [TransportMode](Crm.Sales.SalesOrderLines.md#intrastattransportmodecode) __nullable__ | Transport mode; used for Intrastat reporting 
| [Level1DiscountAmount](Crm.Sales.SalesOrderLines.md#level1discountamount) | [Amount](../data-types.md#amount) | The amount of the level 1 discount. 
| [Level1DiscountPercent](Crm.Sales.SalesOrderLines.md#level1discountpercent) | decimal (7, 6) __nullable__ | The percent of the level 1 discount.[ReadOnly] [Introduced in version 23.1.2.56] 
| [Level2DiscountAmount](Crm.Sales.SalesOrderLines.md#level2discountamount) | [Amount](../data-types.md#amount) | The cumulative amount of the level 2 discount. 
| [Level2DiscountPercent](Crm.Sales.SalesOrderLines.md#level2discountpercent) | decimal (7, 6) __nullable__ | The percent of the level 2 discount.[ReadOnly] [Introduced in version 23.1.2.8] 
| [Level3DiscountAmount](Crm.Sales.SalesOrderLines.md#level3discountamount) | [Amount](../data-types.md#amount) | The cumulative amount of the level 3 discount. 
| [Level3DiscountPercent](Crm.Sales.SalesOrderLines.md#level3discountpercent) | decimal (7, 6) __nullable__ | The percent of the level 3 discount.[ReadOnly] [Introduced in version 23.1.2.8] 
| [LineAmount](Crm.Sales.SalesOrderLines.md#lineamount) | [Amount (14, 2)](../data-types.md#amount) | The total amount for the line. Equals to Quantity * Unit_Price, less the discounts[Currency: SalesOrder.DocumentCurrency] [Required] [Default(0)] 
| [LineCustomDiscountPercent](Crm.Sales.SalesOrderLines.md#linecustomdiscountpercent) | decimal (7, 6) | User-defined discount for the line[Required] [Default(0)] [Filter(ge;le)] 
| [LineFromDate](Crm.Sales.SalesOrderLines.md#linefromdate) | date __nullable__ | When selling a service valid only for a period, denotes the beginning of the period. NULL means that it is unknown or N/A.[Filter(ge;le)] [Introduced in version 20.1] 
| [LineNo](Crm.Sales.SalesOrderLines.md#lineno) | int32 | Consecutive number of the line within the sales order[Required] [Filter(eq)] [ORD] 
| [LineStandardDiscount<br />Percent](Crm.Sales.SalesOrderLines.md#linestandarddiscountpercent) | decimal (7, 6) | Standard discount percent for the line. It is calculated by accumulating in cascade the line discounts at all levels.[Required] [Default(0)] [ReadOnly] 
| [LineToDate](Crm.Sales.SalesOrderLines.md#linetodate) | date __nullable__ | When selling a service valid only for a period, denotes the end of the period. NULL means that it is unknown or N/A.[Filter(ge;le)] [Introduced in version 20.1] 
| [Notes](Crm.Sales.SalesOrderLines.md#notes) | string (max) __nullable__ | Notes for this SalesOrderLine. 
| [ParentLineNo](Crm.Sales.SalesOrderLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. NULL when the current line does not execute parent line.[Filter(eq)] 
| [PersistLot](Crm.Sales.SalesOrderLines.md#persistlot) | boolean | If checked specifies that the lot in the line cannot be changed in the sub-documents created by the current document.[Required] [Default(false)] [Filter(eq)] 
| [ProductDescription](Crm.Sales.SalesOrderLines.md#productdescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of the sold product at the time the sale was made[Required] [Filter(like)] 
| [PromotionalPackageAmount](Crm.Sales.SalesOrderLines.md#promotionalpackageamount) | [Amount](../data-types.md#amount) | The amount of the discount from the relative promotional package line. 
| [Quantity](Crm.Sales.SalesOrderLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity sold[Unit: QuantityUnit] [Required] [Default(1)] [Filter(ge;le)] 
| [QuantityBase](Crm.Sales.SalesOrderLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The equivalent of Quantity in the base measurement category of the product[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] 
| [RequestedQuantity](Crm.Sales.SalesOrderLines.md#requestedquantity) | [Quantity (12, 3)](../data-types.md#quantity) __nullable__ | Quantity requested by customer[Unit: QuantityUnit] 
| [RequiredDeliveryDate](Crm.Sales.SalesOrderLines.md#requireddeliverydate) | date __nullable__ | The required (contracted) delivery date for the line[Filter(ge;le)] 
| [StandardQuantityBase](Crm.Sales.SalesOrderLines.md#standardquantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [ReadOnly] [Introduced in version 18.2] 
| [StandardUnitPrice](Crm.Sales.SalesOrderLines.md#standardunitprice) | [Amount (14, 5)](../data-types.md#amount) __nullable__ | Standard unit price of the product during the creation of the sales order line[Currency: SalesOrder.DocumentCurrency] [ReadOnly] 
| [UnitPrice](Crm.Sales.SalesOrderLines.md#unitprice) | [Amount (14, 5)](../data-types.md#amount) | Unit price of the product in the currency of the sales order and in the unit of measure, as specified by QuantityUnitId[Currency: SalesOrder.DocumentCurrency] [Required] [Default(0)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BonusProgram](Crm.Sales.SalesOrderLines.md#bonusprogram) | [BonusPrograms](Crm.Pricing.BonusPrograms.md) (nullable) | The bonus program, based on which the line was automatically added. NULL when the line was not added for bonus program. |
| [Document](Crm.Sales.SalesOrderLines.md#document) | [SalesOrders](Crm.Sales.SalesOrders.md) | The owner document. The <see cref="SalesOrder"/> to which this SalesOrderLine belongs. `Required` `Filter(multi eq)` |
| [IntrastatTransportCountry](Crm.Sales.SalesOrderLines.md#intrastattransportcountry) | [Countries](General.Geography.Countries.md) (nullable) | Country of origin of the transport company; used for Intrastat reporting |
| [Level1Discount](Crm.Sales.SalesOrderLines.md#level1discount) | [LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable) | Indicates the level 1 discount. |
| [Level2Discount](Crm.Sales.SalesOrderLines.md#level2discount) | [LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable) | Indicates the level 2 discount. |
| [Level3Discount](Crm.Sales.SalesOrderLines.md#level3discount) | [LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable) | Indicates the level 3 discount. |
| [LineDealType](Crm.Sales.SalesOrderLines.md#linedealtype) | [DealTypes](Regulatory.Vat.DealTypes.md) (nullable) | Deal type to be passed to the invoice line. If deal type in entered then the invoice creates VAT entry for this deal type. |
| [<s>LineDiscount</s>](Crm.Sales.SalesOrderLines.md#linediscount) | [LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable) | **OBSOLETE! Do not use!** The line discount type used to form the Line_Standard_<br />Discount_Percent |
| [LineEndCustomerParty](Crm.Sales.SalesOrderLines.md#lineendcustomerparty) | [Parties](General.Contacts.Parties.md) (nullable) | The end customer is the customer of the dealer. It is stored for information purposes only. The end customer may not have customer definition, just party. |
| [LineStore](Crm.Sales.SalesOrderLines.md#linestore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store which should be used to issue the goods for the line. NULL means to use the store from the header |
| [Lot](Crm.Sales.SalesOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | Specifies the lot from which the goods should be issued. NULL means that the lot will be specified at a later stage (store order, etc.) |
| [ParentDocument](Crm.Sales.SalesOrderLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. NULL when the current line does not execute another line. |
| [Product](Crm.Sales.SalesOrderLines.md#product) | [Products](General.Products.Products.md) | The product sold |
| [ProductCode](Crm.Sales.SalesOrderLines.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Used to set the Product_Id thru the coding systems |
| [ProductPrice](Crm.Sales.SalesOrderLines.md#productprice) | [ProductPrices](Crm.Pricing.ProductPrices.md) (nullable) | Not NULL when the price has been selected from the list of valid standard prices |
| [ProductVariant](Crm.Sales.SalesOrderLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. |
| [PromotionalPackage](Crm.Sales.SalesOrderLines.md#promotionalpackage) | [PromotionalPackages](Crm.Pricing.PromotionalPackages.md) (nullable) | The promotional package, based on which the line was added. NULL when the line was not added as part of a promotional package |
| [QuantityUnit](Crm.Sales.SalesOrderLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity |
| [ReturnForInvoiceLine](Crm.Sales.SalesOrderLines.md#returnforinvoiceline) | [InvoiceLines](Crm.Invoicing.InvoiceLines.md) (nullable) | When specified, indicates that the current line is a return for products, invoiced with the specified invoice line. |
| [ReturnForSalesOrderLine](Crm.Sales.SalesOrderLines.md#returnforsalesorderline) | [SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable) | When specified indicates that the goods sold in Return_For_Sales_<br />Order_Line_Id are returned with the current line |
| [SalesOrder](Crm.Sales.SalesOrderLines.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) | The <see cref="SalesOrder"/> to which this SalesOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [SerialNumber](Crm.Sales.SalesOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [StoreBin](Crm.Sales.SalesOrderLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | The bin from which the goods should be withdrawn. NULL means that the bin will be specified at a later stage (store order, etc.) |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Sales.SalesOrderLines.md#id) | guid |  
| [ObjectVersion](Crm.Sales.SalesOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Sales.SalesOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ApplyTradeConditions

Specifies whether the system should apply standard pricing and discounts to this line.[Required] [Default(true)] [Filter(eq)] [Introduced in version 25.1.2.53]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SalesOrder.ApplyTradeConditions`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.ReturnForSalesOrderLine != null) OrElse ( obj.ReturnForInvoiceLine != null)) OrElse ( obj.HistoricalUnitCost != null)), False, True)`
`obj.SalesOrder.ApplyTradeConditions`
### BonusProgramAmount

The amount of the discount from the bonus program.

Type: **[Amount](../data-types.md#amount)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
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

Type: **[DeliveryTerms](Crm.Sales.SalesOrderLines.md#deliverytermscode) __nullable__**  
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
`obj.SalesOrder.DeliveryTermsCode`

Front-End Recalc Expressions:  
`obj.SalesOrder.DeliveryTermsCode`
### GuaranteePeriodDays

Guarantee period in days for the offered product. NULL for non-serviced products

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.Product != null), obj.Product.GuaranteePeriodDays, obj.GuaranteePeriodDays)`
### HistoricalDataJson

Used only for lines, which are returns. It is a JSON-formatted string, containing data from the original sale.[Introduced in version 19.1]

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### HistoricalUnitCost

Used for returning of goods that are sold before the exploitation of the system[Currency: SalesOrder.DocumentCurrency] [Filter(eq;ge;le)]

Type: **[Amount (14, 5)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### IntrastatApplyDate

Specifies in which period for Intrastat declaration must be included the current operation. Used only when the invoice is issued in different period than the one, that the operation must be included. If not set the document date is used.[Filter(ge;le)] [Introduced in version 21.1.3.83]

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### IntrastatTransactionNatureCode

Transaction nature; used for Intrastat reporting

Type: **[TransactionNature](Crm.Sales.SalesOrderLines.md#intrastattransactionnaturecode) __nullable__**  
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
`obj.SalesOrder.IntrastatTransactionNatureCode`

Front-End Recalc Expressions:  
`obj.SalesOrder.IntrastatTransactionNatureCode`
### IntrastatTransportModeCode

Transport mode; used for Intrastat reporting

Type: **[TransportMode](Crm.Sales.SalesOrderLines.md#intrastattransportmodecode) __nullable__**  
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
`obj.SalesOrder.IntrastatTransportModeCode`

Front-End Recalc Expressions:  
`obj.SalesOrder.IntrastatTransportModeCode`
### Level1DiscountAmount

The amount of the level 1 discount.

Type: **[Amount](../data-types.md#amount)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### Level1DiscountPercent

The percent of the level 1 discount.[ReadOnly] [Introduced in version 23.1.2.56]

Type: **decimal (7, 6) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.Level1Discount != null), Convert( obj.Level1Discount.DiscountPercent, Object), null)`
### Level2DiscountAmount

The cumulative amount of the level 2 discount.

Type: **[Amount](../data-types.md#amount)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### Level2DiscountPercent

The percent of the level 2 discount.[ReadOnly] [Introduced in version 23.1.2.8]

Type: **decimal (7, 6) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.Level2Discount != null), Convert( obj.Level2Discount.DiscountPercent, Object), null)`
### Level3DiscountAmount

The cumulative amount of the level 3 discount.

Type: **[Amount](../data-types.md#amount)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### Level3DiscountPercent

The percent of the level 3 discount.[ReadOnly] [Introduced in version 23.1.2.8]

Type: **decimal (7, 6) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.Level3Discount != null), Convert( obj.Level3Discount.DiscountPercent, Object), null)`
### LineAmount

The total amount for the line. Equals to Quantity * Unit_Price, less the discounts[Currency: SalesOrder.DocumentCurrency] [Required] [Default(0)]

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.UnitPrice == null)) OrElse ( ( obj.Quantity.Value == 0) AndAlso ( obj.UnitPrice.Value == 0))), obj.LineAmount, obj.CalculateLineAmount( obj.Quantity, obj.UnitPrice, obj.LineStandardDiscountPercent, obj.LineCustomDiscountPercent))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.UnitPrice == null)) OrElse ( ( obj.Quantity.Value == 0) AndAlso ( obj.UnitPrice.Value == 0))), obj.LineAmount, obj.CalculateLineAmount( obj.Quantity, obj.UnitPrice, obj.LineStandardDiscountPercent, obj.LineCustomDiscountPercent))`
### LineCustomDiscountPercent

User-defined discount for the line[Required] [Default(0)] [Filter(ge;le)]

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### LineFromDate

When selling a service valid only for a period, denotes the beginning of the period. NULL means that it is unknown or N/A.[Filter(ge;le)] [Introduced in version 20.1]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.SalesOrder.FromDate`

Front-End Recalc Expressions:  
`obj.SalesOrder.FromDate`
### LineNo

Consecutive number of the line within the sales order[Required] [Filter(eq)] [ORD]

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.SalesOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.SalesOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineStandardDiscountPercent

Standard discount percent for the line. It is calculated by accumulating in cascade the line discounts at all levels.[Required] [Default(0)] [ReadOnly]

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.DetermineLineStandardDiscountPercent( obj.Product, obj.BonusProgram, obj.PromotionalPackage, obj.ReturnForSalesOrderLine, obj.Level1Discount, obj.Level2Discount, obj.Level3Discount)`

Front-End Recalc Expressions:  
`obj.DetermineLineStandardDiscountPercent( obj.Product, obj.BonusProgram, obj.PromotionalPackage, obj.ReturnForSalesOrderLine, obj.Level1Discount, obj.Level2Discount, obj.Level3Discount)`
### LineToDate

When selling a service valid only for a period, denotes the end of the period. NULL means that it is unknown or N/A.[Filter(ge;le)] [Introduced in version 20.1]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.SalesOrder.ToDate`

Front-End Recalc Expressions:  
`obj.SalesOrder.ToDate`
### Notes

Notes for this SalesOrderLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. NULL when the current line does not execute parent line.[Filter(eq)]

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### PersistLot

If checked specifies that the lot in the line cannot be changed in the sub-documents created by the current document.[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`( ( obj.Lot != null) AndAlso obj.SalesOrder.Customer.PersistSalesOrdersLots)`

Front-End Recalc Expressions:  
`( ( obj.Lot != null) AndAlso obj.SalesOrder.Customer.PersistSalesOrdersLots)`
### ProductDescription

The name of the sold product at the time the sale was made[Required] [Filter(like)]

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Product.Name`

Front-End Recalc Expressions:  
`obj.Product.Name`
### PromotionalPackageAmount

The amount of the discount from the relative promotional package line.

Type: **[Amount](../data-types.md#amount)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### Quantity

The quantity sold[Unit: QuantityUnit] [Required] [Default(1)] [Filter(ge;le)]

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### QuantityBase

The equivalent of Quantity in the base measurement category of the product[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required]

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### RequestedQuantity

Quantity requested by customer[Unit: QuantityUnit]

Type: **[Quantity (12, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### RequiredDeliveryDate

The required (contracted) delivery date for the line[Filter(ge;le)]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.SalesOrder.RequiredDeliveryDate`

Front-End Recalc Expressions:  
`obj.SalesOrder.RequiredDeliveryDate`
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
### StandardUnitPrice

Standard unit price of the product during the creation of the sales order line[Currency: SalesOrder.DocumentCurrency] [ReadOnly]

Type: **[Amount (14, 5)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Product.GetStandardUnitPrice( obj.QuantityUnit, obj.SalesOrder.DocumentCurrency, obj.SalesOrder.CurrencyDirectory)`

Front-End Recalc Expressions:  
`obj.Product.GetStandardUnitPrice( obj.QuantityUnit, obj.SalesOrder.DocumentCurrency, obj.SalesOrder.CurrencyDirectory)`
### UnitPrice

Unit price of the product in the currency of the sales order and in the unit of measure, as specified by QuantityUnitId[Currency: SalesOrder.DocumentCurrency] [Required] [Default(0)]

Type: **[Amount (14, 5)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( CalculateUnitPriceFromLineAmount( obj.LineAmount, obj.Quantity, obj.LineStandardDiscountPercent, obj.LineCustomDiscountPercent) ?? obj.UnitPrice)`

Front-End Recalc Expressions:  
`obj.CalculateUnitPrice( obj.SalesOrder, obj.QuantityUnit, obj.Product, obj.ProductPrice)`
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

### BonusProgram

The bonus program, based on which the line was automatically added. NULL when the line was not added for bonus program.

Type: **[BonusPrograms](Crm.Pricing.BonusPrograms.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ReturnForSalesOrderLine != null), null, obj.BonusProgram)`
### Document

The owner document. The <see cref="SalesOrder"/> to which this SalesOrderLine belongs. `Required` `Filter(multi eq)`

Type: **[SalesOrders](Crm.Sales.SalesOrders.md)**  
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
`obj.SalesOrder.IntrastatTransportCountry`

Front-End Recalc Expressions:  
`obj.SalesOrder.IntrastatTransportCountry`
### Level1Discount

Indicates the level 1 discount.

Type: **[LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.DetermineLineDiscount( obj.SalesOrder.EnterpriseCompany, obj.SalesOrder.EnterpriseCompanyLocation, obj.RequiredDeliveryDate, obj.SalesOrder.Customer, obj.SalesOrder.ShipToCustomer, obj.SalesOrder.DistributionChannel, obj.SalesOrder.PriceList, obj.Product, obj.Quantity, obj.QuantityUnit, obj.ApplyTradeConditions, null, obj.PromotionalPackage, obj.Level1Discount, 0)`
### Level2Discount

Indicates the level 2 discount.

Type: **[LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.DetermineLineDiscount( obj.SalesOrder.EnterpriseCompany, obj.SalesOrder.EnterpriseCompanyLocation, obj.RequiredDeliveryDate, obj.SalesOrder.Customer, obj.SalesOrder.ShipToCustomer, obj.SalesOrder.DistributionChannel, obj.SalesOrder.PriceList, obj.Product, obj.Quantity, obj.QuantityUnit, obj.ApplyTradeConditions, null, obj.PromotionalPackage, obj.Level2Discount, 1)`
### Level3Discount

Indicates the level 3 discount.

Type: **[LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.DetermineLineDiscount( obj.SalesOrder.EnterpriseCompany, obj.SalesOrder.EnterpriseCompanyLocation, obj.RequiredDeliveryDate, obj.SalesOrder.Customer, obj.SalesOrder.ShipToCustomer, obj.SalesOrder.DistributionChannel, obj.SalesOrder.PriceList, obj.Product, obj.Quantity, obj.QuantityUnit, obj.ApplyTradeConditions, null, obj.PromotionalPackage, obj.Level3Discount, 2)`
### LineDealType

Deal type to be passed to the invoice line. If deal type in entered then the invoice creates VAT entry for this deal type.

Type: **[DealTypes](Regulatory.Vat.DealTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.SalesOrder.DealType`

Front-End Recalc Expressions:  
`obj.SalesOrder.DealType`
### LineDiscount

**OBSOLETE! Do not use!** The line discount type used to form the Line_Standard_Discount_Percent

Type: **[LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### LineEndCustomerParty

The end customer is the customer of the dealer. It is stored for information purposes only. The end customer may not have customer definition, just party.

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.SalesOrder.EndCustomerParty`

Front-End Recalc Expressions:  
`obj.SalesOrder.EndCustomerParty`
### LineStore

The store which should be used to issue the goods for the line. NULL means to use the store from the header

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.SalesOrder.Store`

Front-End Recalc Expressions:  
`obj.SalesOrder.Store`
### Lot

Specifies the lot from which the goods should be issued. NULL means that the lot will be specified at a later stage (store order, etc.)

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

The product sold

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( ( obj.BonusProgram != null) AndAlso ( Convert( obj.BonusProgram.BonusAction, Int32) == 0)), obj.BonusProgram.BonusProduct, IIF( ( ( obj.ProductCode.Product != null) AndAlso ( obj.ProductCode.Product.Active == True)), obj.ProductCode.Product, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( obj.BonusProgram != null) AndAlso ( Convert( obj.BonusProgram.BonusAction, Int32) == 0)), obj.BonusProgram.BonusProduct, IIF( ( ( obj.ProductCode.Product != null) AndAlso ( obj.ProductCode.Product.Active == True)), obj.ProductCode.Product, obj.Product))`
### ProductCode

Used to set the Product_Id thru the coding systems

Type: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ProductPrice

Not NULL when the price has been selected from the list of valid standard prices

Type: **[ProductPrices](Crm.Pricing.ProductPrices.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ApplyTradeConditions == False), obj.ProductPrice, IIF( ( ( ( obj.BonusProgram != null) AndAlso ( Convert( obj.BonusProgram.BonusAction, Int32) == 0)) OrElse ( obj.ReturnForSalesOrderLine != null)), null, DetermineProductPrice( obj.Product, obj.Quantity, obj.QuantityUnit, obj.RequiredDeliveryDate, obj.SalesOrder.Customer, obj.SalesOrder.ShipToCustomer, obj.SalesOrder.EnterpriseCompany, obj.SalesOrder.EnterpriseCompanyLocation, obj.SalesOrder.DistributionChannel, obj.SalesOrder.PriceList, obj.ProductPrice)))`
### ProductVariant

If specified determines which product variant of the current product in this line is used.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### PromotionalPackage

The promotional package, based on which the line was added. NULL when the line was not added as part of a promotional package

Type: **[PromotionalPackages](Crm.Pricing.PromotionalPackages.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ReturnForSalesOrderLine != null), null, obj.PromotionalPackage)`
### QuantityUnit

The measurement unit of Quantity

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.MeasurementUnit.IfNullThen( obj.QuantityUnit))`

Front-End Recalc Expressions:  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.MeasurementUnit.IfNullThen( obj.QuantityUnit))`
### ReturnForInvoiceLine

When specified, indicates that the current line is a return for products, invoiced with the specified invoice line.

Type: **[InvoiceLines](Crm.Invoicing.InvoiceLines.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ReturnForSalesOrderLine

When specified indicates that the goods sold in Return_For_Sales_Order_Line_Id are returned with the current line

Type: **[SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### SalesOrder

The <see cref="SalesOrder"/> to which this SalesOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[SalesOrders](Crm.Sales.SalesOrders.md)**  
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

The bin from which the goods should be withdrawn. NULL means that the bin will be specified at a later stage (store order, etc.)

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

[!list limit=1000 erp.entity=Crm.Sales.SalesOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Sales.SalesOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Sales_SalesOrderLines

Domain API Entity Type: 
Crm_Sales_SalesOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Sales_SalesOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Sales_SalesOrderLines?$top=10>

