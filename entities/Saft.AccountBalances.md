---
uid: Saft.AccountBalances
---
# Saft.AccountBalances View

**Namespace:** [Saft](Saft.md)  

Account balances for SAT-T reporting purpose . Entity: Saft_Account_Balances (Introduced in version 26.2.1.22)

## Default Visualization
Default Display Text Format:  
_{FromDate}: {ToDate}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _CannotBeShown_  
API access:  _ReadOnly_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Saft.AccountBalances](Saft.AccountBalances.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [EndBalanceBase](Saft.AccountBalances.md#endbalancebase) | decimal (38, 2) | Start balance in base currency. `Required` 
| [FromDate](Saft.AccountBalances.md#fromdate) | date | Filter date for start of period. `Required` `Filter(eq)` 
| [StartBalanceBase](Saft.AccountBalances.md#startbalancebase) | decimal (38, 2) | Start balance in base currency. `Required` 
| [ToDate](Saft.AccountBalances.md#todate) | date | Filter date for end of period. `Required` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Saft.AccountBalances.md#account) | [Accounts](Finance.Accounting.Accounts.md) | Account. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id` |
| [EnterpriseCompany](Saft.AccountBalances.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Enterprise company. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_<br />Companies_Table.Enterprise_Company_Id` |


## Attribute Details

### EndBalanceBase

Start balance in base currency. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### FromDate

Filter date for start of period. `Required` `Filter(eq)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StartBalanceBase

Start balance in base currency. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ToDate

Filter date for end of period. `Required` `Filter(eq)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Account

Account. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id`

_Type_: **[Accounts](Finance.Accounting.Accounts.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Accounts_Table.Account_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

Enterprise company. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_Companies_Table.Enterprise_Company_Id`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Enterprise_Companies_Table.Enterprise_Company_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set: 
Saft_AccountBalances

Domain API Entity Type: 
Saft_AccountBalancesEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Saft_AccountBalances?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Saft_AccountBalances?$top=10>

