---
uid: Finance.Accounting.CurrentBalances
---
# Finance.Accounting.CurrentBalances (View)


Contains live account balances calculated from all released accounting vouchers in the system. Reflects the up-to-date financial position, including transactions with future dates.

## General
Namespace: [Finance.Accounting](Finance.Accounting.md)  
Repository: Finance.Accounting.CurrentBalances  
Introduced In Version: 25.1.3.29  
API access:  ReadWrite  

## Visualization
Display Format: {EnterpriseCompanyId}: {EnterpriseCompanyLocationId}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

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

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BalanceBase

Current balance in base currency. `Required`

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BalanceReporting

Current balance in reporting currency. `Required`

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ItemKey

Item Key. `Required`

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  


## Reference Details

### Account

Account reference. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id` `FilterableReference`

Type: **[Accounts](Finance.Accounting.Accounts.md)**  
Category: **System**  
Inherited From: **Acc_Accounts_Table.Account_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### CostCenter

Cost Center. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Cost_Centers_Table.Cost_Center_Id`

Type: **[CostCenters](Finance.Accounting.CostCenters.md)**  
Category: **System**  
Inherited From: **Acc_Cost_Centers_Table.Cost_Center_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Currency

Currency. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Currencies_Table.Currency_Id`

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Inherited From: **Gen_Currencies_Table.Currency_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

Legal entity . `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_Companies_Table.Enterprise_Company_Id` `FilterableReference`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Inherited From: **Gen_Enterprise_Companies_Table.Enterprise_Company_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### EnterpriseCompanyLocation

Optional location/branch filter. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cm_Company_Locations_Table.Company_Location_Id` `FilterableReference`

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md)**  
Category: **System**  
Inherited From: **Cm_Company_Locations_Table.Company_Location_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### ProfitCenter

Profit Center. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Profit_Centers_Table.Profit_Center_Id`

Type: **[ProfitCenters](Finance.Accounting.ProfitCenters.md)**  
Category: **System**  
Inherited From: **Acc_Profit_Centers_Table.Profit_Center_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Finance_Accounting_CurrentBalances

Domain API Entity Type: 
Finance_Accounting_CurrentBalancesEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Accounting_CurrentBalances?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Accounting_CurrentBalances?$top=10>

