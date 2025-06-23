---
uid: Finance.Accounting.HistoricalBalances
---
# Finance.Accounting.HistoricalBalances View

**Namespace:** [Finance.Accounting](Finance.Accounting.md)  

Account balances with analytical dimensions as of the selected date. Entity: Acc_Historical_Balances (Introduced in version 25.1.2.93)

## Default Visualization
Default Display Text Format:  
_{BalanceValue}: {BalanceBaseValue}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Accounting.HistoricalBalances](Finance.Accounting.HistoricalBalances.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Balance](Finance.Accounting.HistoricalBalances.md#balance) | [Amount (19, 2)](../data-types.md#amount) | Account balance in the original accounting currency as of the selected date. `Currency: Currency` `Required` 
| [BalanceBase](Finance.Accounting.HistoricalBalances.md#balancebase) | [Amount (19, 2)](../data-types.md#amount) | Account balance in the company’s base currency as of the selected date. `Currency: EnterpriseCompany.BaseCurrency` `Required` 
| [BalanceReporting](Finance.Accounting.HistoricalBalances.md#balancereporting) | [Amount (19, 2)](../data-types.md#amount) | Account balance in the reporting currency as of the selected date. `Currency: EnterpriseCompany.ReportingCurrency` `Required` 
| [Date](Finance.Accounting.HistoricalBalances.md#date) | date | The report shows balances as of this date. This is a required filter; if not set, the view returns no data. `Required` `Filter(eq)` 
| [ItemKey](Finance.Accounting.HistoricalBalances.md#itemkey) | string (64) | Combined analytical dimensions key used for grouping and filtering account balances. `Required` `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.HistoricalBalances.md#account) | [Accounts](Finance.Accounting.Accounts.md) | The general ledger account for which the balance is calculated. Required field. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id` `FilterableReference` |
| [CostCenter](Finance.Accounting.HistoricalBalances.md#costcenter) | [CostCenters](Finance.Accounting.CostCenters.md) | The cost center associated with the account balance for analytical and reporting purposes. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Cost_Centers_Table.Cost_Center_Id` |
| [Currency](Finance.Accounting.HistoricalBalances.md#currency) | [Currencies](General.Currencies.Currencies.md) | Currency in which the account balance is shown. Required field. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Currencies_Table.Currency_Id` `FilterableReference` |
| [EnterpriseCompany](Finance.Accounting.HistoricalBalances.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company whose accounts are being analyzed. Required for filtering accounting data. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_<br />Companies_Table.Enterprise_Company_Id` `FilterableReference` |
| [ProfitCenter](Finance.Accounting.HistoricalBalances.md#profitcenter) | [ProfitCenters](Finance.Accounting.ProfitCenters.md) | The profit center associated with the account balance for profit analysis and segment reporting. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Profit_Centers_Table.Profit_Center_Id` |


## Attribute Details

### Balance

Account balance in the original accounting currency as of the selected date. `Currency: Currency` `Required`

_Type_: **[Amount (19, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### BalanceBase

Account balance in the company’s base currency as of the selected date. `Currency: EnterpriseCompany.BaseCurrency` `Required`

_Type_: **[Amount (19, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### BalanceReporting

Account balance in the reporting currency as of the selected date. `Currency: EnterpriseCompany.ReportingCurrency` `Required`

_Type_: **[Amount (19, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Date

The report shows balances as of this date. This is a required filter; if not set, the view returns no data. `Required` `Filter(eq)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ItemKey

Combined analytical dimensions key used for grouping and filtering account balances. `Required` `Filter(eq;like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Account

The general ledger account for which the balance is calculated. Required field. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id` `FilterableReference`

_Type_: **[Accounts](Finance.Accounting.Accounts.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Accounts_Table.Account_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### CostCenter

The cost center associated with the account balance for analytical and reporting purposes. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Cost_Centers_Table.Cost_Center_Id`

_Type_: **[CostCenters](Finance.Accounting.CostCenters.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Cost_Centers_Table.Cost_Center_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Currency

Currency in which the account balance is shown. Required field. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Currencies_Table.Currency_Id` `FilterableReference`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Currencies_Table.Currency_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

The enterprise company whose accounts are being analyzed. Required for filtering accounting data. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_Companies_Table.Enterprise_Company_Id` `FilterableReference`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Enterprise_Companies_Table.Enterprise_Company_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### ProfitCenter

The profit center associated with the account balance for profit analysis and segment reporting. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Profit_Centers_Table.Profit_Center_Id`

_Type_: **[ProfitCenters](Finance.Accounting.ProfitCenters.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Profit_Centers_Table.Profit_Center_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Accounting_HistoricalBalances?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Accounting_HistoricalBalances?$top=10>

