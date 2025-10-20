---
uid: Logistics.Inventory.TransactionCostCorrectionsSummary
---
# Logistics.Inventory.TransactionCostCorrectionsSummary View

**Namespace:** [Logistics.Inventory](Logistics.Inventory.md)  

Summary of cost corrections, grouped by the line corrected. Entity: Inv_Transaction_Cost_Corrections_Summary

## Default Visualization
Default Display Text Format:  
_{BaseCostAdjustmentValue}: {CostCorrectionAmountValue}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Inventory.StoreTransactions](Logistics.Inventory.StoreTransactions.md)  
Aggregate Root:  
[Logistics.Inventory.StoreTransactions](Logistics.Inventory.StoreTransactions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseCostAdjustment](Logistics.Inventory.TransactionCostCorrectionsSummary.md#basecostadjustment) | [Amount (38, 2)](../data-types.md#amount) | The cost correction in Base currency. `Currency: TransactionObj.EnterpriseCompany.BaseCurrency` `Required` `Filter(eq;ge;le)` 
| [CostCorrectionAmount](Logistics.Inventory.TransactionCostCorrectionsSummary.md#costcorrectionamount) | [Amount (38, 2)](../data-types.md#amount) | The cost correction in the original currency of the store transaction. `Currency: TransactionObj.DocumentCurrency` `Required` `Filter(eq;ge;le)` 
| [ProductCostAdjustment](Logistics.Inventory.TransactionCostCorrectionsSummary.md#productcostadjustment) | [Amount (38, 2)](../data-types.md#amount) | The cost correction in Products currency. `Currency: TransactionLine.Product.CostingCurrency` `Required` `Filter(eq;ge;le)` 
| [StoreCostAdjustment](Logistics.Inventory.TransactionCostCorrectionsSummary.md#storecostadjustment) | [Amount (38, 2)](../data-types.md#amount) | The cost correction in Stores currency. `Currency: TransactionObj.Store.Currency` `Required` `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [TransactionLine](Logistics.Inventory.TransactionCostCorrectionsSummary.md#transactionline) | [StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) | Unique transaction line id. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Transaction_Line_Id` |
| [TransactionObj](Logistics.Inventory.TransactionCostCorrectionsSummary.md#transactionobj) | [StoreTransactions](Logistics.Inventory.StoreTransactions.md) | The transaction to which the transaction line belongs. `Required` `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Transaction_Id` `Owner` |


## Attribute Details

### BaseCostAdjustment

The cost correction in Base currency. `Currency: TransactionObj.EnterpriseCompany.BaseCurrency` `Required` `Filter(eq;ge;le)`

_Type_: **[Amount (38, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CostCorrectionAmount

The cost correction in the original currency of the store transaction. `Currency: TransactionObj.DocumentCurrency` `Required` `Filter(eq;ge;le)`

_Type_: **[Amount (38, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ProductCostAdjustment

The cost correction in Products currency. `Currency: TransactionLine.Product.CostingCurrency` `Required` `Filter(eq;ge;le)`

_Type_: **[Amount (38, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StoreCostAdjustment

The cost correction in Stores currency. `Currency: TransactionObj.Store.Currency` `Required` `Filter(eq;ge;le)`

_Type_: **[Amount (38, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### TransactionLine

Unique transaction line id. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Transaction_Line_Id`

_Type_: **[StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md)**  
_Category_: **System**  
_Inherited From_: **Inv_Transaction_Lines_Table.Transaction_Line_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### TransactionObj

The transaction to which the transaction line belongs. `Required` `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Transaction_Id` `Owner`

_Type_: **[StoreTransactions](Logistics.Inventory.StoreTransactions.md)**  
_Category_: **System**  
_Inherited From_: **Inv_Transaction_Lines_Table.Transaction_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set:
Logistics_Inventory_TransactionCostCorrectionsSummary

Domain API Entity Type:
Logistics_Inventory_TransactionCostCorrectionsSummaryEntry

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Inventory_TransactionCostCorrectionsSummary?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_TransactionCostCorrectionsSummary?$top=10>

