---
uid: Finance.Accounting.CurrentBalances
---
# Finance.Accounting.CurrentBalances View

**Namespace:** [Finance.Accounting](Finance.Accounting.md)  

Contains live account balances calculated from all released accounting vouchers in the system. Reflects the up-to-date financial position, including transactions with future dates. Entity: Acc_Current_Balances (Introduced in version 25.1.3.29)

## Default Visualization
Default Display Text Format:  
_{EnterpriseCompanyId}: {EnterpriseCompanyLocationId}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Accounting.CurrentBalances](Finance.Accounting.CurrentBalances.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Balance](Finance.Accounting.CurrentBalances.md#balance) | decimal (38, 2) | Net current balance (Debit - Credit). `Required` 
| [BalanceBase](Finance.Accounting.CurrentBalances.md#balancebase) | decimal (38, 2) | Current balance in base currency. `Required` 
| [BalanceReporting](Finance.Accounting.CurrentBalances.md#balancereporting) | decimal (38, 2) | Current balance in reporting currency. `Required` 
| [ItemKey](Finance.Accounting.CurrentBalances.md#itemkey) | string (64) | Item Key. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.CurrentBalances.md#account) | [Accounts](Finance.Accounting.Accounts.md) | Account reference. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id` `FilterableReference` |
| [CostCenter](Finance.Accounting.CurrentBalances.md#costcenter) | [CostCenters](Finance.Accounting.CostCenters.md) | Cost Center. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Cost_Centers_Table.Cost_Center_Id` |
| [Currency](Finance.Accounting.CurrentBalances.md#currency) | [Currencies](General.Currencies.Currencies.md) | Currency. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Currencies_Table.Currency_Id` |
| [EnterpriseCompany](Finance.Accounting.CurrentBalances.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Legal entity . `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_<br />Companies_Table.Enterprise_Company_Id` `FilterableReference` |
| [EnterpriseCompanyLocation](Finance.Accounting.CurrentBalances.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) | Optional location/branch filter. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cm_Company_Locations_Table.Company_Location_Id` `FilterableReference` |
| [ProfitCenter](Finance.Accounting.CurrentBalances.md#profitcenter) | [ProfitCenters](Finance.Accounting.ProfitCenters.md) | Profit Center. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Profit_Centers_Table.Profit_Center_Id` |


## Attribute Details

### Balance

Net current balance (Debit - Credit). `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### BalanceBase

Current balance in base currency. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### BalanceReporting

Current balance in reporting currency. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ItemKey

Item Key. `Required`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Account

Account reference. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id` `FilterableReference`

_Type_: **[Accounts](Finance.Accounting.Accounts.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Accounts_Table.Account_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### CostCenter

Cost Center. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Cost_Centers_Table.Cost_Center_Id`

_Type_: **[CostCenters](Finance.Accounting.CostCenters.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Cost_Centers_Table.Cost_Center_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Currency

Currency. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Currencies_Table.Currency_Id`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Currencies_Table.Currency_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

Legal entity . `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_Companies_Table.Enterprise_Company_Id` `FilterableReference`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Enterprise_Companies_Table.Enterprise_Company_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompanyLocation

Optional location/branch filter. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cm_Company_Locations_Table.Company_Location_Id` `FilterableReference`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md)**  
_Category_: **System**  
_Inherited From_: **Cm_Company_Locations_Table.Company_Location_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### ProfitCenter

Profit Center. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Profit_Centers_Table.Profit_Center_Id`

_Type_: **[ProfitCenters](Finance.Accounting.ProfitCenters.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Profit_Centers_Table.Profit_Center_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set:
Finance_Accounting_CurrentBalances

Domain API Entity Type:
Finance_Accounting_CurrentBalancesEntry

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Accounting_CurrentBalances?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Accounting_CurrentBalances?$top=10>

