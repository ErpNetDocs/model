---
uid: Saft.AccountBalances
---
# Saft.AccountBalances (View)


Account balances for SAT-T reporting purpose .

## General
Namespace: [Saft](Saft.md)  
Repository: Saft.AccountBalances  
Introduced In Version: 26.2.1.22  
API access:  ReadOnly  

## Visualization
Display Format: {FromDate}: {ToDate}  
Search Members:   
Category:  Views  
Show in UI:  CannotBeShown  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Saft.AccountBalances](Saft.AccountBalances.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [EndBalanceBase](Saft.AccountBalances.md#endbalancebase) | decimal (38, 2) | Start balance in base currency. `Required` 
| [FromDate](Saft.AccountBalances.md#fromdate) | date | Filter date for start of period. `Required` `Filter(eq)` 
| [ItemKey](Saft.AccountBalances.md#itemkey) | string (64) | Item_Key. `Required` `Introduced in version 26.2.1.27` 
| [StartBalanceBase](Saft.AccountBalances.md#startbalancebase) | decimal (38, 2) | Start balance in base currency. `Required` 
| [ToDate](Saft.AccountBalances.md#todate) | date | Filter date for end of period. `Required` `Filter(eq)` 
| [VouchersInPeriod](Saft.AccountBalances.md#vouchersinperiod) | int32 | Count of Vouchers in period. `Required` `Introduced in version 26.2.1.27` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Saft.AccountBalances.md#account) | [Accounts](Finance.Accounting.Accounts.md) | Account. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id` |
| [EnterpriseCompany](Saft.AccountBalances.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Enterprise company. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_<br />Companies_Table.Enterprise_Company_Id` |


## Attribute Details

### EndBalanceBase

Start balance in base currency. `Required`

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FromDate

Filter date for start of period. `Required` `Filter(eq)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ItemKey

Item_Key. `Required` `Introduced in version 26.2.1.27`

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### StartBalanceBase

Start balance in base currency. `Required`

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ToDate

Filter date for end of period. `Required` `Filter(eq)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### VouchersInPeriod

Count of Vouchers in period. `Required` `Introduced in version 26.2.1.27`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### Account

Account. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id`

Type: **[Accounts](Finance.Accounting.Accounts.md)**  
Category: **System**  
Inherited From: **Acc_Accounts_Table.Account_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

Enterprise company. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_Companies_Table.Enterprise_Company_Id`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Inherited From: **Gen_Enterprise_Companies_Table.Enterprise_Company_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Saft_AccountBalances

Domain API Entity Type: 
Saft_AccountBalancesEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Saft_AccountBalances?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Saft_AccountBalances?$top=10>

