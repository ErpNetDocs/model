---
uid: Logistics.Procurement.ProductSupply
---
# Logistics.Procurement.ProductSupply


Contains supply rules, which are used by the procurement planning system.

## General
Namespace: [Logistics.Procurement](Logistics.Procurement.md)  
Repository: Logistics.Procurement.ProductSupply  
Base Table: Gen_Product_Supply  
API access:  ReadWrite  

## Renames

Old name: General.Products.ProductSupply  
New name: Logistics.Procurement.ProductSupply  
Version: 25.1.1.48  
Case: 37717  



## Visualization
Display Format: {ProcurementType} {Product.PartNumber}: {Product.Name:T} ({Store.Name:T})  
Search Members: Product.PartNumber; Product.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Procurement.ProductSupply](Logistics.Procurement.ProductSupply.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BuyerName](Logistics.Procurement.ProductSupply.md#buyername) | string (64) __nullable__ | The code or name of the person, who is in charge for purchasing the product from external suppliers. It is used to group different products on purchase demand report. NULL when Procurement_Type is not buy 
| [FixedOrderQuantityBase](Logistics.Procurement.ProductSupply.md#fixedorderquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Fixed order quantity under the FOQ & EOQ replenishment system`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 
| [IsActive](Logistics.Procurement.ProductSupply.md#isactive) | boolean | 1 if this product supply is active`Required` `Default(true)` `Filter(eq)` 
| [IsDefault](Logistics.Procurement.ProductSupply.md#isdefault) | boolean | Specifies whether this is the default supply rule. The planning system works using *only* the default supply rules. The other rules are for reference and user information.`Required` `Default(true)` `Filter(eq)` 
| [ManufacturingPolicy](Logistics.Procurement.ProductSupply.md#manufacturingpolicy) | [ManufacturingPolicy](Logistics.Procurement.ProductSupply.md#manufacturingpolicy) | MTS=Make-To-Stock; MTO=Make-To-Order; ATO=Assemble-To-Order;ETO=Engineer-To-<br />Order`Required` `Default(&quot;MTS&quot;)` `Filter(eq)` 
| [OrderLotSizeQuantityBase](Logistics.Procurement.ProductSupply.md#orderlotsizequantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity of the product, normally ordered from the plant or supplier. The quantity is expressed in the base measurement unit`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(1)` 
| [OrderLotSizingMethod](Logistics.Procurement.ProductSupply.md#orderlotsizingmethod) | [OrderLotSizingMethod](Logistics.Procurement.ProductSupply.md#orderlotsizingmethod) | LFL=Lot for Lot; FOQ=Fixed order quantity; EOQ=Eqonomic Order Quantity; ROP=ReOrder Point; ROT=ReOrder point with Time planning; LFP = Lot For Period;`Required` `Default(&quot;ROP&quot;)` `Filter(eq)` 
| [OrderMaximum](Logistics.Procurement.ProductSupply.md#ordermaximum) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Order maximum when buying or making. NULL means no maximum`Unit: Product.BaseMeasurementCategory.BaseUnit` 
| [OrderMinimum](Logistics.Procurement.ProductSupply.md#orderminimum) | [Quantity (18, 3)](../data-types.md#quantity) | Minimum order quantity both for buying and making`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(eq;ge;le)` 
| [OrderMultiple](Logistics.Procurement.ProductSupply.md#ordermultiple) | boolean | 1 if the order qty should be multiple of lot size when buying or making`Required` `Default(false)` 
| [OrderPeriodPlanningDays](Logistics.Procurement.ProductSupply.md#orderperiodplanningdays) | int32 __nullable__ | For how many days in the future should be planned - for fixed period replenishment system. NULL - not yet specified 
| [OrderPeriodStartDate](Logistics.Procurement.ProductSupply.md#orderperiodstartdate) | datetime __nullable__ | Start date of the first period under fixed period replenishment system. NULL - not yet specified`Filter(ge;le)` 
| [OrderPointQuantityBase](Logistics.Procurement.ProductSupply.md#orderpointquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Order point quantity under the OP replenishment system`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(eq;ge;le)` 
| [OrderPolicy](Logistics.Procurement.ProductSupply.md#orderpolicy) | [OrderPolicy](Logistics.Procurement.ProductSupply.md#orderpolicy) | Order policy/replenishment system. OPS=Order Point System; OPT=Order Point System with Time planning; PRS=Periodic Review System/Periods Of Supply; MRP = Material Requirements Planning`Required` `Default(&quot;OPS&quot;)` `Filter(eq)` 
| [PlanningAnnual<br />CarryingCostPercent](Logistics.Procurement.ProductSupply.md#planningannualcarryingcostpercent) | decimal (5, 4) __nullable__ | The expected carrying cost as percentage of inventory cost. NULL means unknown 
| [PlanningAnnual<br />UsageQuantityBase](Logistics.Procurement.ProductSupply.md#planningannualusagequantitybase) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Average usage of the product for 1 year. NUL means unknown`Unit: Product.BaseMeasurementCategory.BaseUnit` 
| [PlanningHorizonDays](Logistics.Procurement.ProductSupply.md#planninghorizondays) | int32 | Number of days in the future for which to plan the demand and supply`Required` `Default(0)` 
| [PlanningLeadTimeDays](Logistics.Procurement.ProductSupply.md#planningleadtimedays) | int32 | The number of days required to supply or manufacture the product. The number is exclusive of the lead-time of lower-level components`Required` `Default(0)` 
| [PlanningMaximum<br />InventoryQuantity<br />Base](Logistics.Procurement.ProductSupply.md#planningmaximuminventoryquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Maximum inventory. NULL if N/A`Unit: Product.BaseMeasurementCategory.BaseUnit` 
| [PlanningOrderCost<br />BaseCurrency](Logistics.Procurement.ProductSupply.md#planningordercostbasecurrency) | [Amount (18, 3)](../data-types.md#amount) __nullable__ | Projected cost to place an order and set-up equipment`Currency: EnterpriseCompany.BaseCurrency` 
| [PlanningOrderCycleDays](Logistics.Procurement.ProductSupply.md#planningordercycledays) | int32 __nullable__ | Number of days in one period under fixed period replenishment system. NULL - not yet specified 
| [PlanningSafety<br />StockQuantityBase](Logistics.Procurement.ProductSupply.md#planningsafetystockquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Planned lowest inventory level, protecting against unplanned demands. The quantity is expressed in the base measurement unit of the product`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 
| [PlanningTimeFenceDays](Logistics.Procurement.ProductSupply.md#planningtimefencedays) | int32 | Period in the future inside of which changes to the MPS are carefully evaluated to prevent costly schedule disruption. Demand for the period between DTF and PTF is calculated as the bigger of customer orders and sales forecast. Abbr. - PTF`Required` `Default(1)` 
| [ProcurementType](Logistics.Procurement.ProductSupply.md#procurementtype) | [ProcurementType](Logistics.Procurement.ProductSupply.md#procurementtype) | M=Make; B=Buy; T=Transfer.  Identifies whether the product is produced or externally bought`Required` `Default(&quot;B&quot;)` `Filter(eq)` 
| [StandardCostPerLot](Logistics.Procurement.ProductSupply.md#standardcostperlot) | [Amount (18, 4)](../data-types.md#amount) | Standard cost for one lot of the product`Currency: Product.CostingCurrency` `Required` `Default(0)` 
| [SupplySchemaId](Logistics.Procurement.ProductSupply.md#supplyschemaid) | guid __nullable__ | The supply schema to use for the distribution of the product among warehouses. `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultStoreBin](Logistics.Procurement.ProductSupply.md#defaultstorebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | Default store bin for new deliveries using this supply scheme |
| [EnterpriseCompany](Logistics.Procurement.ProductSupply.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this ProductSupply applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [FromStore](Logistics.Procurement.ProductSupply.md#fromstore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | Used when the Procurement_Type is Transfer |
| [GenerateDocumentType](Logistics.Procurement.ProductSupply.md#generatedocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | Specifies the type of the document which should be generated by the procurement planning system, when generating supply based on this rule. |
| [PreferredSupplier](Logistics.Procurement.ProductSupply.md#preferredsupplier) | [Suppliers](Logistics.Procurement.Suppliers.md) (nullable) | Preferred supplier for the product. NULL if there is no preferred supplier |
| [Product](Logistics.Procurement.ProductSupply.md#product) | [Products](General.Products.Products.md) (nullable) | The <see cref="General.Products.Product"/> to which this ProductSupply belongs. `Filter(multi eq)` `FilterableReference` |
| [ProductGroup](Logistics.Procurement.ProductSupply.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) (nullable) | Product group - the new products in the group copy it's supply method from this method |
| [Store](Logistics.Procurement.ProductSupply.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store for which this rule is defined. When null, the rule is valid for all stores. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Procurement.ProductSupply.md#id) | guid |  
| [ObjectVersion](Logistics.Procurement.ProductSupply.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Logistics.Procurement.ProductSupply.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Procurement.ProductSupply.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Logistics.Procurement.ProductSupply.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Logistics.Procurement.ProductSupply.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BuyerName

The code or name of the person, who is in charge for purchasing the product from external suppliers. It is used to group different products on purchase demand report. NULL when Procurement_Type is not buy

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### FixedOrderQuantityBase

Fixed order quantity under the FOQ & EOQ replenishment system`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

### IsActive

1 if this product supply is active`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **HiddenByDefault**  

### IsDefault

Specifies whether this is the default supply rule. The planning system works using *only* the default supply rules. The other rules are for reference and user information.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **HiddenByDefault**  

### ManufacturingPolicy

MTS=Make-To-Stock; MTO=Make-To-Order; ATO=Assemble-To-Order;ETO=Engineer-To-Order`Required` `Default(&quot;MTS&quot;)` `Filter(eq)`

Type: **[ManufacturingPolicy](Logistics.Procurement.ProductSupply.md#manufacturingpolicy)**  
Category: **System**  
Allowed values for the `ManufacturingPolicy`(Logistics.Procurement.ProductSupply.md#manufacturingpolicy) data attribute  
Allowed Values (Logistics.Procurement.ProductSupplyRepository.ManufacturingPolicy Enum Members)  

| Value | Description |
| ---- | --- |
| AssembleToOrder | AssembleToOrder value. Stored as 'ATO'. <br /> Database Value: 'ATO' <br /> Model Value: 0 <br /> Domain API Value: 'AssembleToOrder' |
| MakeToOrder | MakeToOrder value. Stored as 'MTO'. <br /> Database Value: 'MTO' <br /> Model Value: 1 <br /> Domain API Value: 'MakeToOrder' |
| MakeToStock | MakeToStock value. Stored as 'MTS'. <br /> Database Value: 'MTS' <br /> Model Value: 2 <br /> Domain API Value: 'MakeToStock' |
| EngineerToOrder | EngineerToOrder value. Stored as 'ETO'. <br /> Database Value: 'ETO' <br /> Model Value: 3 <br /> Domain API Value: 'EngineerToOrder' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **MakeToStock**  
Show in UI: **HiddenByDefault**  

### OrderLotSizeQuantityBase

The quantity of the product, normally ordered from the plant or supplier. The quantity is expressed in the base measurement unit`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(1)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### OrderLotSizingMethod

LFL=Lot for Lot; FOQ=Fixed order quantity; EOQ=Eqonomic Order Quantity; ROP=ReOrder Point; ROT=ReOrder point with Time planning; LFP = Lot For Period;`Required` `Default(&quot;ROP&quot;)` `Filter(eq)`

Type: **[OrderLotSizingMethod](Logistics.Procurement.ProductSupply.md#orderlotsizingmethod)**  
Category: **System**  
Allowed values for the `OrderLotSizingMethod`(Logistics.Procurement.ProductSupply.md#orderlotsizingmethod) data attribute  
Allowed Values (Logistics.Procurement.ProductSupplyRepository.OrderLotSizingMethod Enum Members)  

| Value | Description |
| ---- | --- |
| EconomicOrderQuantity | EconomicOrderQuantity value. Stored as 'EOQ'. <br /> Database Value: 'EOQ' <br /> Model Value: 0 <br /> Domain API Value: 'EconomicOrderQuantity' |
| FixedOrderQuantity | FixedOrderQuantity value. Stored as 'FOQ'. <br /> Database Value: 'FOQ' <br /> Model Value: 1 <br /> Domain API Value: 'FixedOrderQuantity' |
| LotForLot | LotForLot value. Stored as 'LFL'. <br /> Database Value: 'LFL' <br /> Model Value: 2 <br /> Domain API Value: 'LotForLot' |
| LotForPeriod | LotForPeriod value. Stored as 'LFP'. <br /> Database Value: 'LFP' <br /> Model Value: 3 <br /> Domain API Value: 'LotForPeriod' |
| ReorderPoint | ReorderPoint value. Stored as 'ROP'. <br /> Database Value: 'ROP' <br /> Model Value: 4 <br /> Domain API Value: 'ReorderPoint' |
| ReorderPointWith<br />TimePlanning | ReorderPointWith<br />TimePlanning value. Stored as 'ROT'. <br /> Database Value: 'ROT' <br /> Model Value: 5 <br /> Domain API Value: 'ReorderPointWith<br />TimePlanning' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **ReorderPoint**  
Show in UI: **HiddenByDefault**  

### OrderMaximum

Order maximum when buying or making. NULL means no maximum`Unit: Product.BaseMeasurementCategory.BaseUnit`

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### OrderMinimum

Minimum order quantity both for buying and making`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(eq;ge;le)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

### OrderMultiple

1 if the order qty should be multiple of lot size when buying or making`Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### OrderPeriodPlanningDays

For how many days in the future should be planned - for fixed period replenishment system. NULL - not yet specified

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### OrderPeriodStartDate

Start date of the first period under fixed period replenishment system. NULL - not yet specified`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### OrderPointQuantityBase

Order point quantity under the OP replenishment system`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(eq;ge;le)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### OrderPolicy

Order policy/replenishment system. OPS=Order Point System; OPT=Order Point System with Time planning; PRS=Periodic Review System/Periods Of Supply; MRP = Material Requirements Planning`Required` `Default(&quot;OPS&quot;)` `Filter(eq)`

Type: **[OrderPolicy](Logistics.Procurement.ProductSupply.md#orderpolicy)**  
Category: **System**  
Allowed values for the `OrderPolicy`(Logistics.Procurement.ProductSupply.md#orderpolicy) data attribute  
Allowed Values (Logistics.Procurement.ProductSupplyRepository.OrderPolicy Enum Members)  

| Value | Description |
| ---- | --- |
| MaterialRequirements<br />Planning | MaterialRequirements<br />Planning value. Stored as 'MRP'. <br /> Database Value: 'MRP' <br /> Model Value: 0 <br /> Domain API Value: 'MaterialRequirements<br />Planning' |
| OrderPointSystem | OrderPointSystem value. Stored as 'OPS'. <br /> Database Value: 'OPS' <br /> Model Value: 1 <br /> Domain API Value: 'OrderPointSystem' |
| OrderPointSystem<br />WithTimePlanning | OrderPointSystem<br />WithTimePlanning value. Stored as 'OPT'. <br /> Database Value: 'OPT' <br /> Model Value: 2 <br /> Domain API Value: 'OrderPointSystem<br />WithTimePlanning' |
| PeriodicReviewSystem | PeriodicReviewSystem value. Stored as 'PRS'. <br /> Database Value: 'PRS' <br /> Model Value: 3 <br /> Domain API Value: 'PeriodicReviewSystem' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **OrderPointSystem**  
Show in UI: **HiddenByDefault**  

### PlanningAnnualCarryingCostPercent

The expected carrying cost as percentage of inventory cost. NULL means unknown

Type: **decimal (5, 4) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### PlanningAnnualUsageQuantityBase

Average usage of the product for 1 year. NUL means unknown`Unit: Product.BaseMeasurementCategory.BaseUnit`

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### PlanningHorizonDays

Number of days in the future for which to plan the demand and supply`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **CannotBeShown**  

### PlanningLeadTimeDays

The number of days required to supply or manufacture the product. The number is exclusive of the lead-time of lower-level components`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.PreferredSupplier.DefaultDeliveryTermDays`
### PlanningMaximumInventoryQuantityBase

Maximum inventory. NULL if N/A`Unit: Product.BaseMeasurementCategory.BaseUnit`

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PlanningOrderCostBaseCurrency

Projected cost to place an order and set-up equipment`Currency: EnterpriseCompany.BaseCurrency`

Type: **[Amount (18, 3)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### PlanningOrderCycleDays

Number of days in one period under fixed period replenishment system. NULL - not yet specified

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### PlanningSafetyStockQuantityBase

Planned lowest inventory level, protecting against unplanned demands. The quantity is expressed in the base measurement unit of the product`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

### PlanningTimeFenceDays

Period in the future inside of which changes to the MPS are carefully evaluated to prevent costly schedule disruption. Demand for the period between DTF and PTF is calculated as the bigger of customer orders and sales forecast. Abbr. - PTF`Required` `Default(1)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **CannotBeShown**  

### ProcurementType

M=Make; B=Buy; T=Transfer.  Identifies whether the product is produced or externally bought`Required` `Default(&quot;B&quot;)` `Filter(eq)`

Type: **[ProcurementType](Logistics.Procurement.ProductSupply.md#procurementtype)**  
Category: **System**  
Allowed values for the `ProcurementType`(Logistics.Procurement.ProductSupply.md#procurementtype) data attribute  
Allowed Values (Logistics.Procurement.ProductSupplyRepository.ProcurementType Enum Members)  

| Value | Description |
| ---- | --- |
| Buy | Buy value. Stored as 'B'. <br /> Database Value: 'B' <br /> Model Value: 0 <br /> Domain API Value: 'Buy' |
| Make | Make value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 1 <br /> Domain API Value: 'Make' |
| Transfer | Transfer value. Stored as 'T'. <br /> Database Value: 'T' <br /> Model Value: 2 <br /> Domain API Value: 'Transfer' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Buy**  
Show in UI: **HiddenByDefault**  

### StandardCostPerLot

Standard cost for one lot of the product`Currency: Product.CostingCurrency` `Required` `Default(0)`

Type: **[Amount (18, 4)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

### SupplySchemaId

The supply schema to use for the distribution of the product among warehouses. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

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

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

### DefaultStoreBin

Default store bin for new deliveries using this supply scheme

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### EnterpriseCompany

The Enterprise Company to which this ProductSupply applies, or null if it is for all enterprise companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### FromStore

Used when the Procurement_Type is Transfer

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### GenerateDocumentType

Specifies the type of the document which should be generated by the procurement planning system, when generating supply based on this rule.

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PreferredSupplier

Preferred supplier for the product. NULL if there is no preferred supplier

Type: **[Suppliers](Logistics.Procurement.Suppliers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The <see cref="General.Products.Product"/> to which this ProductSupply belongs. `Filter(multi eq)` `FilterableReference`

Type: **[Products](General.Products.Products.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ProductGroup

Product group - the new products in the group copy it's supply method from this method

Type: **[ProductGroups](General.Products.ProductGroups.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Store

The store for which this rule is defined. When null, the rule is valid for all stores.

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Logistics.Procurement.ProductSupply erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Procurement.ProductSupply erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Procurement_ProductSupply

Domain API Entity Type: 
Logistics_Procurement_ProductSupply

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Procurement_ProductSupply?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Procurement_ProductSupply?$top=10>

