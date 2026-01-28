---
uid: Logistics.Inventory.TransactionCostCorrectionsSummary
---
# Logistics.Inventory.TransactionCostCorrectionsSummary (View)


Summary of cost corrections, grouped by the line corrected.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.TransactionCostCorrectionsSummary  
API access:  ReadWrite  

## Visualization
Display Format: {BaseCostAdjustmentValue}: {CostCorrectionAmountValue}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

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

Type: **[Amount (38, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CostCorrectionAmount

The cost correction in the original currency of the store transaction. `Currency: TransactionObj.DocumentCurrency` `Required` `Filter(eq;ge;le)`

Type: **[Amount (38, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ProductCostAdjustment

The cost correction in Products currency. `Currency: TransactionLine.Product.CostingCurrency` `Required` `Filter(eq;ge;le)`

Type: **[Amount (38, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StoreCostAdjustment

The cost correction in Stores currency. `Currency: TransactionObj.Store.Currency` `Required` `Filter(eq;ge;le)`

Type: **[Amount (38, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### TransactionLine

Unique transaction line id. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Transaction_Line_Id`

Type: **[StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Transaction_Line_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### TransactionObj

The transaction to which the transaction line belongs. `Required` `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Transaction_Id` `Owner`

Type: **[StoreTransactions](Logistics.Inventory.StoreTransactions.md)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Transaction_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Logistics_Inventory_TransactionCostCorrectionsSummary

Domain API Entity Type: 
Logistics_Inventory_TransactionCostCorrectionsSummaryEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_TransactionCostCorrectionsSummary?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_TransactionCostCorrectionsSummary?$top=10>

