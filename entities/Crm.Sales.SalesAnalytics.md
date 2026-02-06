---
uid: Crm.Sales.SalesAnalytics
---
# Crm.Sales.SalesAnalytics (View)


Sales Analytics provides aggregated and structured sales data optimized for reporting and analysis.

This data type contains pre-grouped sales measures and dimensions derived from sales documents, such as quantities, amounts, discounts, revenues, and related analytical attributes (e.g. customer, product, period, location).

Sales Analytics is designed to support fast and consistent sales reporting, dashboards, KPIs, and business analysis, enabling users to analyze sales performance across different perspectives without processing raw transactional data.

## General
Namespace: [Crm.Sales](Crm.Sales.md)  
Repository: Crm.Sales.SalesAnalytics  
Introduced In Version: 26.2.0.62  
API access:  ReadOnly  

## Visualization
Display Format: {SalesAnalyticId}: {DocumentDate}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Sales.SalesAnalytics](Crm.Sales.SalesAnalytics.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentDate](Crm.Sales.SalesAnalytics.md#documentdate) | date | Date to group for[Required] [Filter(ge;le)] [ORD] 
| [LineAmount](Crm.Sales.SalesAnalytics.md#lineamount) | decimal (38, 2) | Line Amount for date[Required] 
| [LineDiscountAmount](Crm.Sales.SalesAnalytics.md#linediscountamount) | decimal (38, 2) | Discount over Line Amount for Date[Required] 
| [QuantityBase](Crm.Sales.SalesAnalytics.md#quantitybase) | decimal (38, 3) | Base Quantity for Date[Required] 
| [SalesAnalyticId](Crm.Sales.SalesAnalytics.md#salesanalyticid) | guid | Row Id. `Required` `Filter(multi eq)` 
| [StandardQuantityBase](Crm.Sales.SalesAnalytics.md#standardquantitybase) | decimal (38, 3) | Standard Base Quantity for Date[Required] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Customer](Crm.Sales.SalesAnalytics.md#customer) | [Customers](Crm.Sales.Customers.md) | Unique customer Id. |
| [Dealer](Crm.Sales.SalesAnalytics.md#dealer) | [Dealers](Crm.Sales.Dealers.md) | External Dealer for this sales |
| [DistributionChannel](Crm.Sales.SalesAnalytics.md#distributionchannel) | [DistributionChannels](Crm.Marketing.DistributionChannels.md) | Distribution Channel for this sales |
| [DocumentCurrency](Crm.Sales.SalesAnalytics.md#documentcurrency) | [Currencies](General.Currencies.Currencies.md) | Currency for this sales |
| [EndCustomerParty](Crm.Sales.SalesAnalytics.md#endcustomerparty) | [Parties](General.Contacts.Parties.md) | Unique party id. |
| [EnterpriseCompany](Crm.Sales.SalesAnalytics.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The Enterprise Company to which this SalesAnalyticsEntry applies. |
| [EnterpriseCompanyLocation](Crm.Sales.SalesAnalytics.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) | The Enterprise Company Location to which this SalesAnalyticsEntry applies. |
| [Product](Crm.Sales.SalesAnalytics.md#product) | [Products](General.Products.Products.md) | Unique id of the item. |
| [ProductVariant](Crm.Sales.SalesAnalytics.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) | Product Variant for this sales |
| [SalesPerson](Crm.Sales.SalesAnalytics.md#salesperson) | [SalesPersons](Crm.SalesForce.SalesPersons.md) | Unique sales person for this sales |
| [Store](Crm.Sales.SalesAnalytics.md#store) | [Stores](Logistics.Inventory.Stores.md) | Unique store Id. |


## Attribute Details

### DocumentDate

Date to group for[Required] [Filter(ge;le)] [ORD]

Type: **date**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### LineAmount

Line Amount for date[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineDiscountAmount

Discount over Line Amount for Date[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### QuantityBase

Base Quantity for Date[Required]

Type: **decimal (38, 3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SalesAnalyticId

Row Id. `Required` `Filter(multi eq)`

Type: **guid**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### StandardQuantityBase

Standard Base Quantity for Date[Required]

Type: **decimal (38, 3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### Customer

Unique customer Id.

Type: **[Customers](Crm.Sales.Customers.md)**  
Category: **System**  
Inherited From: **Crm_Customers_Table.Customer_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Dealer

External Dealer for this sales

Type: **[Dealers](Crm.Sales.Dealers.md)**  
Category: **System**  
Inherited From: **Crm_Dealers_Table.Dealer_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### DistributionChannel

Distribution Channel for this sales

Type: **[DistributionChannels](Crm.Marketing.DistributionChannels.md)**  
Category: **System**  
Inherited From: **Crm_Distribution_Channels_Table.Distribution_Channel_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### DocumentCurrency

Currency for this sales

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Inherited From: **Gen_Currencies_Table.Currency_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### EndCustomerParty

Unique party id.

Type: **[Parties](General.Contacts.Parties.md)**  
Category: **System**  
Inherited From: **Gen_Parties_Table.Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company to which this SalesAnalyticsEntry applies.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Inherited From: **Gen_Enterprise_Companies_Table.Enterprise_Company_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### EnterpriseCompanyLocation

The Enterprise Company Location to which this SalesAnalyticsEntry applies.

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md)**  
Category: **System**  
Inherited From: **Cm_Company_Locations_Table.Company_Location_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Product

Unique id of the item.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Inherited From: **Gen_Products_Table.Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### ProductVariant

Product Variant for this sales

Type: **[ProductVariants](General.Products.ProductVariants.md)**  
Category: **System**  
Inherited From: **Gen_Product_Variants_Table.Product_Variant_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### SalesPerson

Unique sales person for this sales

Type: **[SalesPersons](Crm.SalesForce.SalesPersons.md)**  
Category: **System**  
Inherited From: **Crm_Sales_Persons_Table.Sales_Person_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Store

Unique store Id.

Type: **[Stores](Logistics.Inventory.Stores.md)**  
Category: **System**  
Inherited From: **Inv_Stores_Table.Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Crm_Sales_SalesAnalytics

Domain API Entity Type: 
Crm_Sales_SalesAnalyticsEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Sales_SalesAnalytics?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Sales_SalesAnalytics?$top=10>

