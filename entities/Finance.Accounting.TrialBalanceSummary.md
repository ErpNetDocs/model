---
uid: Finance.Accounting.TrialBalanceSummary
---
# Finance.Accounting.TrialBalanceSummary (View)


Displays aggregated debit and credit turnovers and balances by account for a selected period. Ideal for general financial overview and period-end reconciliation.

## General
Namespace: [Finance.Accounting](Finance.Accounting.md)  
Repository: Finance.Accounting.TrialBalanceSummary  
Introduced In Version: 25.1.3.28  
API access:  ReadWrite  

## Visualization
Display Format: {FromDate}: {ToDate}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Accounting.TrialBalanceSummary](Finance.Accounting.TrialBalanceSummary.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Closing](Finance.Accounting.TrialBalanceSummary.md#closing) | decimal (38, 2) | Closing Balance (debit balance is positive, credit - negative)[Required] 
| [ClosingBase](Finance.Accounting.TrialBalanceSummary.md#closingbase) | decimal (38, 2) | Closing balance in base currency (debit balance is positive, credit - negative)[Required] 
| [ClosingCredit](Finance.Accounting.TrialBalanceSummary.md#closingcredit) | decimal (38, 2) | Closing balance when it is credit[Required] 
| [ClosingCreditBase](Finance.Accounting.TrialBalanceSummary.md#closingcreditbase) | decimal (38, 2) | Closing balance in base currency when it is credit[Required] 
| [ClosingDebit](Finance.Accounting.TrialBalanceSummary.md#closingdebit) | decimal (38, 2) | Closing balance when it is debit[Required] 
| [ClosingDebitBase](Finance.Accounting.TrialBalanceSummary.md#closingdebitbase) | decimal (38, 2) | Closing balance in base currency when it is debit[Required] 
| [ClosingReporting](Finance.Accounting.TrialBalanceSummary.md#closingreporting) | decimal (38, 2) | Closing balance in reporting currency[Required] 
| [Credits](Finance.Accounting.TrialBalanceSummary.md#credits) | decimal (38, 2) | Total credits for the period[Required] 
| [CreditsBase](Finance.Accounting.TrialBalanceSummary.md#creditsbase) | decimal (38, 2) | Total credits (Base Currency)[Required] 
| [CreditsReporting](Finance.Accounting.TrialBalanceSummary.md#creditsreporting) | decimal (38, 2) | Total credits (Reporting Currency)[Required] 
| [Debits](Finance.Accounting.TrialBalanceSummary.md#debits) | decimal (38, 2) | Total debits for the period[Required] 
| [DebitsBase](Finance.Accounting.TrialBalanceSummary.md#debitsbase) | decimal (38, 2) | Total debits (Base Currency)[Required] 
| [DebitsReporting](Finance.Accounting.TrialBalanceSummary.md#debitsreporting) | decimal (38, 2) | Total debits (Reporting Currency)[Required] 
| [FromDate](Finance.Accounting.TrialBalanceSummary.md#fromdate) | date | Period Start Date - Should be filtered with exact date[Required] [Filter(eq)] 
| [Opening](Finance.Accounting.TrialBalanceSummary.md#opening) | decimal (38, 2) | Opening balance (debit balance is positive, credit - negative)[Required] 
| [OpeningBase](Finance.Accounting.TrialBalanceSummary.md#openingbase) | decimal (38, 2) | Opening balance in base currency (debit balance is positive, credit - negative)[Required] 
| [OpeningCredit](Finance.Accounting.TrialBalanceSummary.md#openingcredit) | decimal (38, 2) | Opening balance when it is credit[Required] 
| [OpeningCreditBase](Finance.Accounting.TrialBalanceSummary.md#openingcreditbase) | decimal (38, 2) | Opening balance in base currency when it is credit[Required] 
| [OpeningDebit](Finance.Accounting.TrialBalanceSummary.md#openingdebit) | decimal (38, 2) | Opening balance when it is debit[Required] 
| [OpeningDebitBase](Finance.Accounting.TrialBalanceSummary.md#openingdebitbase) | decimal (38, 2) | Opening balance in base currency when it is debit[Required] 
| [OpeningReporting](Finance.Accounting.TrialBalanceSummary.md#openingreporting) | decimal (38, 2) | Opening Reporting[Required] 
| [ToDate](Finance.Accounting.TrialBalanceSummary.md#todate) | date | Period End Date - Should be filtered with exact date[Required] [Filter(eq)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.TrialBalanceSummary.md#account) | [Accounts](Finance.Accounting.Accounts.md) | General Ledger Account |
| [Currency](Finance.Accounting.TrialBalanceSummary.md#currency) | [Currencies](General.Currencies.Currencies.md) | Currency |
| [EnterpriseCompany](Finance.Accounting.TrialBalanceSummary.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Enterprise Company |
| [EnterpriseCompanyLocation](Finance.Accounting.TrialBalanceSummary.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) | Enterprise Company Location |
| [Level1AccountGroup](Finance.Accounting.TrialBalanceSummary.md#level1accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 1 Account Group |
| [Level2AccountGroup](Finance.Accounting.TrialBalanceSummary.md#level2accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 2 Account Group |
| [Level3AccountGroup](Finance.Accounting.TrialBalanceSummary.md#level3accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 3 Account Group |
| [Level4AccountGroup](Finance.Accounting.TrialBalanceSummary.md#level4accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 4 Account Group |
| [Level5AccountGroup](Finance.Accounting.TrialBalanceSummary.md#level5accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 5 Account Group |
| [Level6AccountGroup](Finance.Accounting.TrialBalanceSummary.md#level6accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 6 Account Group |


## Attribute Details

### Closing

Closing Balance (debit balance is positive, credit - negative)[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingBase

Closing balance in base currency (debit balance is positive, credit - negative)[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingCredit

Closing balance when it is credit[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingCreditBase

Closing balance in base currency when it is credit[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingDebit

Closing balance when it is debit[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingDebitBase

Closing balance in base currency when it is debit[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingReporting

Closing balance in reporting currency[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Credits

Total credits for the period[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreditsBase

Total credits (Base Currency)[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreditsReporting

Total credits (Reporting Currency)[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Debits

Total debits for the period[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DebitsBase

Total debits (Base Currency)[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DebitsReporting

Total debits (Reporting Currency)[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FromDate

Period Start Date - Should be filtered with exact date[Required] [Filter(eq)]

Type: **date**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
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

### OpeningCredit

Opening balance when it is credit[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OpeningCreditBase

Opening balance in base currency when it is credit[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OpeningDebit

Opening balance when it is debit[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OpeningDebitBase

Opening balance in base currency when it is debit[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OpeningReporting

Opening Reporting[Required]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
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
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### EnterpriseCompanyLocation

Enterprise Company Location

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md)**  
Category: **System**  
Inherited From: **Cm_Company_Locations_Table.Company_Location_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level1AccountGroup

Level 1 Account Group

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
Category: **System**  
Inherited From: **Acc_Account_Groups_Table.Account_Group_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level2AccountGroup

Level 2 Account Group

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
Category: **System**  
Inherited From: **Acc_Account_Groups_Table.Account_Group_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level3AccountGroup

Level 3 Account Group

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
Category: **System**  
Inherited From: **Acc_Account_Groups_Table.Account_Group_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level4AccountGroup

Level 4 Account Group

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
Category: **System**  
Inherited From: **Acc_Account_Groups_Table.Account_Group_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level5AccountGroup

Level 5 Account Group

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
Category: **System**  
Inherited From: **Acc_Account_Groups_Table.Account_Group_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level6AccountGroup

Level 6 Account Group

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
Category: **System**  
Inherited From: **Acc_Account_Groups_Table.Account_Group_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Finance_Accounting_TrialBalanceSummary

Domain API Entity Type: 
Finance_Accounting_TrialBalanceSummaryEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Accounting_TrialBalanceSummary?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Accounting_TrialBalanceSummary?$top=10>

