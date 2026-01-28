---
uid: Crm.Pricing.BonusPrograms
---
# Crm.Pricing.BonusPrograms


Bonus programs allow automatic adding of new line with bonus product or automatic application of discount in a sales document.

## General
Namespace: [Crm.Pricing](Crm.Pricing.md)  
Repository: Crm.Pricing.BonusPrograms  
Base Table: Crm_Bonus_Programs  
API access:  ReadWrite  

## Renames

Old name: Crm.Marketing.BonusPrograms  
New name: Crm.Pricing.BonusPrograms  
Version: 25.1.1.36  
Case: 37717  



## Visualization
Display Format: {Name:T}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pricing.BonusPrograms](Crm.Pricing.BonusPrograms.md)  
  * [Crm.Pricing.BonusProgramProducts](Crm.Pricing.BonusProgramProducts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Crm.Pricing.BonusPrograms.md#active) | boolean __nullable__ | General condition if the bonus is active. The other conditions are verified only for active bonus programs. `Default(true)` `Filter(eq)` 
| [BonusAction](Crm.Pricing.BonusPrograms.md#bonusaction) | [BonusAction](Crm.Pricing.BonusPrograms.md#bonusaction) | If the bonus is a product, then Bonus Product, Bonus Product Quantity and Bonus Product Quantity Unit fields should be filled in. If the bonus is a discount, the Bonus Line Discount Percent should be filled in. Product - add product to the order, Discount – replace the standard discount, Cascade discount - apply after the standard discount. `Required` `Default("D")` `Filter(multi eq)` 
| [BonusDocumentAmountPercent](Crm.Pricing.BonusPrograms.md#bonusdocumentamountpercent) | decimal (7, 6) __nullable__ | The percent of the document amount that is rewarded. Should be null if and only if the bonus document amount is null. 
| [BonusLineDiscountPercent](Crm.Pricing.BonusPrograms.md#bonuslinediscountpercent) | decimal (7, 6) | The percent discount to be applied to bonus lines. Used only for bonus programs with Action = D (Discount) and Action = C (Cascade discount). `Required` `Default(0)` 
| [BonusProductQuantity](Crm.Pricing.BonusPrograms.md#bonusproductquantity) | [Quantity (12, 3)](../data-types.md#quantity) __nullable__ | The quantity rewarded of the bonus product. Should be not null if and only when the bonus product is not null. `Unit: BonusProductQuantityUnit` 
| [BonusProductQuantity<br />MultiplierForEach<br />LotSize](Crm.Pricing.BonusPrograms.md#bonusproductquantitymultiplierforeachlotsize) | [Quantity (12, 3)](../data-types.md#quantity) __nullable__ | When not null, specifies that the bonus quantity should be multiplied for each of the specified lot size. Can be non-null only when condition product is specified. `Unit: ConditionProduct.BaseMeasurementCategory.BaseUnit` 
| [ConditionCustomerFilterXML](Crm.Pricing.BonusPrograms.md#conditioncustomerfilterxml) | dataaccessfilter __nullable__ | When not null, specifies that the bonus should be applied only to customers who meet the specified criteria. The criteria could include custom properties. `Unit: Crm.Sales.CustomersRepository.TableName` 
| [ConditionDistribution<br />ChannelFilterX<br />ML](Crm.Pricing.BonusPrograms.md#conditiondistributionchannelfilterxml) | dataaccessfilter __nullable__ | When not null, specifies that the bonus should be applied only when the distribution channel of the sales order has the specified characteristics. `Unit: Marketing.DistributionChannels<br />Repository.TableName` 
| [ConditionFromDate](Crm.Pricing.BonusPrograms.md#conditionfromdate) | datetime __nullable__ | Starting date of the bonus. null means that there is no starting date restriction. `Filter(eq;ge;le)` 
| [ConditionMaxAmount](Crm.Pricing.BonusPrograms.md#conditionmaxamount) | [Amount (12, 2)](../data-types.md#amount) __nullable__ | If not null specifies the maximal amount for which the bonus is valid. null means that there is no maximal amount condition for the bonus. `Currency: ConditionDocumentCurrency` `Filter(eq;ge;le)` 
| [ConditionMaxQuantity](Crm.Pricing.BonusPrograms.md#conditionmaxquantity) | [Quantity (12, 3)](../data-types.md#quantity) __nullable__ | When not null, specifies condition for the bonus - maximal quantity of the condition product. If the condition product is null, this cannot be specified. `Unit: ConditionProduct.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)` 
| [ConditionMinAmount](Crm.Pricing.BonusPrograms.md#conditionminamount) | [Amount (12, 2)](../data-types.md#amount) __nullable__ | If not null specifies the minimal amount for which the bonus is valid. null means that there is no minimal amount condition for the bonus. `Currency: ConditionDocumentCurrency` `Filter(eq;ge;le)` 
| [ConditionMinQuantity](Crm.Pricing.BonusPrograms.md#conditionminquantity) | [Quantity (12, 3)](../data-types.md#quantity) __nullable__ | When not null, specifies condition for the bonus - minimal quantity of the condition product. If the condition product is null, this cannot be specified. `Unit: ConditionProduct.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)` 
| [ConditionShipTo<br />CustomerFilter<br />XML](Crm.Pricing.BonusPrograms.md#conditionshiptocustomerfilterxml) | dataaccessfilter __nullable__ | When not null, specifies that the bonus should be applied only when shipping to customer with the specified characteristics. `Unit: Crm.Sales.CustomersRepository.TableName` 
| [ConditionToDate](Crm.Pricing.BonusPrograms.md#conditiontodate) | datetime __nullable__ | Ending date (inclusive) of the bonus. null means that there is no ending date restriction. `Filter(eq;ge;le)` 
| [Name](Crm.Pricing.BonusPrograms.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of the bonus program. `Required` `Filter(eq;like)` 
| [Priority](Crm.Pricing.BonusPrograms.md#priority) | [Priority](Crm.Pricing.BonusPrograms.md#priority) | Priority (1-5) of the bonus program comparative to the other bonus programs. 1 is the lowest priority. `Required` `Default(2)` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BonusDocumentAmountType](Crm.Pricing.BonusPrograms.md#bonusdocumentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable) | When not null specifies that a document amount should be added to the order when the bonus conditions are met. null means that the bonus reward is not a document amount. `Filter(multi eq)` |
| [BonusProduct](Crm.Pricing.BonusPrograms.md#bonusproduct) | [Products](General.Products.Products.md) (nullable) | The product that is rewarded if the bonus conditions are met. null means that the bonus reward is not product. `Filter(multi eq)` |
| [BonusProductQuantityUnit](Crm.Pricing.BonusPrograms.md#bonusproductquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The measurement unit of the quantity rewarded of the bonus product. Should be not null if and only when the bonus product is not null. `Filter(multi eq)` |
| [Campaign](Crm.Pricing.BonusPrograms.md#campaign) | [Campaigns](Crm.Marketing.Campaigns.md) (nullable) | Тhe marketing campaign to which the current definition belongs. `Filter(multi eq)` `Introduced in version 22.1.4.67` |
| [CompanyLocation](Crm.Pricing.BonusPrograms.md#companylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | When set, specifies that the sales document must be of the specified enterprise company location. `Filter(multi eq)` |
| [ConditionCustomer](Crm.Pricing.BonusPrograms.md#conditioncustomer) | [Customers](Crm.Sales.Customers.md) (nullable) | When not null, specifies that the bonus should be applied only to the specified customer. `Filter(multi eq)` |
| [ConditionDistribution<br />Channel](Crm.Pricing.BonusPrograms.md#conditiondistributionchannel) | [DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable) | When not null, specifies that the bonus should be applied only when the specified channel is used. `Filter(multi eq)` |
| [ConditionDocumentCurrency](Crm.Pricing.BonusPrograms.md#conditiondocumentcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Condition for the document amount. Should be not null if any of the amount conditions are not null. `Filter(multi eq)` |
| [ConditionPriceList](Crm.Pricing.BonusPrograms.md#conditionpricelist) | [PriceLists](Crm.Pricing.PriceLists.md) (nullable) | When not null, specifies that the bonus should be applied only when the sales order is based on the speicfied price list. `Filter(multi eq)` |
| [ConditionProduct](Crm.Pricing.BonusPrograms.md#conditionproduct) | [Products](General.Products.Products.md) (nullable) | When not null, specifies a conditional product, which is required to exist in the sales document in order for the bonus program to be applied. If a condition with multiple products is required, additional products can be added to Bonus Program Products. If null the other conditions should be evaluated against the whole order. `Filter(multi eq)` |
| [ConditionProductGroup](Crm.Pricing.BonusPrograms.md#conditionproductgroup) | [ProductGroups](General.Products.ProductGroups.md) (nullable) | When not null, specifies that the bonus should be applied only to products from the specified product group or its subgroups. `Filter(multi eq)` |
| [ConditionShipToCustomer](Crm.Pricing.BonusPrograms.md#conditionshiptocustomer) | [Customers](Crm.Sales.Customers.md) (nullable) | When not null, specifies that the bonus should be applied only when shipping to the specified customer. `Filter(multi eq)` |
| [ConditionTargetGroup](Crm.Pricing.BonusPrograms.md#conditiontargetgroup) | [TargetGroups](Crm.Marketing.TargetGroups.md) (nullable) | When not null, specifies that the bonus should be applied only to the specified target customer group. `Filter(multi eq)` |
| [DocumentAmountType](Crm.Pricing.BonusPrograms.md#documentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable) | The document amount type that is used as а category. When specified, triggers the recording of the applied discount amount that comes from the bonus program in the Document Distributed Amounts panel in sales orders. `Filter(multi eq)` `Introduced in version 25.1.1.66` |
| [EnterpriseCompany](Crm.Pricing.BonusPrograms.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When set, specifies that the sales document must be of the specified enterprise company. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pricing.BonusPrograms.md#id) | guid |  
| [ObjectVersion](Crm.Pricing.BonusPrograms.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Pricing.BonusPrograms.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pricing.BonusPrograms.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Pricing.BonusPrograms.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Pricing.BonusPrograms.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Products | [BonusProgramProducts](Crm.Pricing.BonusProgramProducts.md) | List of `BonusProgramProduct`(Crm.Pricing.BonusProgramProducts.md) child objects, based on the `Crm.Pricing.BonusProgramProduct.BonusProgram`(Crm.Pricing.BonusProgramProducts.md#bonusprogram) back reference 


## Attribute Details

### Active

General condition if the bonus is active. The other conditions are verified only for active bonus programs. `Default(true)` `Filter(eq)`

Type: **boolean __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### BonusAction

If the bonus is a product, then Bonus Product, Bonus Product Quantity and Bonus Product Quantity Unit fields should be filled in. If the bonus is a discount, the Bonus Line Discount Percent should be filled in. Product - add product to the order, Discount – replace the standard discount, Cascade discount - apply after the standard discount. `Required` `Default("D")` `Filter(multi eq)`

Type: **[BonusAction](Crm.Pricing.BonusPrograms.md#bonusaction)**  
Category: **System**  
Allowed values for the `BonusAction`(Crm.Pricing.BonusPrograms.md#bonusaction) data attribute  
Allowed Values (Crm.Pricing.BonusProgramsRepository.BonusAction Enum Members)  

| Value | Description |
| ---- | --- |
| Product | Product value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 0 <br /> Domain API Value: 'Product' |
| Discount | Discount value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 1 <br /> Domain API Value: 'Discount' |
| CascadeDiscount | CascadeDiscount value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 2 <br /> Domain API Value: 'CascadeDiscount' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Discount**  
Show in UI: **ShownByDefault**  

### BonusDocumentAmountPercent

The percent of the document amount that is rewarded. Should be null if and only if the bonus document amount is null.

Type: **decimal (7, 6) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

### BonusLineDiscountPercent

The percent discount to be applied to bonus lines. Used only for bonus programs with Action = D (Discount) and Action = C (Cascade discount). `Required` `Default(0)`

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### BonusProductQuantity

The quantity rewarded of the bonus product. Should be not null if and only when the bonus product is not null. `Unit: BonusProductQuantityUnit`

Type: **[Quantity (12, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BonusProductQuantityMultiplierForEachLotSize

When not null, specifies that the bonus quantity should be multiplied for each of the specified lot size. Can be non-null only when condition product is specified. `Unit: ConditionProduct.BaseMeasurementCategory.BaseUnit`

Type: **[Quantity (12, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConditionCustomerFilterXML

When not null, specifies that the bonus should be applied only to customers who meet the specified criteria. The criteria could include custom properties. `Unit: Crm.Sales.CustomersRepository.TableName`

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConditionDistributionChannelFilterXML

When not null, specifies that the bonus should be applied only when the distribution channel of the sales order has the specified characteristics. `Unit: Marketing.DistributionChannelsRepository.TableName`

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConditionFromDate

Starting date of the bonus. null means that there is no starting date restriction. `Filter(eq;ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConditionMaxAmount

If not null specifies the maximal amount for which the bonus is valid. null means that there is no maximal amount condition for the bonus. `Currency: ConditionDocumentCurrency` `Filter(eq;ge;le)`

Type: **[Amount (12, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConditionMaxQuantity

When not null, specifies condition for the bonus - maximal quantity of the condition product. If the condition product is null, this cannot be specified. `Unit: ConditionProduct.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)`

Type: **[Quantity (12, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConditionMinAmount

If not null specifies the minimal amount for which the bonus is valid. null means that there is no minimal amount condition for the bonus. `Currency: ConditionDocumentCurrency` `Filter(eq;ge;le)`

Type: **[Amount (12, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConditionMinQuantity

When not null, specifies condition for the bonus - minimal quantity of the condition product. If the condition product is null, this cannot be specified. `Unit: ConditionProduct.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)`

Type: **[Quantity (12, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConditionShipToCustomerFilterXML

When not null, specifies that the bonus should be applied only when shipping to customer with the specified characteristics. `Unit: Crm.Sales.CustomersRepository.TableName`

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConditionToDate

Ending date (inclusive) of the bonus. null means that there is no ending date restriction. `Filter(eq;ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Name

The name of the bonus program. `Required` `Filter(eq;like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Priority

Priority (1-5) of the bonus program comparative to the other bonus programs. 1 is the lowest priority. `Required` `Default(2)` `Filter(multi eq)`

Type: **[Priority](Crm.Pricing.BonusPrograms.md#priority)**  
Category: **System**  
Allowed values for the `Priority`(Crm.Pricing.BonusPrograms.md#priority) data attribute  
Allowed Values (Crm.Pricing.BonusProgramsRepository.Priority Enum Members)  

| Value | Description |
| ---- | --- |
| v_1Lowest | v_1Lowest value. Stored as 0. <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'v_1Lowest' |
| Two | Two value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'Two' |
| Three | Three value. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Three' |
| Four | Four value. Stored as 3. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'Four' |
| v_5Highest | v_5Highest value. Stored as 4. <br /> Database Value: 4 <br /> Model Value: 4 <br /> Domain API Value: 'v_5Highest' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **2**  
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

### BonusDocumentAmountType

When not null specifies that a document amount should be added to the order when the bonus conditions are met. null means that the bonus reward is not a document amount. `Filter(multi eq)`

Type: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### BonusProduct

The product that is rewarded if the bonus conditions are met. null means that the bonus reward is not product. `Filter(multi eq)`

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### BonusProductQuantityUnit

The measurement unit of the quantity rewarded of the bonus product. Should be not null if and only when the bonus product is not null. `Filter(multi eq)`

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Campaign

Тhe marketing campaign to which the current definition belongs. `Filter(multi eq)` `Introduced in version 22.1.4.67`

Type: **[Campaigns](Crm.Marketing.Campaigns.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CompanyLocation

When set, specifies that the sales document must be of the specified enterprise company location. `Filter(multi eq)`

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConditionCustomer

When not null, specifies that the bonus should be applied only to the specified customer. `Filter(multi eq)`

Type: **[Customers](Crm.Sales.Customers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConditionDistributionChannel

When not null, specifies that the bonus should be applied only when the specified channel is used. `Filter(multi eq)`

Type: **[DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConditionDocumentCurrency

Condition for the document amount. Should be not null if any of the amount conditions are not null. `Filter(multi eq)`

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConditionPriceList

When not null, specifies that the bonus should be applied only when the sales order is based on the speicfied price list. `Filter(multi eq)`

Type: **[PriceLists](Crm.Pricing.PriceLists.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConditionProduct

When not null, specifies a conditional product, which is required to exist in the sales document in order for the bonus program to be applied. If a condition with multiple products is required, additional products can be added to Bonus Program Products. If null the other conditions should be evaluated against the whole order. `Filter(multi eq)`

Type: **[Products](General.Products.Products.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConditionProductGroup

When not null, specifies that the bonus should be applied only to products from the specified product group or its subgroups. `Filter(multi eq)`

Type: **[ProductGroups](General.Products.ProductGroups.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConditionShipToCustomer

When not null, specifies that the bonus should be applied only when shipping to the specified customer. `Filter(multi eq)`

Type: **[Customers](Crm.Sales.Customers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConditionTargetGroup

When not null, specifies that the bonus should be applied only to the specified target customer group. `Filter(multi eq)`

Type: **[TargetGroups](Crm.Marketing.TargetGroups.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DocumentAmountType

The document amount type that is used as а category. When specified, triggers the recording of the applied discount amount that comes from the bonus program in the Document Distributed Amounts panel in sales orders. `Filter(multi eq)` `Introduced in version 25.1.1.66`

Type: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

When set, specifies that the sales document must be of the specified enterprise company. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Pricing.BonusPrograms erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pricing.BonusPrograms erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pricing_BonusPrograms

Domain API Entity Type: 
Crm_Pricing_BonusProgram

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pricing_BonusPrograms?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pricing_BonusPrograms?$top=10>

