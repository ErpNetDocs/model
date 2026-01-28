---
uid: Logistics.Inventory.CurrentBalances
---
# Logistics.Inventory.CurrentBalances (View)


The current inventory balances, grouped by storage key (Store, Product, Lot, etc.).

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.CurrentBalances  
Introduced In Version: 22.1.4.33  
API access:  ReadWrite  

## Visualization
Display Format: {BaseCostValue}: {EnterpriseCompanyId}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.CurrentBalances](Logistics.Inventory.CurrentBalances.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseCost](Logistics.Inventory.CurrentBalances.md#basecost) | [Amount (38, 2)](../data-types.md#amount) | The cost of the inventory in base currency of the enterprise company. `Currency: EnterpriseCompany.BaseCurrency` `Required` `Filter(ge;le)` 
| [ProductCost](Logistics.Inventory.CurrentBalances.md#productcost) | [Amount (38, 2)](../data-types.md#amount) | The cost of the inventory in the products currency. `Currency: Product.CostingCurrency` `Required` 
| [QuantityBase](Logistics.Inventory.CurrentBalances.md#quantitybase) | [Quantity (38, 3)](../data-types.md#quantity) | The quantity of the stock received/issued in base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` `ReadOnly` 
| [StoreCost](Logistics.Inventory.CurrentBalances.md#storecost) | [Amount (38, 2)](../data-types.md#amount) | The cost of the inventory in the stores currency. `Currency: Store.Currency` `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Logistics.Inventory.CurrentBalances.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company which issued the document. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id` `Introduced in version 24.1.0.7` |
| [Lot](Logistics.Inventory.CurrentBalances.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If non-null, contains the specific lot to use for the movement. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Lot_Id` `Introduced in version 24.1.0.7` |
| [Product](Logistics.Inventory.CurrentBalances.md#product) | [Products](General.Products.Products.md) | The item that was received/issued. `Required` `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Product_Id` `Introduced in version 24.1.0.7` `FilterableReference` |
| [ProductVariant](Logistics.Inventory.CurrentBalances.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Product_Variant_Id` `Introduced in version 24.1.0.7` |
| [SerialNumber](Logistics.Inventory.CurrentBalances.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Item serial number for serialized items. null for non-serialized items. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Serial_Number_Id` `Introduced in version 24.1.0.7` |
| [Store](Logistics.Inventory.CurrentBalances.md#store) | [Stores](Logistics.Inventory.Stores.md) | The store from which the goods are received or issued. `Required` `Filter(multi eq)` `Inherited from Inv_Transactions_Table.Store_Id` `Introduced in version 24.1.0.7` |
| [StoreBin](Logistics.Inventory.CurrentBalances.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | Store bin, from/to which the transaction was performed. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Store_Bin_Id` `Introduced in version 24.1.0.7` |


## Attribute Details

### BaseCost

The cost of the inventory in base currency of the enterprise company. `Currency: EnterpriseCompany.BaseCurrency` `Required` `Filter(ge;le)`

Type: **[Amount (38, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ProductCost

The cost of the inventory in the products currency. `Currency: Product.CostingCurrency` `Required`

Type: **[Amount (38, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### QuantityBase

The quantity of the stock received/issued in base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` `ReadOnly`

Type: **[Quantity (38, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### StoreCost

The cost of the inventory in the stores currency. `Currency: Store.Currency` `Required`

Type: **[Amount (38, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

The enterprise company which issued the document. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id` `Introduced in version 24.1.0.7`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Inherited From: **Gen_Documents_Table.Enterprise_Company_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

If non-null, contains the specific lot to use for the movement. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Lot_Id` `Introduced in version 24.1.0.7`

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Lot_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The item that was received/issued. `Required` `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Product_Id` `Introduced in version 24.1.0.7` `FilterableReference`

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Product_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ProductVariant

If specified determines which product variant of the current product in this line is used. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Product_Variant_Id` `Introduced in version 24.1.0.7`

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Product_Variant_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SerialNumber

Item serial number for serialized items. null for non-serialized items. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Serial_Number_Id` `Introduced in version 24.1.0.7`

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Serial_Number_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Store

The store from which the goods are received or issued. `Required` `Filter(multi eq)` `Inherited from Inv_Transactions_Table.Store_Id` `Introduced in version 24.1.0.7`

Type: **[Stores](Logistics.Inventory.Stores.md)**  
Category: **System**  
Inherited From: **Inv_Transactions_Table.Store_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### StoreBin

Store bin, from/to which the transaction was performed. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Store_Bin_Id` `Introduced in version 24.1.0.7`

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Store_Bin_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Logistics_Inventory_CurrentBalances

Domain API Entity Type: 
Logistics_Inventory_CurrentBalance

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_CurrentBalances?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_CurrentBalances?$top=10>

