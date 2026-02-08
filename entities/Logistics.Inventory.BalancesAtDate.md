---
uid: Logistics.Inventory.BalancesAtDate
---
# Logistics.Inventory.BalancesAtDate (View)


View past inventory balances as they were on a specific date. Filter by the 'Date' column to select the date for which you want to retrieve stock levels. This report provides a snapshot of inventory at that moment in time, helping with audits, stock analysis, and historical tracking.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.BalancesAtDate  
Introduced In Version: 25.1.1.62  
API access:  ReadWrite  

## Visualization
Display Format: {BaseCostValue}: {Date}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.BalancesAtDate](Logistics.Inventory.BalancesAtDate.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseCost](Logistics.Inventory.BalancesAtDate.md#basecost) | [Amount (38, 2)](../data-types.md#amount) | The cost of the inventory in base currency of the enterprise company.`Currency: EnterpriseCompany.BaseCurrency` `Required` 
| [Date](Logistics.Inventory.BalancesAtDate.md#date) | date | The date parameter used to compute the balances.`Required` `Filter(eq)` 
| [ProductCost](Logistics.Inventory.BalancesAtDate.md#productcost) | [Amount (38, 2)](../data-types.md#amount) | The cost of the inventory in the products currency.`Currency: Product.CostingCurrency` `Required` 
| [QuantityBase](Logistics.Inventory.BalancesAtDate.md#quantitybase) | [Quantity (38, 3)](../data-types.md#quantity) | The quantity of the stock received/issued in base measurement unit`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` 
| [StoreCost](Logistics.Inventory.BalancesAtDate.md#storecost) | [Amount (38, 2)](../data-types.md#amount) | The cost of the inventory in the stores currency.`Currency: Store.Currency` `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Logistics.Inventory.BalancesAtDate.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company |
| [Lot](Logistics.Inventory.BalancesAtDate.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If non-null, contains the specific lot to use for the movement |
| [Product](Logistics.Inventory.BalancesAtDate.md#product) | [Products](General.Products.Products.md) | The product |
| [ProductVariant](Logistics.Inventory.BalancesAtDate.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. |
| [SerialNumber](Logistics.Inventory.BalancesAtDate.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Item serial number for serialized items. NULL for non-serialized items |
| [Store](Logistics.Inventory.BalancesAtDate.md#store) | [Stores](Logistics.Inventory.Stores.md) | The store |
| [StoreBin](Logistics.Inventory.BalancesAtDate.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | Store bin, from/to which the transaction was performed. |


## Attribute Details

### BaseCost

The cost of the inventory in base currency of the enterprise company.`Currency: EnterpriseCompany.BaseCurrency` `Required`

Type: **[Amount (38, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Date

The date parameter used to compute the balances.`Required` `Filter(eq)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ProductCost

The cost of the inventory in the products currency.`Currency: Product.CostingCurrency` `Required`

Type: **[Amount (38, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### QuantityBase

The quantity of the stock received/issued in base measurement unit`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required`

Type: **[Quantity (38, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StoreCost

The cost of the inventory in the stores currency.`Currency: Store.Currency` `Required`

Type: **[Amount (38, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

The enterprise company

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Inherited From: **Gen_Documents_Table.Enterprise_Company_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

If non-null, contains the specific lot to use for the movement

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Lot_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The product

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Product_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductVariant

If specified determines which product variant of the current product in this line is used.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Product_Variant_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### SerialNumber

Item serial number for serialized items. NULL for non-serialized items

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Serial_Number_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Store

The store

Type: **[Stores](Logistics.Inventory.Stores.md)**  
Category: **System**  
Inherited From: **Inv_Transactions_Table.Store_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### StoreBin

Store bin, from/to which the transaction was performed.

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Store_Bin_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  


## API

Domain API Entity Set: 
Logistics_Inventory_BalancesAtDate

Domain API Entity Type: 
Logistics_Inventory_BalancesAtDateEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_BalancesAtDate?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_BalancesAtDate?$top=10>

