---
uid: Finance.Accounting.AccountStatement
---
# Finance.Accounting.AccountStatement (View)


Provides a chronological breakdown of all accounting transactions for each general ledger account within a specified date range. For each account, the report shows the opening, total debits and credits, and the closing balance, followed by a detailed list of all associated accounting vouchers. From Date and To Date must be filtered using exact dates to define the reporting window precisely.

## General
Namespace: [Finance.Accounting](Finance.Accounting.md)  
Repository: Finance.Accounting.AccountStatement  
Introduced In Version: 25.1.3.31  
API access:  ReadWrite  

## Visualization
Display Format: {FromDate}: {ToDate}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Accounting.AccountStatement](Finance.Accounting.AccountStatement.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Balance](Finance.Accounting.AccountStatement.md#balance) | decimal (38, 2) | Balance is running sum of (Opening + Debit - Credit) calculated for each row of group.[Required] 
| [BalanceBase](Finance.Accounting.AccountStatement.md#balancebase) | decimal (38, 2) | Calculated as Balance over Base currency.[Required] 
| [BalanceReporting](Finance.Accounting.AccountStatement.md#balancereporting) | decimal (38, 2) | Calculated as Balance over Reporting currency.[Required] 
| [Closing](Finance.Accounting.AccountStatement.md#closing) | decimal (38, 2) | Closing Balance(at the end of reporting period)[Required] 
| [ClosingBase](Finance.Accounting.AccountStatement.md#closingbase) | decimal (38, 2) | Closing Balance(in Base currency)[Required] 
| [ClosingReporting](Finance.Accounting.AccountStatement.md#closingreporting) | decimal (38, 2) | Closing Balance(in Reporting currency)[Required] 
| [Credit](Finance.Accounting.AccountStatement.md#credit) | decimal (18, 2) | Credit[Required] 
| [CreditBase](Finance.Accounting.AccountStatement.md#creditbase) | decimal (18, 2) | Credit Base[Required] 
| [CreditReporting](Finance.Accounting.AccountStatement.md#creditreporting) | decimal (18, 2) | Credit Reporting[Required] 
| [Debit](Finance.Accounting.AccountStatement.md#debit) | decimal (18, 2) | Debit[Required] 
| [DebitBase](Finance.Accounting.AccountStatement.md#debitbase) | decimal (18, 2) | Debit Base[Required] 
| [DebitReporting](Finance.Accounting.AccountStatement.md#debitreporting) | decimal (18, 2) | Debit Reporting[Required] 
| [DocumentDate](Finance.Accounting.AccountStatement.md#documentdate) | date | Document Date[Required] [Filter(ge;le)] 
| [FromDate](Finance.Accounting.AccountStatement.md#fromdate) | date | Period Start Date - Should be filtered with exact date[Required] [Filter(eq)] 
| [ItemKey](Finance.Accounting.AccountStatement.md#itemkey) | string (64) | Item Key[Required] 
| [MovementType](Finance.Accounting.AccountStatement.md#movementtype) | string (7) | Movement Type[Required] [Filter(multi eq)] 
| [Opening](Finance.Accounting.AccountStatement.md#opening) | decimal (38, 2) | Opening balance (debit balance is positive, credit - negative)[Required] 
| [OpeningBase](Finance.Accounting.AccountStatement.md#openingbase) | decimal (38, 2) | Opening balance in base currency (debit balance is positive, credit - negative)[Required] 
| [OpeningReporting](Finance.Accounting.AccountStatement.md#openingreporting) | decimal (38, 2) | Opening balance in reporting currency[Required] 
| [ReleaseTime](Finance.Accounting.AccountStatement.md#releasetime) | datetime | Document Release Time[Required] [Filter(ge;le)] 
| [ToDate](Finance.Accounting.AccountStatement.md#todate) | date | Period End Date - Should be filtered with exact date[Required] [Filter(eq)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.AccountStatement.md#account) | [Accounts](Finance.Accounting.Accounts.md) | General Ledger Account |
| [CostCenter](Finance.Accounting.AccountStatement.md#costcenter) | [CostCenters](Finance.Accounting.CostCenters.md) | Cost Center |
| [Currency](Finance.Accounting.AccountStatement.md#currency) | [Currencies](General.Currencies.Currencies.md) | Currency |
| [EnterpriseCompany](Finance.Accounting.AccountStatement.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Enterprise Company |
| [EnterpriseCompanyLocation](Finance.Accounting.AccountStatement.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) | Company Location / Branch |
| [ProfitCenter](Finance.Accounting.AccountStatement.md#profitcenter) | [ProfitCenters](Finance.Accounting.ProfitCenters.md) | Profit Center |
| [VoucherLine](Finance.Accounting.AccountStatement.md#voucherline) | [AccountingVoucherLines](Finance.Accounting.AccountingVoucherLines.md) | Voucher Line reference |


## Attribute Details

### Balance

Balance is running sum of (Opening + Debit - Credit) calculated for each row of group.[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BalanceBase

Calculated as Balance over Base currency.[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BalanceReporting

Calculated as Balance over Reporting currency.[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Closing

Closing Balance(at the end of reporting period)[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingBase

Closing Balance(in Base currency)[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingReporting

Closing Balance(in Reporting currency)[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Credit

Credit[Required]

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreditBase

Credit Base[Required]

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreditReporting

Credit Reporting[Required]

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Debit

Debit[Required]

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DebitBase

Debit Base[Required]

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DebitReporting

Debit Reporting[Required]

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DocumentDate

Document Date[Required] [Filter(ge;le)]

Type: **date**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FromDate

Period Start Date - Should be filtered with exact date[Required] [Filter(eq)]

Type: **date**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ItemKey

Item Key[Required]

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### MovementType

Movement Type[Required] [Filter(multi eq)]

Type: **string (7)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **7**  
Show in UI: **ShownByDefault**  

### Opening

Opening balance (debit balance is positive, credit - negative)[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OpeningBase

Opening balance in base currency (debit balance is positive, credit - negative)[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OpeningReporting

Opening balance in reporting currency[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReleaseTime

Document Release Time[Required] [Filter(ge;le)]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ToDate

Period End Date - Should be filtered with exact date[Required] [Filter(eq)]

Type: **date**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### Account

General Ledger Account

Type: **[Accounts](Finance.Accounting.Accounts.md)**  
Category: **System**  
Inherited From: **Acc_Accounts_Table.Account_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### CostCenter

Cost Center

Type: **[CostCenters](Finance.Accounting.CostCenters.md)**  
Category: **System**  
Inherited From: **Acc_Cost_Centers_Table.Cost_Center_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Currency

Currency

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Inherited From: **Gen_Currencies_Table.Currency_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

Enterprise Company

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Inherited From: **Gen_Enterprise_Companies_Table.Enterprise_Company_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### EnterpriseCompanyLocation

Company Location / Branch

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md)**  
Category: **System**  
Inherited From: **Cm_Company_Locations_Table.Company_Location_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### ProfitCenter

Profit Center

Type: **[ProfitCenters](Finance.Accounting.ProfitCenters.md)**  
Category: **System**  
Inherited From: **Acc_Profit_Centers_Table.Profit_Center_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### VoucherLine

Voucher Line reference

Type: **[AccountingVoucherLines](Finance.Accounting.AccountingVoucherLines.md)**  
Category: **System**  
Inherited From: **Acc_Voucher_Lines_Table.Voucher_Line_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Finance_Accounting_AccountStatement

Domain API Entity Type: 
Finance_Accounting_AccountStatementEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Accounting_AccountStatement?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Accounting_AccountStatement?$top=10>

