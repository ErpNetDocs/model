---
uid: Logistics.Inventory.CurrentBalanceAdjustedCosts
---
# Logistics.Inventory.CurrentBalanceAdjustedCosts View

**Namespace:** [Logistics.Inventory](Logistics.Inventory.md)  

The current inventory balances with adjustments, grouped by storage key (Store, Product, Lot, etc.). Entity: Inv_Current_Balance_Adjusted_Costs (Introduced in version 24.1.5.34)

## Default Visualization
Default Display Text Format:  
_{BaseCostValue}: {EnterpriseCompanyId}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _HiddenByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.CurrentBalanceAdjustedCosts](Logistics.Inventory.CurrentBalanceAdjustedCosts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseCost](Logistics.Inventory.CurrentBalanceAdjustedCosts.md#basecost) | [Amount (38, 2)](../data-types.md#amount) | The cost of the inventory in base currency of the enterprise company. `Currency: EnterpriseCompany.BaseCurrency` `Required` `Filter(eq;ge;le)` 
| [ProductCost](Logistics.Inventory.CurrentBalanceAdjustedCosts.md#productcost) | [Amount (38, 2)](../data-types.md#amount) | The cost of the inventory in the products currency. `Currency: Product.CostingCurrency` `Required` 
| [QuantityBase](Logistics.Inventory.CurrentBalanceAdjustedCosts.md#quantitybase) | [Quantity (38, 3)](../data-types.md#quantity) | The quantity of the stock received/issued in base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` 
| [StoreCost](Logistics.Inventory.CurrentBalanceAdjustedCosts.md#storecost) | [Amount (38, 2)](../data-types.md#amount) | The cost of the inventory in the stores currency. `Currency: Store.Currency` `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Logistics.Inventory.CurrentBalanceAdjustedCosts.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company which issued the document. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id` |
| [Lot](Logistics.Inventory.CurrentBalanceAdjustedCosts.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If non-null, contains the specific lot to use for the movement. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Lot_Id` |
| [Product](Logistics.Inventory.CurrentBalanceAdjustedCosts.md#product) | [Products](General.Products.Products.md) | The item that was received/issued. `Required` `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Product_Id` `FilterableReference` |
| [ProductVariant](Logistics.Inventory.CurrentBalanceAdjustedCosts.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Product_Variant_Id` |
| [SerialNumber](Logistics.Inventory.CurrentBalanceAdjustedCosts.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Item serial number for serialized items. null for non-serialized items. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Serial_Number_Id` |
| [Store](Logistics.Inventory.CurrentBalanceAdjustedCosts.md#store) | [Stores](Logistics.Inventory.Stores.md) | The store from which the goods are received or issued. `Required` `Filter(multi eq)` `Inherited from Inv_Transactions_Table.Store_Id` |
| [StoreBin](Logistics.Inventory.CurrentBalanceAdjustedCosts.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | Store bin, from/to which the transaction was performed. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Store_Bin_Id` |


## Attribute Details

### BaseCost

The cost of the inventory in base currency of the enterprise company. `Currency: EnterpriseCompany.BaseCurrency` `Required` `Filter(eq;ge;le)`

_Type_: **[Amount (38, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ProductCost

The cost of the inventory in the products currency. `Currency: Product.CostingCurrency` `Required`

_Type_: **[Amount (38, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

The quantity of the stock received/issued in base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)`

_Type_: **[Quantity (38, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StoreCost

The cost of the inventory in the stores currency. `Currency: Store.Currency` `Required`

_Type_: **[Amount (38, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

The enterprise company which issued the document. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Documents_Table.Enterprise_Company_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Lot

If non-null, contains the specific lot to use for the movement. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Lot_Id`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Inv_Transaction_Lines_Table.Lot_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The item that was received/issued. `Required` `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Product_Id` `FilterableReference`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Inherited From_: **Inv_Transaction_Lines_Table.Product_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ProductVariant

If specified determines which product variant of the current product in this line is used. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Product_Variant_Id`

_Type_: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Inv_Transaction_Lines_Table.Product_Variant_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SerialNumber

Item serial number for serialized items. null for non-serialized items. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Serial_Number_Id`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Inv_Transaction_Lines_Table.Serial_Number_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Store

The store from which the goods are received or issued. `Required` `Filter(multi eq)` `Inherited from Inv_Transactions_Table.Store_Id`

_Type_: **[Stores](Logistics.Inventory.Stores.md)**  
_Category_: **System**  
_Inherited From_: **Inv_Transactions_Table.Store_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### StoreBin

Store bin, from/to which the transaction was performed. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Store_Bin_Id`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Inv_Transaction_Lines_Table.Store_Bin_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Inventory_CurrentBalanceAdjustedCosts?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_CurrentBalanceAdjustedCosts?$top=10>

