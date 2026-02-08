---
uid: General.Products.Products
---
# General.Products.Products


Products are the different items in the enterprise, which can be purchased, stored, sold and depreciated.

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.Products  
Base Table: Gen_Products  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: PartNumber; Name  
Code Member: PartNumber  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  
Layout category By:  ProductTypeId  

## Track Changes  
Min level:  2 - Track object changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.Products.Products](General.Products.Products.md)  
  * [Crm.Marketing.ProductDistributionChannels](Crm.Marketing.ProductDistributionChannels.md)  
  * [General.Products.ProductCodes](General.Products.ProductCodes.md)  
  * [General.Products.ProductDimensions](General.Products.ProductDimensions.md)  
  * [General.Products.ProductDocumentAmounts](General.Products.ProductDocumentAmounts.md)  
  * [General.Products.ProductPictures](General.Products.ProductPictures.md)  
  * [General.Products.ProductRelations](General.Products.ProductRelations.md)  
  * [General.Products.ProductVariants](General.Products.ProductVariants.md)  
  * [General.Products.CompositeProductComponents](General.Products.CompositeProductComponents.md)  
  * [Logistics.Inventory.ProductDefaultStoreBins](Logistics.Inventory.ProductDefaultStoreBins.md)  
  * [Logistics.Inventory.SerialNumbers](Logistics.Inventory.SerialNumbers.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ABCClass](General.Products.Products.md#abcclass) | [ABCClass](General.Products.Products.md#abcclass) | Product importance classification, where A are the most important and C - the least important products. Usually used as user filtering condition when previewing results of the procurement planning process.`Required` `Default(&quot;B &quot;)` `Filter(eq)` 
| [Active](General.Products.Products.md#active) | boolean | 1 if the product is active, 0 - not to list in combo boxes for choosing in new documents`Required` `Default(true)` `Filter(eq)` 
| [AllowVariableMeasurement<br />Ratios](General.Products.Products.md#allowvariablemeasurementratios) | boolean | Allow variable (dynamic) measurement ratios for each transaction. If specified, each store transaction could specify non-standard measurement ratio between the used measurement unit and the base unit.`Required` `Default(false)` `Filter(eq)` 
| [CatalogDescriptionHtml](General.Products.Products.md#catalogdescriptionhtml) | string (max) __nullable__ | Full HTML description of the product. Usually used for display on product catalogs, web pages, etc. 
| [CostingMethod](General.Products.Products.md#costingmethod) | [CostingMethod](General.Products.Products.md#costingmethod) __nullable__ | Specifies the costing method for the product. NULL means to use the Enterprise Company default. Currently supported methods are: EXP - Explicitly specify lot; AVG - Average cost 
| [CreationTime](General.Products.Products.md#creationtime) | datetime __nullable__ | Date and time when the Product was created. `Filter(ge;le)` `ReadOnly` 
| [CreationUser](General.Products.Products.md#creationuser) | string (64) __nullable__ | Login name of the user, who created the Product. `Filter(like)` `ReadOnly` 
| [Description](General.Products.Products.md#description) | [MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__ | The description of the product 
| [ExpiryPeriodDays](General.Products.Products.md#expiryperioddays) | int32 __nullable__ | Total default expiry period for the product (in days) from the date of production to the date of expiry 
| [FlushingMethod](General.Products.Products.md#flushingmethod) | [FlushingMethod](General.Products.Products.md#flushingmethod) | Consumption method for work orders. M=Manual, using Consuption Journals, F=Forward (on release), B=Backward (on finish)`Required` `Default(&quot;M&quot;)` 
| [GuaranteePeriodDays](General.Products.Products.md#guaranteeperioddays) | int32 __nullable__ | standard guarantee period in days. Can be set only if the product type is serviced. 
| [IsFeatured](General.Products.Products.md#isfeatured) | boolean | Specifies whether the product should be presented at the title space in promotional materials, web pages, etc.`Required` `Default(false)` `Filter(eq)` 
| [IsSerialized](General.Products.Products.md#isserialized) | boolean | 1 if the parts use/require serial numbers`Required` `Default(false)` `Filter(eq)` 
| [LotsIssue](General.Products.Products.md#lotsissue) | [LotsIssue](General.Products.Products.md#lotsissue) __nullable__ | Determines the method by which the lots are automatically issued. The method determines the sequence of the lots: in the order of receipt (FIFO), in the order inverse of receipt (LIFO) or in the order of expiration (FEFO). 
| [ManufacturingPolicy](General.Products.Products.md#manufacturingpolicy) | string (3) | Manufacturing policy controls the procurement planing system actions for this product. Allowed values are MTS=Make-To-Stock; MTO=Make-To-Order; ATO=Assemble-To-<br />Order`Required` `Default(&quot;MTS&quot;)` 
| [MinimalSalesPricePerLot](General.Products.Products.md#minimalsalespriceperlot) | [Amount (18, 4)](../data-types.md#amount) __nullable__ | Minimal allowed price for sales of this product. The price is for one standard lot and in the costing currency of the product. The minimum is enforced upon planning and/or releasing a document. NULL means that there is no minimal sales price enforcement.`Currency: CostingCurrency` 
| [MinimalSalesQuantityBase](General.Products.Products.md#minimalsalesquantitybase) | decimal (18, 3) __nullable__ | Minimal base quantity of this product that has to be specified in any sale. 
| [Name](General.Products.Products.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the item`Required` `Filter(eq;like)` 
| [PartNumber](General.Products.Products.md#partnumber) | string (32) | Unique part number of the product`Required` `Filter(multi eq;like)` `ORD` 
| [PlanningDemand<br />TimeFenceDays](General.Products.Products.md#planningdemandtimefencedays) | int32 __nullable__ | Period in the future, in which changes to the MPS are not accepted due to the high cost of changing. Demand for the period is calculated based entirely on the customer orders. Abbr. - DTF (NULL = Default of 30 days) 
| [PlanningHorizonDays](General.Products.Products.md#planninghorizondays) | int32 __nullable__ | Number of days in the future for which to plan the demand and supply (NULL = Default of 180 days) 
| [PlanningTimeFenceDays](General.Products.Products.md#planningtimefencedays) | int32 __nullable__ | Period in the future inside of which changes to the MPS are carefully evaluated to prevent costly schedule disruption. Demand for the period between DTF and PTF is calculated as the bigger of customer orders and sales forecast. Abbr. - PTF. (NULL = Default of 90 days) 
| [ScrapRate](General.Products.Products.md#scraprate) | decimal (7, 6) | Default scrap rate for the recipe, when this product is used as ingredient`Required` `Default(0)` 
| [ShortName](General.Products.Products.md#shortname) | [MultilanguageString (128)](../data-types.md#multilanguagestring) __nullable__ | Short name of the product. Used for space-constrained devices, like mobile phones, fiscal printers, etc.`Filter(eq;like)` 
| [ShowInCatalog](General.Products.Products.md#showincatalog) | boolean | Specifies whether to show the product in catalogs, referring to the product group of the product. 0=Do not show; 1=Show.`Required` `Default(false)` `Filter(multi eq)` 
| [StandardCostPerLot](General.Products.Products.md#standardcostperlot) | [Amount (18, 4)](../data-types.md#amount) | Standard cost for one standard lot of the product in the currency, specified by Costing_Currency_<br />Id`Currency: ProductCurrency` `Required` `Default(0)` 
| [StandardLotSizeBase](General.Products.Products.md#standardlotsizebase) | [Quantity (18, 3)](../data-types.md#quantity) | The size of a standard lot, expressed in the base measurement unit of the product. Used for Standard_Cost and Standard_Price`Unit: BaseMeasurementCategory.BaseUnit` `Required` `Default(1)` 
| [StandardPricePerLot](General.Products.Products.md#standardpriceperlot) | [Amount (18, 4)](../data-types.md#amount) | Standard sales price (used if no special price is defined) for one standard lot of the product in the currency, specified by Costing_Currency_<br />Id`Currency: ProductCurrency` `Required` `Default(0)` 
| [SupplySchemaId](General.Products.Products.md#supplyschemaid) | guid __nullable__ | The supply schema to use for the distribution of the product among warehouses. `Filter(multi eq)` 
| [UpdateTime](General.Products.Products.md#updatetime) | datetime __nullable__ | Date and time when the Product was last updated. `Filter(ge;le)` `ReadOnly` 
| [UpdateUser](General.Products.Products.md#updateuser) | string (64) __nullable__ | Login name of the user, who last updated the Product. `Filter(like)` `ReadOnly` 
| [UseLots](General.Products.Products.md#uselots) | [UseLots](General.Products.Products.md#uselots) | Specifies whether the use of lots for this product in store documents is required or is unallowed or is allowed while not required.`Required` `Default(&quot;A&quot;)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseMeasurementCategory](General.Products.Products.md#basemeasurementcategory) | [MeasurementCategories](General.Products.MeasurementCategories.md) | The base measurement category for quantities of this product. |
| [CargoType](General.Products.Products.md#cargotype) | [CargoTypes](Logistics.Shipment.CargoTypes.md) (nullable) | Specifies what type of cargo this product is. Required when generating transportation requisitions. NULL means unspecified. |
| [CostingCurrency](General.Products.Products.md#costingcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Specifies the currency to use for cost calculations for the product. When NULL, the base currency for the enterprise company should be used |
| [EnterpriseCompany](General.Products.Products.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | Specifies if the product is specific to a given enterprise company and may be used only in documents from this enterprise company. |
| [ExciseProductType](General.Products.Products.md#exciseproducttype) | [ExciseProductTypes](Regulatory.Excise.ExciseProductTypes.md) (nullable) | Specifies the basic excise attributes of the product. |
| [IntrastatCommodityCode](General.Products.Products.md#intrastatcommoditycode) | [CommodityCodes](Regulatory.Intrastat.CommodityCodes.md) (nullable) | Code from The Combined Nomenclature used within the European Union countries. Used when reporting Intrastat and Excise. |
| [IntrastatSupplementaryUnit](General.Products.Products.md#intrastatsupplementaryunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | Additional measurement unit from the Intrastat Combined nomenclature. Used when creating Intrastat declarations. |
| [MeasurementUnit](General.Products.Products.md#measurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | Default measurement unit, when creating new documents with this product. |
| [OriginCountry](General.Products.Products.md#origincountry) | [Countries](General.Geography.Countries.md) (nullable) | Country from which the product originates (in which the product is produced/cultivated ...) |
| [ProductGroup](General.Products.Products.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) | The product group, under which the product is categorized. |
| [ProductType](General.Products.Products.md#producttype) | [ProductTypes](General.Products.ProductTypes.md) | The type of the product. This also defines whether the product is stocked. NULL=no specific product type and the product is stocked |
| [PurchaseMeasurementUnit](General.Products.Products.md#purchasemeasurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | Default measurement unit to use, when creating new purchase documents with this product. |
| [ValuationGroup](General.Products.Products.md#valuationgroup) | [ProductValuationGroups](Logistics.Inventory.ProductValuationGroups.md) (nullable) | Valuation group of the product. Used in reconciliations when compensating pluses and minuses. Equal plus and minus amounts within a valuation group are allowed to be compensated with each other for zero net fiscal effect. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.Products.md#id) | guid | Unique id of the item 
| [ObjectVersion](General.Products.Products.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](General.Products.Products.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Products.Products.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](General.Products.Products.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](General.Products.Products.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Codes | [ProductCodes](General.Products.ProductCodes.md) | List of `ProductCode`(General.Products.ProductCodes.md) child objects, based on the `General.Products.ProductCode.Product`(General.Products.ProductCodes.md#product) back reference 
| CompositeProductComponents | [CompositeProductComponents](General.Products.CompositeProductComponents.md) | List of `CompositeProduct<br />Component`(General.Products.CompositeProductComponents.md) child objects, based on the `General.Products.CompositeProductComponent.CompositeProduct`(General.Products.CompositeProductComponents.md#compositeproduct) back reference 
| DefaultStoreBins | [ProductDefaultStoreBins](Logistics.Inventory.ProductDefaultStoreBins.md) | List of `ProductDefaultStoreBin`(Logistics.Inventory.ProductDefaultStoreBins.md) child objects, based on the `Logistics.Inventory.ProductDefaultStoreBin.Product`(Logistics.Inventory.ProductDefaultStoreBins.md#product) back reference 
| Dimensions | [ProductDimensions](General.Products.ProductDimensions.md) | List of `ProductDimension`(General.Products.ProductDimensions.md) child objects, based on the `General.Products.ProductDimension.Product`(General.Products.ProductDimensions.md#product) back reference 
| DistributionChannels | [ProductDistributionChannels](Crm.Marketing.ProductDistributionChannels.md) | List of `ProductDistribution<br />Channel`(Crm.Marketing.ProductDistribution<br />Channels.md) child objects, based on the `Crm.Marketing.ProductDistributionChannel.Product`(Crm.Marketing.ProductDistribution<br />Channels.md#product) back reference 
| DocumentAmounts | [ProductDocumentAmounts](General.Products.ProductDocumentAmounts.md) | List of `ProductDocumentAmount`(General.Products.ProductDocumentAmounts.md) child objects, based on the `General.Products.ProductDocumentAmount.Product`(General.Products.ProductDocumentAmounts.md#product) back reference 
| LineDiscounts | [LineDiscounts](Crm.Pricing.LineDiscounts.md) | List of `LineDiscount`(Crm.Pricing.LineDiscounts.md) child objects, based on the `Crm.LineDiscount.Product`(Crm.Pricing.LineDiscounts.md#product) back reference 
| Lots | [Lots](Logistics.Inventory.Lots.md) | List of `Lot`(Logistics.Inventory.Lots.md) child objects, based on the `Logistics.Inventory.Lot.Product`(Logistics.Inventory.Lots.md#product) back reference 
| Pictures | [ProductPictures](General.Products.ProductPictures.md) | List of `ProductPicture`(General.Products.ProductPictures.md) child objects, based on the `General.Products.ProductPicture.Product`(General.Products.ProductPictures.md#product) back reference 
| Prices | [ProductPrices](Crm.Pricing.ProductPrices.md) | List of `ProductPrice`(Crm.Pricing.ProductPrices.md) child objects, based on the `Crm.ProductPrice.Product`(Crm.Pricing.ProductPrices.md#product) back reference 
| PurchaseProductPrices | [PurchaseProductPrices](Logistics.Procurement.PurchaseProductPrices.md) | List of `PurchaseProductPrice`(Logistics.Procurement.PurchaseProductPrices.md) child objects, based on the `Logistics.Procurement.PurchaseProductPrice.Product`(Logistics.Procurement.PurchaseProductPrices.md#product) back reference 
| Relations | [ProductRelations](General.Products.ProductRelations.md) | List of `ProductRelation`(General.Products.ProductRelations.md) child objects, based on the `General.Products.ProductRelation.FromProduct`(General.Products.ProductRelations.md#fromproduct) back reference 
| SerialNumbers | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) | List of `SerialNumber`(Logistics.Inventory.SerialNumbers.md) child objects, based on the `Logistics.Inventory.SerialNumber.Product`(Logistics.Inventory.SerialNumbers.md#product) back reference 
| Variants | [ProductVariants](General.Products.ProductVariants.md) | List of `ProductVariant`(General.Products.ProductVariants.md) child objects, based on the `General.Products.ProductVariant.Product`(General.Products.ProductVariants.md#product) back reference 


## Attribute Details

### ABCClass

Product importance classification, where A are the most important and C - the least important products. Usually used as user filtering condition when previewing results of the procurement planning process.`Required` `Default(&quot;B &quot;)` `Filter(eq)`

Type: **[ABCClass](General.Products.Products.md#abcclass)**  
Category: **System**  
Allowed values for the `ABCClass`(General.Products.Products.md#abcclass) data attribute  
Allowed Values (General.Products.ProductsRepository.ABCClass Enum Members)  

| Value | Description |
| ---- | --- |
| A | A value. Stored as 'A '. <br /> Database Value: 'A ' <br /> Model Value: 0 <br /> Domain API Value: 'A' |
| B | B value. Stored as 'B '. <br /> Database Value: 'B ' <br /> Model Value: 1 <br /> Domain API Value: 'B' |
| C | C value. Stored as 'C '. <br /> Database Value: 'C ' <br /> Model Value: 2 <br /> Domain API Value: 'C' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **B**  
Show in UI: **ShownByDefault**  

### Active

1 if the product is active, 0 - not to list in combo boxes for choosing in new documents`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### AllowVariableMeasurementRatios

Allow variable (dynamic) measurement ratios for each transaction. If specified, each store transaction could specify non-standard measurement ratio between the used measurement unit and the base unit.`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### CatalogDescriptionHtml

Full HTML description of the product. Usually used for display on product catalogs, web pages, etc.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **CannotBeShown**  

### CostingMethod

Specifies the costing method for the product. NULL means to use the Enterprise Company default. Currently supported methods are: EXP - Explicitly specify lot; AVG - Average cost

Type: **[CostingMethod](General.Products.Products.md#costingmethod) __nullable__**  
Category: **System**  
Allowed values for the `CostingMethod`(General.Products.Products.md#costingmethod) data attribute  
Allowed Values (General.Products.ProductsRepository.CostingMethod Enum Members)  

| Value | Description |
| ---- | --- |
| AverageCostFor<br />TheWholeProduct | AverageCostFor<br />TheWholeProduct value. Stored as 'AVG'. <br /> Database Value: 'AVG' <br /> Model Value: 0 <br /> Domain API Value: 'AverageCostFor<br />TheWholeProduct' |
| SeparateCostForEachLot | SeparateCostForEachLot value. Stored as 'EXP'. <br /> Database Value: 'EXP' <br /> Model Value: 1 <br /> Domain API Value: 'SeparateCostForEachLot' |
| AveragePartitioned<br />ByReservedForDocument | AveragePartitioned<br />ByReservedForDocument value. Stored as 'BLD'. <br /> Database Value: 'BLD' <br /> Model Value: 2 <br /> Domain API Value: 'AveragePartitioned<br />ByReservedForDocument' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### CreationTime

Date and time when the Product was created. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### CreationUser

Login name of the user, who created the Product. `Filter(like)` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### Description

The description of the product

Type: **[MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExpiryPeriodDays

Total default expiry period for the product (in days) from the date of production to the date of expiry

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FlushingMethod

Consumption method for work orders. M=Manual, using Consuption Journals, F=Forward (on release), B=Backward (on finish)`Required` `Default(&quot;M&quot;)`

Type: **[FlushingMethod](General.Products.Products.md#flushingmethod)**  
Category: **System**  
Allowed values for the `FlushingMethod`(General.Products.Products.md#flushingmethod) data attribute  
Allowed Values (General.Products.ProductsRepository.FlushingMethod Enum Members)  

| Value | Description |
| ---- | --- |
| Backward | Backward value. Stored as 'B'. <br /> Database Value: 'B' <br /> Model Value: 0 <br /> Domain API Value: 'Backward' |
| Forward | Forward value. Stored as 'F'. <br /> Database Value: 'F' <br /> Model Value: 1 <br /> Domain API Value: 'Forward' |
| Manual | Manual value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 2 <br /> Domain API Value: 'Manual' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Manual**  
Show in UI: **ShownByDefault**  

### GuaranteePeriodDays

standard guarantee period in days. Can be set only if the product type is serviced.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsFeatured

Specifies whether the product should be presented at the title space in promotional materials, web pages, etc.`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### IsSerialized

1 if the parts use/require serial numbers`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LotsIssue

Determines the method by which the lots are automatically issued. The method determines the sequence of the lots: in the order of receipt (FIFO), in the order inverse of receipt (LIFO) or in the order of expiration (FEFO).

Type: **[LotsIssue](General.Products.Products.md#lotsissue) __nullable__**  
Category: **System**  
Allowed values for the `LotsIssue`(General.Products.Products.md#lotsissue) data attribute  
Allowed Values (General.Products.ProductsRepository.LotsIssue Enum Members)  

| Value | Description |
| ---- | --- |
| FirstInFirstOut | FirstInFirstOut value. Stored as 'FIFO'. <br /> Database Value: 'FIFO' <br /> Model Value: 0 <br /> Domain API Value: 'FirstInFirstOut' |
| FirstExpireFirstOut | FirstExpireFirstOut value. Stored as 'FEFO'. <br /> Database Value: 'FEFO' <br /> Model Value: 1 <br /> Domain API Value: 'FirstExpireFirstOut' |
| LastInFirstOut | LastInFirstOut value. Stored as 'LIFO'. <br /> Database Value: 'LIFO' <br /> Model Value: 2 <br /> Domain API Value: 'LastInFirstOut' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ManufacturingPolicy

Manufacturing policy controls the procurement planing system actions for this product. Allowed values are MTS=Make-To-Stock; MTO=Make-To-Order; ATO=Assemble-To-Order`Required` `Default(&quot;MTS&quot;)`

Type: **string (3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **3**  
Default Value: **MTS**  
Show in UI: **CannotBeShown**  

### MinimalSalesPricePerLot

Minimal allowed price for sales of this product. The price is for one standard lot and in the costing currency of the product. The minimum is enforced upon planning and/or releasing a document. NULL means that there is no minimal sales price enforcement.`Currency: CostingCurrency`

Type: **[Amount (18, 4)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### MinimalSalesQuantityBase

Minimal base quantity of this product that has to be specified in any sale.

Type: **decimal (18, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Name

Name of the item`Required` `Filter(eq;like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PartNumber

Unique part number of the product`Required` `Filter(multi eq;like)` `ORD`

Type: **string (32)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### PlanningDemandTimeFenceDays

Period in the future, in which changes to the MPS are not accepted due to the high cost of changing. Demand for the period is calculated based entirely on the customer orders. Abbr. - DTF (NULL = Default of 30 days)

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PlanningHorizonDays

Number of days in the future for which to plan the demand and supply (NULL = Default of 180 days)

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

### PlanningTimeFenceDays

Period in the future inside of which changes to the MPS are carefully evaluated to prevent costly schedule disruption. Demand for the period between DTF and PTF is calculated as the bigger of customer orders and sales forecast. Abbr. - PTF. (NULL = Default of 90 days)

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

### ScrapRate

Default scrap rate for the recipe, when this product is used as ingredient`Required` `Default(0)`

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### ShortName

Short name of the product. Used for space-constrained devices, like mobile phones, fiscal printers, etc.`Filter(eq;like)`

Type: **[MultilanguageString (128)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ShowInCatalog

Specifies whether to show the product in catalogs, referring to the product group of the product. 0=Do not show; 1=Show.`Required` `Default(false)` `Filter(multi eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### StandardCostPerLot

Standard cost for one standard lot of the product in the currency, specified by Costing_Currency_Id`Currency: ProductCurrency` `Required` `Default(0)`

Type: **[Amount (18, 4)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### StandardLotSizeBase

The size of a standard lot, expressed in the base measurement unit of the product. Used for Standard_Cost and Standard_Price`Unit: BaseMeasurementCategory.BaseUnit` `Required` `Default(1)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### StandardPricePerLot

Standard sales price (used if no special price is defined) for one standard lot of the product in the currency, specified by Costing_Currency_Id`Currency: ProductCurrency` `Required` `Default(0)`

Type: **[Amount (18, 4)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### SupplySchemaId

The supply schema to use for the distribution of the product among warehouses. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### UpdateTime

Date and time when the Product was last updated. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### UpdateUser

Login name of the user, who last updated the Product. `Filter(like)` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### UseLots

Specifies whether the use of lots for this product in store documents is required or is unallowed or is allowed while not required.`Required` `Default(&quot;A&quot;)`

Type: **[UseLots](General.Products.Products.md#uselots)**  
Category: **System**  
Allowed values for the `UseLots`(General.Products.Products.md#uselots) data attribute  
Allowed Values (General.Products.ProductsRepository.UseLots Enum Members)  

| Value | Description |
| ---- | --- |
| Allowed | Allowed value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 0 <br /> Domain API Value: 'Allowed' |
| NotAllowed | NotAllowed value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 1 <br /> Domain API Value: 'NotAllowed' |
| Required | Required value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 2 <br /> Domain API Value: 'Required' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Allowed**  
Show in UI: **ShownByDefault**  

### Id

Unique id of the item

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

### BaseMeasurementCategory

The base measurement category for quantities of this product.

Type: **[MeasurementCategories](General.Products.MeasurementCategories.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.ProductGroup.DefaultMeasurementUnit.MeasurementCategory`
### CargoType

Specifies what type of cargo this product is. Required when generating transportation requisitions. NULL means unspecified.

Type: **[CargoTypes](Logistics.Shipment.CargoTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CostingCurrency

Specifies the currency to use for cost calculations for the product. When NULL, the base currency for the enterprise company should be used

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

Specifies if the product is specific to a given enterprise company and may be used only in documents from this enterprise company.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.ProductGroup.EnterpriseCompany`
### ExciseProductType

Specifies the basic excise attributes of the product.

Type: **[ExciseProductTypes](Regulatory.Excise.ExciseProductTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### IntrastatCommodityCode

Code from The Combined Nomenclature used within the European Union countries. Used when reporting Intrastat and Excise.

Type: **[CommodityCodes](Regulatory.Intrastat.CommodityCodes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### IntrastatSupplementaryUnit

Additional measurement unit from the Intrastat Combined nomenclature. Used when creating Intrastat declarations.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MeasurementUnit

Default measurement unit, when creating new documents with this product.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.ProductGroup.DefaultMeasurementUnit`
### OriginCountry

Country from which the product originates (in which the product is produced/cultivated ...)

Type: **[Countries](General.Geography.Countries.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductGroup

The product group, under which the product is categorized.

Type: **[ProductGroups](General.Products.ProductGroups.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductType

The type of the product. This also defines whether the product is stocked. NULL=no specific product type and the product is stocked

Type: **[ProductTypes](General.Products.ProductTypes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.ProductGroup.GetDefaultProductTypeForNewProduct( )`

Front-End Recalc Expressions:  
`obj.ProductGroup.GetDefaultProductTypeForNewProduct( )`
### PurchaseMeasurementUnit

Default measurement unit to use, when creating new purchase documents with this product.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ValuationGroup

Valuation group of the product. Used in reconciliations when compensating pluses and minuses. Equal plus and minus amounts within a valuation group are allowed to be compensated with each other for zero net fiscal effect.

Type: **[ProductValuationGroups](Logistics.Inventory.ProductValuationGroups.md) (nullable)**  
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

[!list limit=1000 erp.entity=General.Products.Products erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.Products erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_Products

Domain API Entity Type: 
General_Products_Product

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_Products?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_Products?$top=10>

