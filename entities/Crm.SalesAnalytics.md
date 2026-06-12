---
uid: Crm.SalesAnalytics
---
# Crm.SalesAnalytics View

**Namespace:** [Crm](Crm.md)  

Grouped sales data. Entity: Crm_Sales_Analytics (Introduced in version 26.2.0.62)

## Default Visualization
Default Display Text Format:  
_{SalesAnalyticId}: {DocumentDate}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadOnly_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.SalesAnalytics](Crm.SalesAnalytics.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentDate](Crm.SalesAnalytics.md#documentdate) | date | Date to group for. `Required` `Filter(ge;le)` `ORD` 
| [LineAmount](Crm.SalesAnalytics.md#lineamount) | decimal (38, 2) | Line Amount for date. `Required` 
| [LineDiscountAmount](Crm.SalesAnalytics.md#linediscountamount) | decimal (38, 2) | Discount over Line Amount for Date. `Required` 
| [QuantityBase](Crm.SalesAnalytics.md#quantitybase) | decimal (38, 3) | Base Quantity for Date. `Required` 
| [SalesAnalyticId](Crm.SalesAnalytics.md#salesanalyticid) | guid | Row Id. `Required` `Filter(multi eq)` 
| [StandardQuantityBase](Crm.SalesAnalytics.md#standardquantitybase) | decimal (38, 3) | Standard Base Quantity for Date. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BonusProgram](Crm.SalesAnalytics.md#bonusprogram) | [BonusPrograms](Crm.Pricing.BonusPrograms.md) | Bonus Program. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Bonus_Programs_Table.Bonus_Program_Id` |
| [Customer](Crm.SalesAnalytics.md#customer) | [Customers](Crm.Sales.Customers.md) | Unique customer Id. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Customers_Table.Customer_Id` |
| [Dealer](Crm.SalesAnalytics.md#dealer) | [Dealers](Crm.Sales.Dealers.md) | Dealer. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Dealers_Table.Dealer_Id` |
| [DistributionChannel](Crm.SalesAnalytics.md#distributionchannel) | [DistributionChannels](Crm.Marketing.DistributionChannels.md) | Distribution Channel. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Distribution_<br />Channels_Table.Distribution_Channel_Id` |
| [DocumentCurrency](Crm.SalesAnalytics.md#documentcurrency) | [Currencies](General.Currencies.Currencies.md) | Currency. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Currencies_Table.Currency_Id` |
| [EndCustomerParty](Crm.SalesAnalytics.md#endcustomerparty) | [Parties](General.Contacts.Parties.md) | Unique party id. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Parties_Table.Id` |
| [EnterpriseCompany](Crm.SalesAnalytics.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The Enterprise Company to which this SalesAnalyticsEntry applies. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_<br />Companies_Table.Enterprise_Company_Id` |
| [EnterpriseCompanyLocation](Crm.SalesAnalytics.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) | The Enterprise Company Location to which this SalesAnalyticsEntry applies. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cm_Company_Locations_Table.Company_Location_Id` |
| [Level1Discount](Crm.SalesAnalytics.md#level1discount) | [LineDiscounts](Crm.Pricing.LineDiscounts.md) | Level 1 Discount. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Line_Discounts_Table.Line_Discount_Id` |
| [Level2Discount](Crm.SalesAnalytics.md#level2discount) | [LineDiscounts](Crm.Pricing.LineDiscounts.md) | Level 2 Discount. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Line_Discounts_Table.Line_Discount_Id` |
| [Level3Discount](Crm.SalesAnalytics.md#level3discount) | [LineDiscounts](Crm.Pricing.LineDiscounts.md) | Level 3 Discount. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Line_Discounts_Table.Line_Discount_Id` |
| [Product](Crm.SalesAnalytics.md#product) | [Products](General.Products.Products.md) | Unique id of the item. `Required` `Default(New Guid)` `Filter(multi eq)` `ORD` `Inherited from Gen_Products_Table.Id` |
| [ProductPrice](Crm.SalesAnalytics.md#productprice) | [ProductPrices](Crm.Pricing.ProductPrices.md) | Product Price. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Product_Prices_Table.Product_Price_Id` |
| [ProductVariant](Crm.SalesAnalytics.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) | Product Variant. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Product_Variants_Table.Product_Variant_Id` |
| [PromotionalPackage](Crm.SalesAnalytics.md#promotionalpackage) | [PromotionalPackages](Crm.Pricing.PromotionalPackages.md) | Promotional Package. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Promotional_<br />Packages_Table.Promotional_Package_Id` |
| [SalesPerson](Crm.SalesAnalytics.md#salesperson) | [SalesPersons](Crm.SalesForce.SalesPersons.md) | Unique sales person Id. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Sales_Persons_Table.Sales_Person_Id` |
| [Store](Crm.SalesAnalytics.md#store) | [Stores](Logistics.Inventory.Stores.md) | Unique store Id. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Inv_Stores_Table.Id` |


## Attribute Details

### DocumentDate

Date to group for. `Required` `Filter(ge;le)` `ORD`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### LineAmount

Line Amount for date. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LineDiscountAmount

Discount over Line Amount for Date. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

Base Quantity for Date. `Required`

_Type_: **decimal (38, 3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### SalesAnalyticId

Row Id. `Required` `Filter(multi eq)`

_Type_: **guid**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### StandardQuantityBase

Standard Base Quantity for Date. `Required`

_Type_: **decimal (38, 3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### BonusProgram

Bonus Program. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Bonus_Programs_Table.Bonus_Program_Id`

_Type_: **[BonusPrograms](Crm.Pricing.BonusPrograms.md)**  
_Category_: **System**  
_Inherited From_: **Crm_Bonus_Programs_Table.Bonus_Program_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Customer

Unique customer Id. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Customers_Table.Customer_Id`

_Type_: **[Customers](Crm.Sales.Customers.md)**  
_Category_: **System**  
_Inherited From_: **Crm_Customers_Table.Customer_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Dealer

Dealer. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Dealers_Table.Dealer_Id`

_Type_: **[Dealers](Crm.Sales.Dealers.md)**  
_Category_: **System**  
_Inherited From_: **Crm_Dealers_Table.Dealer_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### DistributionChannel

Distribution Channel. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Distribution_Channels_Table.Distribution_Channel_Id`

_Type_: **[DistributionChannels](Crm.Marketing.DistributionChannels.md)**  
_Category_: **System**  
_Inherited From_: **Crm_Distribution_Channels_Table.Distribution_Channel_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### DocumentCurrency

Currency. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Currencies_Table.Currency_Id`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Currencies_Table.Currency_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### EndCustomerParty

Unique party id. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Parties_Table.Id`

_Type_: **[Parties](General.Contacts.Parties.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Parties_Table.Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company to which this SalesAnalyticsEntry applies. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_Companies_Table.Enterprise_Company_Id`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Enterprise_Companies_Table.Enterprise_Company_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompanyLocation

The Enterprise Company Location to which this SalesAnalyticsEntry applies. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cm_Company_Locations_Table.Company_Location_Id`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md)**  
_Category_: **System**  
_Inherited From_: **Cm_Company_Locations_Table.Company_Location_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level1Discount

Level 1 Discount. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Line_Discounts_Table.Line_Discount_Id`

_Type_: **[LineDiscounts](Crm.Pricing.LineDiscounts.md)**  
_Category_: **System**  
_Inherited From_: **Crm_Line_Discounts_Table.Line_Discount_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level2Discount

Level 2 Discount. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Line_Discounts_Table.Line_Discount_Id`

_Type_: **[LineDiscounts](Crm.Pricing.LineDiscounts.md)**  
_Category_: **System**  
_Inherited From_: **Crm_Line_Discounts_Table.Line_Discount_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level3Discount

Level 3 Discount. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Line_Discounts_Table.Line_Discount_Id`

_Type_: **[LineDiscounts](Crm.Pricing.LineDiscounts.md)**  
_Category_: **System**  
_Inherited From_: **Crm_Line_Discounts_Table.Line_Discount_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Product

Unique id of the item. `Required` `Default(New Guid)` `Filter(multi eq)` `ORD` `Inherited from Gen_Products_Table.Id`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Products_Table.Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### ProductPrice

Product Price. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Product_Prices_Table.Product_Price_Id`

_Type_: **[ProductPrices](Crm.Pricing.ProductPrices.md)**  
_Category_: **System**  
_Inherited From_: **Crm_Product_Prices_Table.Product_Price_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### ProductVariant

Product Variant. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Product_Variants_Table.Product_Variant_Id`

_Type_: **[ProductVariants](General.Products.ProductVariants.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Product_Variants_Table.Product_Variant_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### PromotionalPackage

Promotional Package. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Promotional_Packages_Table.Promotional_Package_Id`

_Type_: **[PromotionalPackages](Crm.Pricing.PromotionalPackages.md)**  
_Category_: **System**  
_Inherited From_: **Crm_Promotional_Packages_Table.Promotional_Package_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### SalesPerson

Unique sales person Id. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Crm_Sales_Persons_Table.Sales_Person_Id`

_Type_: **[SalesPersons](Crm.SalesForce.SalesPersons.md)**  
_Category_: **System**  
_Inherited From_: **Crm_Sales_Persons_Table.Sales_Person_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Store

Unique store Id. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Inv_Stores_Table.Id`

_Type_: **[Stores](Logistics.Inventory.Stores.md)**  
_Category_: **System**  
_Inherited From_: **Inv_Stores_Table.Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set: 
Crm_SalesAnalytics

Domain API Entity Type: 
Crm_SalesAnalyticsEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_SalesAnalytics?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_SalesAnalytics?$top=10>

