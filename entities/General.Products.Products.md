---
uid: General.Products.Products
---
# General.Products.Products Entity

**Namespace:** [General.Products](General.Products.md)  

Products are the different items in the enterprise, which can be purchased, stored, sold and depreciated. Entity: Gen_Products

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_PartNumber; Name_  
Code Data Member:  
_PartNumber_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  
Layout category attribute:  _ProductTypeId_  

## Track Changes  
Min level:  _2 - Track object changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [ABCClass](General.Products.Products.md#abcclass) | [ABCClass](General.Products.Products.md#abcclass) | Product importance classification, where A are the most important and C - the least important products. Usually used as user filtering condition when previewing results of the procurement planning process. `Required` `Default("B ")` `Filter(eq)` 
| [Active](General.Products.Products.md#active) | boolean | True if the product is active, false - not to list in combo boxes for choosing in new documents. `Required` `Default(true)` `Filter(eq)` 
| [AggregateLastUpdateTimeUtc](General.Products.Products.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [AllowVariableMeasurement<br />Ratios](General.Products.Products.md#allowvariablemeasurementratios) | boolean | Allow variable (dynamic) measurement ratios for each transaction. If specified, each store transaction could specify different measurement ratio between the used measurement unit and the base measurement unit. `Required` `Default(false)` `Filter(eq)` 
| [CatalogDescriptionHtml](General.Products.Products.md#catalogdescriptionhtml) | string (max) __nullable__ | Full HTML description of the product. Usually used for display on product catalogs, web pages, etc. 
| [CostingMethod](General.Products.Products.md#costingmethod) | [CostingMethod](General.Products.Products.md#costingmethod) __nullable__ | Specifies the costing method for the product. null means to use the Enterprise Company default. Currently supported methods are: EXP - Explicitly specify lot; AVG - Average cost. 
| [CreationTime](General.Products.Products.md#creationtime) | datetime __nullable__ | Date and time when the Product was created. `Filter(ge;le)` `ReadOnly` 
| [CreationUser](General.Products.Products.md#creationuser) | string (64) __nullable__ | Login name of the user, who created the Product. `Filter(like)` `ReadOnly` 
| [Description](General.Products.Products.md#description) | [MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__ | The description of the product. 
| [DisplayText](General.Products.Products.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExpiryPeriodDays](General.Products.Products.md#expiryperioddays) | int32 __nullable__ | Total default expiry period for the product (in days) from the date of production to the date of expiry. 
| [ExternalId](General.Products.Products.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Products.Products.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FlushingMethod](General.Products.Products.md#flushingmethod) | [FlushingMethod](General.Products.Products.md#flushingmethod) | Consumption method for work orders. M=Manual, using Consuption Journals, F=Forward (on release), B=Backward (on finish). `Required` `Default("M")` 
| [GuaranteePeriodDays](General.Products.Products.md#guaranteeperioddays) | int32 __nullable__ | Default guarantee period length in days. 0 means no guarantee. Should be non-null for serviced products and null for the others. 
| [Id](General.Products.Products.md#id) | guid |  
| [IsFeatured](General.Products.Products.md#isfeatured) | boolean | Specifies whether the product should be presented at the title space in promotional materials, web pages, etc. `Required` `Default(false)` `Filter(eq)` 
| [IsSerialized](General.Products.Products.md#isserialized) | boolean | True if the parts use/require serial numbers. `Required` `Default(false)` `Filter(eq)` 
| [LotsIssue](General.Products.Products.md#lotsissue) | [LotsIssue](General.Products.Products.md#lotsissue) __nullable__ | Determines the method by which the lots are automatically issued. The method determines the sequence of the lots: in the order of receipt (FIFO), in the order inverse of receipt (LIFO) or in the order of expiration (FEFO). 
| [ManufacturingPolicy](General.Products.Products.md#manufacturingpolicy) | string (3) | Manufacturing policy controls the procurement planing system actions for this product. Allowed values are MTS=Make-To-Stock; MTO=Make-To-Order; ATO=Assemble-To-Order. `Required` `Default("MTS")` 
| [MinimalSalesPricePerLot](General.Products.Products.md#minimalsalespriceperlot) | [Amount (18, 4)](../data-types.md#amount) __nullable__ | Minimal allowed price for sales of this product. The price is for one standard lot and in the costing currency of the product. The minimum is enforced upon planning and/or releasing a document. null means that there is no minimal sales price enforcement. `Currency: CostingCurrency` 
| [MinimalSalesQuantityBase](General.Products.Products.md#minimalsalesquantitybase) | decimal (18, 3) __nullable__ | Minimal base quantity of this product that has to be specified in any sale. 
| [Name](General.Products.Products.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the item. `Required` `Filter(eq;like)` 
| [ObjectVersion](General.Products.Products.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PartNumber](General.Products.Products.md#partnumber) | string (32) | Unique part number of the product. `Required` `Filter(multi eq;like)` `ORD` 
| [PlanningDemand<br />TimeFenceDays](General.Products.Products.md#planningdemandtimefencedays) | int32 __nullable__ | Period in the future, in which changes to the MPS are not accepted due to the high cost of changing. Demand for the period is calculated based entirely on the customer orders. Abbr. - DTF (null = Default of 30 days). 
| [PlanningHorizonDays](General.Products.Products.md#planninghorizondays) | int32 __nullable__ | Number of days in the future for which to plan the demand and supply (null = Default of 180 days). 
| [PlanningTimeFenceDays](General.Products.Products.md#planningtimefencedays) | int32 __nullable__ | Period in the future inside of which changes to the MPS are carefully evaluated to prevent costly schedule disruption. Demand for the period between DTF and PTF is calculated as the bigger of customer orders and sales forecast. Abbr. - PTF. (null = Default of 90 days). 
| [ScrapRate](General.Products.Products.md#scraprate) | decimal (7, 6) | Default scrap rate for the recipe, when this product is used as ingredient. `Required` `Default(0)` 
| [ShortName](General.Products.Products.md#shortname) | [MultilanguageString (128)](../data-types.md#multilanguagestring) __nullable__ | Short name of the product. Used for space-constrained devices, like mobile phones, fiscal printers, etc. `Filter(eq;like)` 
| [ShowInCatalog](General.Products.Products.md#showincatalog) | boolean | Specifies whether to show the product in catalogs, referring to the product group of the product. false=Do not show; true=Show. `Required` `Default(false)` `Filter(multi eq)` 
| [StandardCostPerLot](General.Products.Products.md#standardcostperlot) | [Amount (18, 4)](../data-types.md#amount) | Standard cost for one standard lot of the product in the currency, specified by Costing_Currency_Id. `Currency: ProductCurrency` `Required` `Default(0)` 
| [StandardLotSizeBase](General.Products.Products.md#standardlotsizebase) | [Quantity (18, 3)](../data-types.md#quantity) | The size of a standard lot, expressed in the base measurement unit of the product. Used for Standard_Cost and Standard_Price. `Unit: BaseMeasurementCategory.BaseUnit` `Required` `Default(1)` 
| [StandardPricePerLot](General.Products.Products.md#standardpriceperlot) | [Amount (18, 4)](../data-types.md#amount) | Standard sales price (used if no special price is defined) for one standard lot of the product in the currency, specified by Costing_Currency_Id. `Currency: ProductCurrency` `Required` `Default(0)` 
| [SupplySchemaId](General.Products.Products.md#supplyschemaid) | guid __nullable__ | The supply schema to use for the distribution of the product among warehouses. `Filter(multi eq)` 
| [UpdateTime](General.Products.Products.md#updatetime) | datetime __nullable__ | Date and time when the Product was last updated. `Filter(ge;le)` `ReadOnly` 
| [UpdateUser](General.Products.Products.md#updateuser) | string (64) __nullable__ | Login name of the user, who last updated the Product. `Filter(like)` `ReadOnly` 
| [UseLots](General.Products.Products.md#uselots) | [UseLots](General.Products.Products.md#uselots) | Specifies whether the use of lots for this product in store documents is required or is unallowed or is allowed while not required. `Required` `Default("A")` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseMeasurementCategory](General.Products.Products.md#basemeasurementcategory) | [MeasurementCategories](General.Products.MeasurementCategories.md) | The base measurement category for quantities of this product. `Required` `Filter(multi eq)` |
| [CargoType](General.Products.Products.md#cargotype) | [CargoTypes](Logistics.Shipment.CargoTypes.md) (nullable) | Specifies what type of cargo this product is. Required when generating transportation requisitions. null means unspecified. `Filter(multi eq)` |
| [CostingCurrency](General.Products.Products.md#costingcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Specifies the currency to use for cost calculations for the product. When null, the base currency for the enterprise company should be used. `Filter(multi eq)` |
| [EnterpriseCompany](General.Products.Products.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When not null, specifies that the product is specific to a given enterprise company and may be used only in documents from this enterprise company. `Filter(multi eq)` |
| [ExciseProductType](General.Products.Products.md#exciseproducttype) | [ExciseProductTypes](Finance.Excise.ExciseProductTypes.md) (nullable) | Specifies the basic excise attributes of the product. `Filter(multi eq)` `Introduced in version 22.1.6.45` |
| [IntrastatCommodityCode](General.Products.Products.md#intrastatcommoditycode) | [CommodityCodes](Regulatory.Intrastat.CommodityCodes.md) (nullable) | Code from The Combined Nomenclature used within the European Union countries. Used when reporting Intrastat and Excise. `Filter(multi eq)` |
| [IntrastatSupplementaryUnit](General.Products.Products.md#intrastatsupplementaryunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | Additional measurement unit from the Intrastat Combined nomenclature. Used when creating Intrastat declarations. `Filter(multi eq)` |
| [MeasurementUnit](General.Products.Products.md#measurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | Default measurement unit, when creating new documents with this product. `Required` `Filter(multi eq)` |
| [OriginCountry](General.Products.Products.md#origincountry) | [Countries](General.Geography.Countries.md) (nullable) | Country from which the product originates (in which the product is produced/cultivated ...). Primarily used for Intrastat reporting. `Filter(multi eq)` |
| [ProductGroup](General.Products.Products.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) | The product group, under which the product is categorized. `Required` `Filter(multi eq)` |
| [ProductType](General.Products.Products.md#producttype) | [ProductTypes](General.Products.ProductTypes.md) | The type of the product. This also defines whether the product is stocked. null=no specific product type and the product is stocked. `Required` `Filter(multi eq)` |
| [PurchaseMeasurementUnit](General.Products.Products.md#purchasemeasurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | Default measurement unit to use, when creating new purchase documents with this product. `Filter(multi eq)` |
| [ValuationGroup](General.Products.Products.md#valuationgroup) | [ProductValuationGroups](Logistics.Inventory.ProductValuationGroups.md) (nullable) | Valuation group of the product. Used in reconciliations when compensating pluses and minuses. Equal plus and minus amounts within a valuation group are allowed to be compensated with each other for zero net fiscal effect. `Filter(multi eq)` |

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

Product importance classification, where A are the most important and C - the least important products. Usually used as user filtering condition when previewing results of the procurement planning process. `Required` `Default("B ")` `Filter(eq)`

_Type_: **[ABCClass](General.Products.Products.md#abcclass)**  
_Category_: **System**  
Allowed values for the `ABCClass`(General.Products.Products.md#abcclass) data attribute  
_Allowed Values (General.Products.ProductsRepository.ABCClass Enum Members)_  

| Value | Description |
| ---- | --- |
| A | A value. Stored as 'A '. <br /> _Database Value:_ 'A ' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'A' |
| B | B value. Stored as 'B '. <br /> _Database Value:_ 'B ' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'B' |
| C | C value. Stored as 'C '. <br /> _Database Value:_ 'C ' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'C' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **B**  
_Show in UI_: **ShownByDefault**  

### Active

True if the product is active, false - not to list in combo boxes for choosing in new documents. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### AllowVariableMeasurementRatios

Allow variable (dynamic) measurement ratios for each transaction. If specified, each store transaction could specify different measurement ratio between the used measurement unit and the base measurement unit. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### CatalogDescriptionHtml

Full HTML description of the product. Usually used for display on product catalogs, web pages, etc.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **CannotBeShown**  

### CostingMethod

Specifies the costing method for the product. null means to use the Enterprise Company default. Currently supported methods are: EXP - Explicitly specify lot; AVG - Average cost.

_Type_: **[CostingMethod](General.Products.Products.md#costingmethod) __nullable__**  
_Category_: **System**  
Allowed values for the `CostingMethod`(General.Products.Products.md#costingmethod) data attribute  
_Allowed Values (General.Products.ProductsRepository.CostingMethod Enum Members)_  

| Value | Description |
| ---- | --- |
| AverageCostFor<br />TheWholeProduct | AverageCostFor<br />TheWholeProduct value. Stored as 'AVG'. <br /> _Database Value:_ 'AVG' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AverageCostFor<br />TheWholeProduct' |
| SeparateCostForEachLot | SeparateCostForEachLot value. Stored as 'EXP'. <br /> _Database Value:_ 'EXP' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'SeparateCostForEachLot' |
| AveragePartitioned<br />ByReservedForDocument | AveragePartitioned<br />ByReservedForDocument value. Stored as 'BLD'. <br /> _Database Value:_ 'BLD' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'AveragePartitioned<br />ByReservedForDocument' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### CreationTime

Date and time when the Product was created. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### CreationUser

Login name of the user, who created the Product. `Filter(like)` `ReadOnly`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **HiddenByDefault**  

### Description

The description of the product.

_Type_: **[MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExpiryPeriodDays

Total default expiry period for the product (in days) from the date of production to the date of expiry.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

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

### FlushingMethod

Consumption method for work orders. M=Manual, using Consuption Journals, F=Forward (on release), B=Backward (on finish). `Required` `Default("M")`

_Type_: **[FlushingMethod](General.Products.Products.md#flushingmethod)**  
_Category_: **System**  
Allowed values for the `FlushingMethod`(General.Products.Products.md#flushingmethod) data attribute  
_Allowed Values (General.Products.ProductsRepository.FlushingMethod Enum Members)_  

| Value | Description |
| ---- | --- |
| Backward | Backward value. Stored as 'B'. <br /> _Database Value:_ 'B' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Backward' |
| Forward | Forward value. Stored as 'F'. <br /> _Database Value:_ 'F' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Forward' |
| Manual | Manual value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Manual' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Manual**  
_Show in UI_: **ShownByDefault**  

### GuaranteePeriodDays

Default guarantee period length in days. 0 means no guarantee. Should be non-null for serviced products and null for the others.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsFeatured

Specifies whether the product should be presented at the title space in promotional materials, web pages, etc. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### IsSerialized

True if the parts use/require serial numbers. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### LotsIssue

Determines the method by which the lots are automatically issued. The method determines the sequence of the lots: in the order of receipt (FIFO), in the order inverse of receipt (LIFO) or in the order of expiration (FEFO).

_Type_: **[LotsIssue](General.Products.Products.md#lotsissue) __nullable__**  
_Category_: **System**  
Allowed values for the `LotsIssue`(General.Products.Products.md#lotsissue) data attribute  
_Allowed Values (General.Products.ProductsRepository.LotsIssue Enum Members)_  

| Value | Description |
| ---- | --- |
| FirstInFirstOut | FirstInFirstOut value. Stored as 'FIFO'. <br /> _Database Value:_ 'FIFO' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'FirstInFirstOut' |
| FirstExpireFirstOut | FirstExpireFirstOut value. Stored as 'FEFO'. <br /> _Database Value:_ 'FEFO' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'FirstExpireFirstOut' |
| LastInFirstOut | LastInFirstOut value. Stored as 'LIFO'. <br /> _Database Value:_ 'LIFO' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'LastInFirstOut' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ManufacturingPolicy

Manufacturing policy controls the procurement planing system actions for this product. Allowed values are MTS=Make-To-Stock; MTO=Make-To-Order; ATO=Assemble-To-Order. `Required` `Default("MTS")`

_Type_: **string (3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **3**  
_Default Value_: **MTS**  
_Show in UI_: **CannotBeShown**  

### MinimalSalesPricePerLot

Minimal allowed price for sales of this product. The price is for one standard lot and in the costing currency of the product. The minimum is enforced upon planning and/or releasing a document. null means that there is no minimal sales price enforcement. `Currency: CostingCurrency`

_Type_: **[Amount (18, 4)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### MinimalSalesQuantityBase

Minimal base quantity of this product that has to be specified in any sale.

_Type_: **decimal (18, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Name

Name of the item. `Required` `Filter(eq;like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PartNumber

Unique part number of the product. `Required` `Filter(multi eq;like)` `ORD`

_Type_: **string (32)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### PlanningDemandTimeFenceDays

Period in the future, in which changes to the MPS are not accepted due to the high cost of changing. Demand for the period is calculated based entirely on the customer orders. Abbr. - DTF (null = Default of 30 days).

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### PlanningHorizonDays

Number of days in the future for which to plan the demand and supply (null = Default of 180 days).

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **CannotBeShown**  

### PlanningTimeFenceDays

Period in the future inside of which changes to the MPS are carefully evaluated to prevent costly schedule disruption. Demand for the period between DTF and PTF is calculated as the bigger of customer orders and sales forecast. Abbr. - PTF. (null = Default of 90 days).

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **CannotBeShown**  

### ScrapRate

Default scrap rate for the recipe, when this product is used as ingredient. `Required` `Default(0)`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### ShortName

Short name of the product. Used for space-constrained devices, like mobile phones, fiscal printers, etc. `Filter(eq;like)`

_Type_: **[MultilanguageString (128)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ShowInCatalog

Specifies whether to show the product in catalogs, referring to the product group of the product. false=Do not show; true=Show. `Required` `Default(false)` `Filter(multi eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### StandardCostPerLot

Standard cost for one standard lot of the product in the currency, specified by Costing_Currency_Id. `Currency: ProductCurrency` `Required` `Default(0)`

_Type_: **[Amount (18, 4)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### StandardLotSizeBase

The size of a standard lot, expressed in the base measurement unit of the product. Used for Standard_Cost and Standard_Price. `Unit: BaseMeasurementCategory.BaseUnit` `Required` `Default(1)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### StandardPricePerLot

Standard sales price (used if no special price is defined) for one standard lot of the product in the currency, specified by Costing_Currency_Id. `Currency: ProductCurrency` `Required` `Default(0)`

_Type_: **[Amount (18, 4)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### SupplySchemaId

The supply schema to use for the distribution of the product among warehouses. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  

### UpdateTime

Date and time when the Product was last updated. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### UpdateUser

Login name of the user, who last updated the Product. `Filter(like)` `ReadOnly`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **HiddenByDefault**  

### UseLots

Specifies whether the use of lots for this product in store documents is required or is unallowed or is allowed while not required. `Required` `Default("A")`

_Type_: **[UseLots](General.Products.Products.md#uselots)**  
_Category_: **System**  
Allowed values for the `UseLots`(General.Products.Products.md#uselots) data attribute  
_Allowed Values (General.Products.ProductsRepository.UseLots Enum Members)_  

| Value | Description |
| ---- | --- |
| Allowed | Allowed value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Allowed' |
| NotAllowed | NotAllowed value. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'NotAllowed' |
| Required | Required value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Required' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Allowed**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### BaseMeasurementCategory

The base measurement category for quantities of this product. `Required` `Filter(multi eq)`

_Type_: **[MeasurementCategories](General.Products.MeasurementCategories.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.ProductGroup.DefaultMeasurementUnit.MeasurementCategory`
### CargoType

Specifies what type of cargo this product is. Required when generating transportation requisitions. null means unspecified. `Filter(multi eq)`

_Type_: **[CargoTypes](Logistics.Shipment.CargoTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### CostingCurrency

Specifies the currency to use for cost calculations for the product. When null, the base currency for the enterprise company should be used. `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

When not null, specifies that the product is specific to a given enterprise company and may be used only in documents from this enterprise company. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.ProductGroup.EnterpriseCompany`
### ExciseProductType

Specifies the basic excise attributes of the product. `Filter(multi eq)` `Introduced in version 22.1.6.45`

_Type_: **[ExciseProductTypes](Finance.Excise.ExciseProductTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### IntrastatCommodityCode

Code from The Combined Nomenclature used within the European Union countries. Used when reporting Intrastat and Excise. `Filter(multi eq)`

_Type_: **[CommodityCodes](Regulatory.Intrastat.CommodityCodes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### IntrastatSupplementaryUnit

Additional measurement unit from the Intrastat Combined nomenclature. Used when creating Intrastat declarations. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### MeasurementUnit

Default measurement unit, when creating new documents with this product. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.ProductGroup.DefaultMeasurementUnit`
### OriginCountry

Country from which the product originates (in which the product is produced/cultivated ...). Primarily used for Intrastat reporting. `Filter(multi eq)`

_Type_: **[Countries](General.Geography.Countries.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductGroup

The product group, under which the product is categorized. `Required` `Filter(multi eq)`

_Type_: **[ProductGroups](General.Products.ProductGroups.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductType

The type of the product. This also defines whether the product is stocked. null=no specific product type and the product is stocked. `Required` `Filter(multi eq)`

_Type_: **[ProductTypes](General.Products.ProductTypes.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.ProductGroup.GetDefaultProductTypeForNewProduct( )`

_Front-End Recalc Expressions:_  
`obj.ProductGroup.GetDefaultProductTypeForNewProduct( )`
### PurchaseMeasurementUnit

Default measurement unit to use, when creating new purchase documents with this product. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ValuationGroup

Valuation group of the product. Used in reconciliations when compensating pluses and minuses. Equal plus and minus amounts within a valuation group are allowed to be compensated with each other for zero net fiscal effect. `Filter(multi eq)`

_Type_: **[ProductValuationGroups](Logistics.Inventory.ProductValuationGroups.md) (nullable)**  
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

