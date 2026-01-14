---
uid: Logistics.Procurement.ProductSupply
---
# Logistics.Procurement.ProductSupply Entity

**Namespace:** [Logistics.Procurement](Logistics.Procurement.md)  

Contains supply rules, which are used by the procurement planning system. Entity: Gen_Product_Supply

## Renames

Old name: **General.Products.ProductSupply**  
New name: **Logistics.Procurement.ProductSupply**  
Version: **25.1.1.48**  
Case: **37717**  



## Default Visualization
Default Display Text Format:  
_{ProcurementType} {Product.PartNumber}: {Product.Name:T} ({Store.Name:T})_  
Default Search Members:  
_Product.PartNumber; Product.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Procurement.ProductSupply](Logistics.Procurement.ProductSupply.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Logistics.Procurement.ProductSupply.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [BuyerName](Logistics.Procurement.ProductSupply.md#buyername) | string (64) __nullable__ | The code or name of the person, who is in charge for purchasing the product from external suppliers. It is used to group different products on purchase demand report. null when Procurement_Type is not buy. 
| [DisplayText](Logistics.Procurement.ProductSupply.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Logistics.Procurement.ProductSupply.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Procurement.ProductSupply.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FixedOrderQuantityBase](Logistics.Procurement.ProductSupply.md#fixedorderquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Fixed order quantity under the FOQ &amp; EOQ replenishment system. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 
| [Id](Logistics.Procurement.ProductSupply.md#id) | guid |  
| [IsActive](Logistics.Procurement.ProductSupply.md#isactive) | boolean | True if this product supply is active. `Required` `Default(true)` `Filter(eq)` 
| [IsDefault](Logistics.Procurement.ProductSupply.md#isdefault) | boolean | Specifies whether this is the default supply rule. The planning system works using *only* the default supply rules. The other rules are for reference and user information. `Required` `Default(true)` `Filter(eq)` 
| [ManufacturingPolicy](Logistics.Procurement.ProductSupply.md#manufacturingpolicy) | [ManufacturingPolicy](Logistics.Procurement.ProductSupply.md#manufacturingpolicy) | MTS=Make-To-Stock; MTO=Make-To-Order; ATO=Assemble-To-Order;ETO=Engineer-To-Order. `Required` `Default("MTS")` `Filter(eq)` 
| [ObjectVersion](Logistics.Procurement.ProductSupply.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [OrderLotSizeQuantityBase](Logistics.Procurement.ProductSupply.md#orderlotsizequantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity of the product, normally ordered from the plant or supplier. The quantity is expressed in the base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(1)` 
| [OrderLotSizingMethod](Logistics.Procurement.ProductSupply.md#orderlotsizingmethod) | [OrderLotSizingMethod](Logistics.Procurement.ProductSupply.md#orderlotsizingmethod) | LFL=Lot for Lot; FOQ=Fixed order quantity; EOQ=Eqonomic Order Quantity; ROP=ReOrder Point; ROT=ReOrder point with Time planning; LFP = Lot For Period;. `Required` `Default("ROP")` `Filter(eq)` 
| [OrderMaximum](Logistics.Procurement.ProductSupply.md#ordermaximum) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Order maximum when buying or making. null means no maximum. `Unit: Product.BaseMeasurementCategory.BaseUnit` 
| [OrderMinimum](Logistics.Procurement.ProductSupply.md#orderminimum) | [Quantity (18, 3)](../data-types.md#quantity) | Minimum order quantity both for buying and making. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(eq;ge;le)` 
| [OrderMultiple](Logistics.Procurement.ProductSupply.md#ordermultiple) | boolean | True if the order qty should be multiple of lot size when buying or making. `Required` `Default(false)` 
| [OrderPeriodPlanningDays](Logistics.Procurement.ProductSupply.md#orderperiodplanningdays) | int32 __nullable__ | For how many days in the future should be planned - for fixed period replenishment system. null - not yet specified. 
| [OrderPeriodStartDate](Logistics.Procurement.ProductSupply.md#orderperiodstartdate) | datetime __nullable__ | Start date of the first period under fixed period replenishment system. null - not yet specified. `Filter(ge;le)` 
| [OrderPointQuantityBase](Logistics.Procurement.ProductSupply.md#orderpointquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Order point quantity under the OP replenishment system. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(eq;ge;le)` 
| [OrderPolicy](Logistics.Procurement.ProductSupply.md#orderpolicy) | [OrderPolicy](Logistics.Procurement.ProductSupply.md#orderpolicy) | Order policy/replenishment system. OPS=Order Point System; OPT=Order Point System with Time planning; PRS=Periodic Review System/Periods Of Supply; MRP = Material Requirements Planning. `Required` `Default("OPS")` `Filter(eq)` 
| [PlanningAnnual<br />CarryingCostPercent](Logistics.Procurement.ProductSupply.md#planningannualcarryingcostpercent) | decimal (5, 4) __nullable__ | The expected carrying cost as percentage of inventory cost. null means unknown. 
| [PlanningAnnual<br />UsageQuantityBase](Logistics.Procurement.ProductSupply.md#planningannualusagequantitybase) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Average usage of the product for 1 year. NUL means unknown. `Unit: Product.BaseMeasurementCategory.BaseUnit` 
| [PlanningHorizonDays](Logistics.Procurement.ProductSupply.md#planninghorizondays) | int32 | Number of days in the future for which to plan the demand and supply. `Required` `Default(0)` 
| [PlanningLeadTimeDays](Logistics.Procurement.ProductSupply.md#planningleadtimedays) | int32 | The number of days required to supply or manufacture the product. The number is exclusive of the lead-time of lower-level components. `Required` `Default(0)` 
| [PlanningMaximum<br />InventoryQuantity<br />Base](Logistics.Procurement.ProductSupply.md#planningmaximuminventoryquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Maximum inventory. null if N/A. `Unit: Product.BaseMeasurementCategory.BaseUnit` 
| [PlanningOrderCost<br />BaseCurrency](Logistics.Procurement.ProductSupply.md#planningordercostbasecurrency) | [Amount (18, 3)](../data-types.md#amount) __nullable__ | Projected cost to place an order and set-up equipment. `Currency: EnterpriseCompany.BaseCurrency` 
| [PlanningOrderCycleDays](Logistics.Procurement.ProductSupply.md#planningordercycledays) | int32 __nullable__ | Number of days in one period under fixed period replenishment system. null - not yet specified. 
| [PlanningSafety<br />StockQuantityBase](Logistics.Procurement.ProductSupply.md#planningsafetystockquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Planned lowest inventory level, protecting against unplanned demands. The quantity is expressed in the base measurement unit of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 
| [PlanningTimeFenceDays](Logistics.Procurement.ProductSupply.md#planningtimefencedays) | int32 | Period in the future inside of which changes to the MPS are carefully evaluated to prevent costly schedule disruption. Demand for the period between DTF and PTF is calculated as the bigger of customer orders and sales forecast. Abbr. - PTF. `Required` `Default(1)` 
| [ProcurementType](Logistics.Procurement.ProductSupply.md#procurementtype) | [ProcurementType](Logistics.Procurement.ProductSupply.md#procurementtype) | M=Make; B=Buy; T=Transfer.  Identifies whether the product is produced or externally bought. `Required` `Default("B")` `Filter(eq)` 
| [StandardCostPerLot](Logistics.Procurement.ProductSupply.md#standardcostperlot) | [Amount (18, 4)](../data-types.md#amount) | Standard cost for one lot of the product. `Currency: Product.CostingCurrency` `Required` `Default(0)` 
| [SupplySchemaId](Logistics.Procurement.ProductSupply.md#supplyschemaid) | guid __nullable__ | The supply schema to use for the distribution of the product among warehouses. `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultStoreBin](Logistics.Procurement.ProductSupply.md#defaultstorebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | Default store bin for new deliveries using this supply scheme. `Filter(multi eq)` |
| [EnterpriseCompany](Logistics.Procurement.ProductSupply.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this ProductSupply applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [FromStore](Logistics.Procurement.ProductSupply.md#fromstore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | Used when the Procurement_Type is Transfer. `Filter(multi eq)` |
| [GenerateDocumentType](Logistics.Procurement.ProductSupply.md#generatedocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | Specifies the type of the document which should be generated by the procurement planning system, when generating supply based on this rule. `Filter(multi eq)` |
| [PreferredSupplier](Logistics.Procurement.ProductSupply.md#preferredsupplier) | [Suppliers](Logistics.Procurement.Suppliers.md) (nullable) | Preferred supplier for the product. null if there is no preferred supplier. `Filter(multi eq)` |
| [Product](Logistics.Procurement.ProductSupply.md#product) | [Products](General.Products.Products.md) (nullable) | The <see cref="General.Products.Product"/> to which this ProductSupply belongs. `Filter(multi eq)` `FilterableReference` |
| [ProductGroup](Logistics.Procurement.ProductSupply.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) (nullable) | Not null when the method is a default method for a whole product group. In this case new products in the group inherit the settings. `Filter(multi eq)` |
| [Store](Logistics.Procurement.ProductSupply.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store for which this rule is defined. When null, the rule is valid for all stores. `Filter(multi eq)` |


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### BuyerName

The code or name of the person, who is in charge for purchasing the product from external suppliers. It is used to group different products on purchase demand report. null when Procurement_Type is not buy.

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### FixedOrderQuantityBase

Fixed order quantity under the FOQ &amp; EOQ replenishment system. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

True if this product supply is active. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **HiddenByDefault**  

### IsDefault

Specifies whether this is the default supply rule. The planning system works using *only* the default supply rules. The other rules are for reference and user information. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **HiddenByDefault**  

### ManufacturingPolicy

MTS=Make-To-Stock; MTO=Make-To-Order; ATO=Assemble-To-Order;ETO=Engineer-To-Order. `Required` `Default("MTS")` `Filter(eq)`

_Type_: **[ManufacturingPolicy](Logistics.Procurement.ProductSupply.md#manufacturingpolicy)**  
_Category_: **System**  
Allowed values for the `ManufacturingPolicy`(Logistics.Procurement.ProductSupply.md#manufacturingpolicy) data attribute  
_Allowed Values (Logistics.Procurement.ProductSupplyRepository.ManufacturingPolicy Enum Members)_  

| Value | Description |
| ---- | --- |
| AssembleToOrder | AssembleToOrder value. Stored as 'ATO'. <br /> _Database Value:_ 'ATO' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AssembleToOrder' |
| MakeToOrder | MakeToOrder value. Stored as 'MTO'. <br /> _Database Value:_ 'MTO' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'MakeToOrder' |
| MakeToStock | MakeToStock value. Stored as 'MTS'. <br /> _Database Value:_ 'MTS' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'MakeToStock' |
| EngineerToOrder | EngineerToOrder value. Stored as 'ETO'. <br /> _Database Value:_ 'ETO' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'EngineerToOrder' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **MakeToStock**  
_Show in UI_: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### OrderLotSizeQuantityBase

The quantity of the product, normally ordered from the plant or supplier. The quantity is expressed in the base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(1)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### OrderLotSizingMethod

LFL=Lot for Lot; FOQ=Fixed order quantity; EOQ=Eqonomic Order Quantity; ROP=ReOrder Point; ROT=ReOrder point with Time planning; LFP = Lot For Period;. `Required` `Default("ROP")` `Filter(eq)`

_Type_: **[OrderLotSizingMethod](Logistics.Procurement.ProductSupply.md#orderlotsizingmethod)**  
_Category_: **System**  
Allowed values for the `OrderLotSizingMethod`(Logistics.Procurement.ProductSupply.md#orderlotsizingmethod) data attribute  
_Allowed Values (Logistics.Procurement.ProductSupplyRepository.OrderLotSizingMethod Enum Members)_  

| Value | Description |
| ---- | --- |
| EconomicOrderQuantity | EconomicOrderQuantity value. Stored as 'EOQ'. <br /> _Database Value:_ 'EOQ' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'EconomicOrderQuantity' |
| FixedOrderQuantity | FixedOrderQuantity value. Stored as 'FOQ'. <br /> _Database Value:_ 'FOQ' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'FixedOrderQuantity' |
| LotForLot | LotForLot value. Stored as 'LFL'. <br /> _Database Value:_ 'LFL' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'LotForLot' |
| LotForPeriod | LotForPeriod value. Stored as 'LFP'. <br /> _Database Value:_ 'LFP' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'LotForPeriod' |
| ReorderPoint | ReorderPoint value. Stored as 'ROP'. <br /> _Database Value:_ 'ROP' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'ReorderPoint' |
| ReorderPointWith<br />TimePlanning | ReorderPointWith<br />TimePlanning value. Stored as 'ROT'. <br /> _Database Value:_ 'ROT' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'ReorderPointWith<br />TimePlanning' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **ReorderPoint**  
_Show in UI_: **HiddenByDefault**  

### OrderMaximum

Order maximum when buying or making. null means no maximum. `Unit: Product.BaseMeasurementCategory.BaseUnit`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### OrderMinimum

Minimum order quantity both for buying and making. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(eq;ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **HiddenByDefault**  

### OrderMultiple

True if the order qty should be multiple of lot size when buying or making. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### OrderPeriodPlanningDays

For how many days in the future should be planned - for fixed period replenishment system. null - not yet specified.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### OrderPeriodStartDate

Start date of the first period under fixed period replenishment system. null - not yet specified. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### OrderPointQuantityBase

Order point quantity under the OP replenishment system. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(eq;ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### OrderPolicy

Order policy/replenishment system. OPS=Order Point System; OPT=Order Point System with Time planning; PRS=Periodic Review System/Periods Of Supply; MRP = Material Requirements Planning. `Required` `Default("OPS")` `Filter(eq)`

_Type_: **[OrderPolicy](Logistics.Procurement.ProductSupply.md#orderpolicy)**  
_Category_: **System**  
Allowed values for the `OrderPolicy`(Logistics.Procurement.ProductSupply.md#orderpolicy) data attribute  
_Allowed Values (Logistics.Procurement.ProductSupplyRepository.OrderPolicy Enum Members)_  

| Value | Description |
| ---- | --- |
| MaterialRequirements<br />Planning | MaterialRequirements<br />Planning value. Stored as 'MRP'. <br /> _Database Value:_ 'MRP' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'MaterialRequirements<br />Planning' |
| OrderPointSystem | OrderPointSystem value. Stored as 'OPS'. <br /> _Database Value:_ 'OPS' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'OrderPointSystem' |
| OrderPointSystem<br />WithTimePlanning | OrderPointSystem<br />WithTimePlanning value. Stored as 'OPT'. <br /> _Database Value:_ 'OPT' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'OrderPointSystem<br />WithTimePlanning' |
| PeriodicReviewSystem | PeriodicReviewSystem value. Stored as 'PRS'. <br /> _Database Value:_ 'PRS' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'PeriodicReviewSystem' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **OrderPointSystem**  
_Show in UI_: **HiddenByDefault**  

### PlanningAnnualCarryingCostPercent

The expected carrying cost as percentage of inventory cost. null means unknown.

_Type_: **decimal (5, 4) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### PlanningAnnualUsageQuantityBase

Average usage of the product for 1 year. NUL means unknown. `Unit: Product.BaseMeasurementCategory.BaseUnit`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### PlanningHorizonDays

Number of days in the future for which to plan the demand and supply. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **CannotBeShown**  

### PlanningLeadTimeDays

The number of days required to supply or manufacture the product. The number is exclusive of the lead-time of lower-level components. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.PreferredSupplier.DefaultDeliveryTermDays`
### PlanningMaximumInventoryQuantityBase

Maximum inventory. null if N/A. `Unit: Product.BaseMeasurementCategory.BaseUnit`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### PlanningOrderCostBaseCurrency

Projected cost to place an order and set-up equipment. `Currency: EnterpriseCompany.BaseCurrency`

_Type_: **[Amount (18, 3)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### PlanningOrderCycleDays

Number of days in one period under fixed period replenishment system. null - not yet specified.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### PlanningSafetyStockQuantityBase

Planned lowest inventory level, protecting against unplanned demands. The quantity is expressed in the base measurement unit of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **HiddenByDefault**  

### PlanningTimeFenceDays

Period in the future inside of which changes to the MPS are carefully evaluated to prevent costly schedule disruption. Demand for the period between DTF and PTF is calculated as the bigger of customer orders and sales forecast. Abbr. - PTF. `Required` `Default(1)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **CannotBeShown**  

### ProcurementType

M=Make; B=Buy; T=Transfer.  Identifies whether the product is produced or externally bought. `Required` `Default("B")` `Filter(eq)`

_Type_: **[ProcurementType](Logistics.Procurement.ProductSupply.md#procurementtype)**  
_Category_: **System**  
Allowed values for the `ProcurementType`(Logistics.Procurement.ProductSupply.md#procurementtype) data attribute  
_Allowed Values (Logistics.Procurement.ProductSupplyRepository.ProcurementType Enum Members)_  

| Value | Description |
| ---- | --- |
| Buy | Buy value. Stored as 'B'. <br /> _Database Value:_ 'B' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Buy' |
| Make | Make value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Make' |
| Transfer | Transfer value. Stored as 'T'. <br /> _Database Value:_ 'T' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Transfer' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Buy**  
_Show in UI_: **HiddenByDefault**  

### StandardCostPerLot

Standard cost for one lot of the product. `Currency: Product.CostingCurrency` `Required` `Default(0)`

_Type_: **[Amount (18, 4)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **HiddenByDefault**  

### SupplySchemaId

The supply schema to use for the distribution of the product among warehouses. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  


## Reference Details

### DefaultStoreBin

Default store bin for new deliveries using this supply scheme. `Filter(multi eq)`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### EnterpriseCompany

The Enterprise Company to which this ProductSupply applies, or null if it is for all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### FromStore

Used when the Procurement_Type is Transfer. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### GenerateDocumentType

Specifies the type of the document which should be generated by the procurement planning system, when generating supply based on this rule. `Filter(multi eq)`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PreferredSupplier

Preferred supplier for the product. null if there is no preferred supplier. `Filter(multi eq)`

_Type_: **[Suppliers](Logistics.Procurement.Suppliers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The <see cref="General.Products.Product"/> to which this ProductSupply belongs. `Filter(multi eq)` `FilterableReference`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ProductGroup

Not null when the method is a default method for a whole product group. In this case new products in the group inherit the settings. `Filter(multi eq)`

_Type_: **[ProductGroups](General.Products.ProductGroups.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Store

The store for which this rule is defined. When null, the rule is valid for all stores. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


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

