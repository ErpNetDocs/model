---
uid: Finance.Accounting.AccountStatement
---
# Finance.Accounting.AccountStatement View

**Namespace:** [Finance.Accounting](Finance.Accounting.md)  

Provides a chronological breakdown of all accounting transactions for each general ledger account within a specified date range. For each account, the report shows the opening, total debits and credits, and the closing balance, followed by a detailed list of all associated accounting vouchers. From Date and To Date must be filtered using exact dates to define the reporting window precisely. Entity: Acc_Account_Statement (Introduced in version 25.1.3.31)

## Default Visualization
Default Display Text Format:  
_{FromDate}: {ToDate}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Accounting.AccountStatement](Finance.Accounting.AccountStatement.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Balance](Finance.Accounting.AccountStatement.md#balance) | decimal (38, 2) | Balance is running sum of (Opening + Debit - Credit) calculated for each row of group. `Required` 
| [BalanceBase](Finance.Accounting.AccountStatement.md#balancebase) | decimal (38, 2) | Calculated as Balance over Base currency. `Required` 
| [BalanceReporting](Finance.Accounting.AccountStatement.md#balancereporting) | decimal (38, 2) | Calculated as Balance over Reporting currency. `Required` 
| [Closing](Finance.Accounting.AccountStatement.md#closing) | decimal (38, 2) | Closing Balance(at the end of reporting period). `Required` 
| [ClosingBase](Finance.Accounting.AccountStatement.md#closingbase) | decimal (38, 2) | Closing Balance(in Base currency). `Required` 
| [ClosingReporting](Finance.Accounting.AccountStatement.md#closingreporting) | decimal (38, 2) | Closing Balance(in Reporting currency). `Required` 
| [Credit](Finance.Accounting.AccountStatement.md#credit) | decimal (18, 2) | Credit. `Required` 
| [CreditBase](Finance.Accounting.AccountStatement.md#creditbase) | decimal (18, 2) | Credit Base. `Required` 
| [CreditReporting](Finance.Accounting.AccountStatement.md#creditreporting) | decimal (18, 2) | Credit Reporting. `Required` 
| [Debit](Finance.Accounting.AccountStatement.md#debit) | decimal (18, 2) | Debit. `Required` 
| [DebitBase](Finance.Accounting.AccountStatement.md#debitbase) | decimal (18, 2) | Debit Base. `Required` 
| [DebitReporting](Finance.Accounting.AccountStatement.md#debitreporting) | decimal (18, 2) | Debit Reporting. `Required` 
| [DocumentDate](Finance.Accounting.AccountStatement.md#documentdate) | date | Document Date. `Required` `Filter(ge;le)` 
| [FromDate](Finance.Accounting.AccountStatement.md#fromdate) | date | Period Start Date - Should be filtered with exact date. `Required` `Filter(eq)` 
| [ItemKey](Finance.Accounting.AccountStatement.md#itemkey) | string (64) | Item Key. `Required` 
| [MovementType](Finance.Accounting.AccountStatement.md#movementtype) | string (7) | Movement Type. `Required` `Filter(multi eq)` 
| [Opening](Finance.Accounting.AccountStatement.md#opening) | decimal (38, 2) | Opening balance (debit balance is positive, credit - negative). `Required` 
| [OpeningBase](Finance.Accounting.AccountStatement.md#openingbase) | decimal (38, 2) | Opening balance in base currency (debit balance is positive, credit - negative). `Required` 
| [OpeningReporting](Finance.Accounting.AccountStatement.md#openingreporting) | decimal (38, 2) | Opening balance in reporting currency. `Required` 
| [ReleaseTime](Finance.Accounting.AccountStatement.md#releasetime) | datetime | Document Release Time. `Required` `Filter(ge;le)` 
| [ToDate](Finance.Accounting.AccountStatement.md#todate) | date | Period End Date - Should be filtered with exact date. `Required` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.AccountStatement.md#account) | [Accounts](Finance.Accounting.Accounts.md) | General Ledger Account. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id` `FilterableReference` |
| [CostCenter](Finance.Accounting.AccountStatement.md#costcenter) | [CostCenters](Finance.Accounting.CostCenters.md) | Cost Center. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Cost_Centers_Table.Cost_Center_Id` |
| [Currency](Finance.Accounting.AccountStatement.md#currency) | [Currencies](General.Currencies.Currencies.md) | Currency. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Currencies_Table.Currency_Id` |
| [EnterpriseCompany](Finance.Accounting.AccountStatement.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Enterprise Company. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_<br />Companies_Table.Enterprise_Company_Id` `FilterableReference` |
| [EnterpriseCompanyLocation](Finance.Accounting.AccountStatement.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) | Company Location / Branch. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cm_Company_Locations_Table.Company_Location_Id` `FilterableReference` |
| [ProfitCenter](Finance.Accounting.AccountStatement.md#profitcenter) | [ProfitCenters](Finance.Accounting.ProfitCenters.md) | Profit Center. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Profit_Centers_Table.Profit_Center_Id` |
| [VoucherLine](Finance.Accounting.AccountStatement.md#voucherline) | [AccountingVoucherLines](Finance.Accounting.AccountingVoucherLines.md) | Voucher Line reference. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Voucher_Lines_Table.Voucher_Line_Id` |


## Attribute Details

### Balance

Balance is running sum of (Opening + Debit - Credit) calculated for each row of group. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### BalanceBase

Calculated as Balance over Base currency. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### BalanceReporting

Calculated as Balance over Reporting currency. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Closing

Closing Balance(at the end of reporting period). `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ClosingBase

Closing Balance(in Base currency). `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ClosingReporting

Closing Balance(in Reporting currency). `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Credit

Credit. `Required`

_Type_: **decimal (18, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CreditBase

Credit Base. `Required`

_Type_: **decimal (18, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CreditReporting

Credit Reporting. `Required`

_Type_: **decimal (18, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Debit

Debit. `Required`

_Type_: **decimal (18, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DebitBase

Debit Base. `Required`

_Type_: **decimal (18, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DebitReporting

Debit Reporting. `Required`

_Type_: **decimal (18, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DocumentDate

Document Date. `Required` `Filter(ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### FromDate

Period Start Date - Should be filtered with exact date. `Required` `Filter(eq)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals**  
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

### MovementType

Movement Type. `Required` `Filter(multi eq)`

_Type_: **string (7)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **7**  
_Show in UI_: **ShownByDefault**  

### Opening

Opening balance (debit balance is positive, credit - negative). `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### OpeningBase

Opening balance in base currency (debit balance is positive, credit - negative). `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### OpeningReporting

Opening balance in reporting currency. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ReleaseTime

Document Release Time. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ToDate

Period End Date - Should be filtered with exact date. `Required` `Filter(eq)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Account

General Ledger Account. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id` `FilterableReference`

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

Enterprise Company. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_Companies_Table.Enterprise_Company_Id` `FilterableReference`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Enterprise_Companies_Table.Enterprise_Company_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompanyLocation

Company Location / Branch. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cm_Company_Locations_Table.Company_Location_Id` `FilterableReference`

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

### VoucherLine

Voucher Line reference. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Voucher_Lines_Table.Voucher_Line_Id`

_Type_: **[AccountingVoucherLines](Finance.Accounting.AccountingVoucherLines.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Voucher_Lines_Table.Voucher_Line_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Accounting_AccountStatement?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Accounting_AccountStatement?$top=10>

