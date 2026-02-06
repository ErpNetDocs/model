---
uid: Finance.Accounting.HistoricalBalances
---
# Finance.Accounting.HistoricalBalances (View)


Account balances with analytical dimensions as of the selected historical date. Used for reviewing past financial positions based on posted transactions up to that point.

## General
Namespace: [Finance.Accounting](Finance.Accounting.md)  
Repository: Finance.Accounting.HistoricalBalances  
Introduced In Version: 25.1.2.93  
API access:  ReadWrite  

## Visualization
Display Format: {BalanceValue}: {BalanceBaseValue}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Accounting.HistoricalBalances](Finance.Accounting.HistoricalBalances.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Balance](Finance.Accounting.HistoricalBalances.md#balance) | [Amount (19, 2)](../data-types.md#amount) | Account balance in the original accounting currency as of the selected date.[Currency: Currency] [Required] 
| [BalanceBase](Finance.Accounting.HistoricalBalances.md#balancebase) | [Amount (19, 2)](../data-types.md#amount) | Account balance in the company’s base currency as of the selected date.[Currency: EnterpriseCompany.BaseCurrency] [Required] 
| [BalanceReporting](Finance.Accounting.HistoricalBalances.md#balancereporting) | [Amount (19, 2)](../data-types.md#amount) | Account balance in the reporting currency as of the selected date.[Currency: EnterpriseCompany.ReportingCurrency] [Required] 
| [Date](Finance.Accounting.HistoricalBalances.md#date) | date | The report shows balances as of this date. This is a required filter; if not set, the view returns no data.[Required] [Filter(eq)] 
| [ItemKey](Finance.Accounting.HistoricalBalances.md#itemkey) | string (64) | Combined analytical dimensions key used for grouping and filtering account balances.[Required] [Filter(eq;like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.HistoricalBalances.md#account) | [Accounts](Finance.Accounting.Accounts.md) | The general ledger account for which the balance is calculated. Required field. |
| [CostCenter](Finance.Accounting.HistoricalBalances.md#costcenter) | [CostCenters](Finance.Accounting.CostCenters.md) | The cost center associated with the account balance for analytical and reporting purposes. |
| [Currency](Finance.Accounting.HistoricalBalances.md#currency) | [Currencies](General.Currencies.Currencies.md) | Currency in which the account balance is shown. Required field. |
| [EnterpriseCompany](Finance.Accounting.HistoricalBalances.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company whose accounts are being analyzed. Required for filtering accounting data. |
| [ProfitCenter](Finance.Accounting.HistoricalBalances.md#profitcenter) | [ProfitCenters](Finance.Accounting.ProfitCenters.md) | The profit center associated with the account balance for profit analysis and segment reporting. |


## Attribute Details

### Balance

Account balance in the original accounting currency as of the selected date.[Currency: Currency] [Required]

Type: **[Amount (19, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BalanceBase

Account balance in the company’s base currency as of the selected date.[Currency: EnterpriseCompany.BaseCurrency] [Required]

Type: **[Amount (19, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BalanceReporting

Account balance in the reporting currency as of the selected date.[Currency: EnterpriseCompany.ReportingCurrency] [Required]

Type: **[Amount (19, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Date

The report shows balances as of this date. This is a required filter; if not set, the view returns no data.[Required] [Filter(eq)]

Type: **date**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ItemKey

Combined analytical dimensions key used for grouping and filtering account balances.[Required] [Filter(eq;like)]

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  


## Reference Details

### Account

The general ledger account for which the balance is calculated. Required field.

Type: **[Accounts](Finance.Accounting.Accounts.md)**  
Category: **System**  
Inherited From: **Acc_Accounts_Table.Account_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### CostCenter

The cost center associated with the account balance for analytical and reporting purposes.

Type: **[CostCenters](Finance.Accounting.CostCenters.md)**  
Category: **System**  
Inherited From: **Acc_Cost_Centers_Table.Cost_Center_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Currency

Currency in which the account balance is shown. Required field.

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Inherited From: **Gen_Currencies_Table.Currency_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The enterprise company whose accounts are being analyzed. Required for filtering accounting data.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Inherited From: **Gen_Enterprise_Companies_Table.Enterprise_Company_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### ProfitCenter

The profit center associated with the account balance for profit analysis and segment reporting.

Type: **[ProfitCenters](Finance.Accounting.ProfitCenters.md)**  
Category: **System**  
Inherited From: **Acc_Profit_Centers_Table.Profit_Center_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Finance_Accounting_HistoricalBalances

Domain API Entity Type: 
Finance_Accounting_HistoricalBalancesEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Accounting_HistoricalBalances?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Accounting_HistoricalBalances?$top=10>

