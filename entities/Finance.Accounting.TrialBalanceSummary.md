---
uid: Finance.Accounting.TrialBalanceSummary
---
# Finance.Accounting.TrialBalanceSummary View

**Namespace:** [Finance.Accounting](Finance.Accounting.md)  

Displays aggregated debit and credit turnovers and balances by account for a selected period. Ideal for general financial overview and period-end reconciliation. Entity: Acc_Trial_Balance_Summary (Introduced in version 25.1.3.28)

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
* [Finance.Accounting.TrialBalanceSummary](Finance.Accounting.TrialBalanceSummary.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Closing](Finance.Accounting.TrialBalanceSummary.md#closing) | decimal (38, 2) | Closing Balance (debit balance is positive, credit - negative). `Required` 
| [ClosingBase](Finance.Accounting.TrialBalanceSummary.md#closingbase) | decimal (38, 2) | Closing balance in base currency (debit balance is positive, credit - negative). `Required` 
| [ClosingCredit](Finance.Accounting.TrialBalanceSummary.md#closingcredit) | decimal (38, 2) | Closing balance when it is credit. `Required` 
| [ClosingCreditBase](Finance.Accounting.TrialBalanceSummary.md#closingcreditbase) | decimal (38, 2) | Closing balance in base currency when it is credit. `Required` 
| [ClosingDebit](Finance.Accounting.TrialBalanceSummary.md#closingdebit) | decimal (38, 2) | Closing balance when it is debit. `Required` 
| [ClosingDebitBase](Finance.Accounting.TrialBalanceSummary.md#closingdebitbase) | decimal (38, 2) | Closing balance in base currency when it is debit. `Required` 
| [ClosingReporting](Finance.Accounting.TrialBalanceSummary.md#closingreporting) | decimal (38, 2) | Closing balance in reporting currency. `Required` 
| [Credits](Finance.Accounting.TrialBalanceSummary.md#credits) | decimal (38, 2) | Total credits for the period. `Required` 
| [CreditsBase](Finance.Accounting.TrialBalanceSummary.md#creditsbase) | decimal (38, 2) | Total credits (Base Currency). `Required` 
| [CreditsReporting](Finance.Accounting.TrialBalanceSummary.md#creditsreporting) | decimal (38, 2) | Total credits (Reporting Currency). `Required` 
| [Debits](Finance.Accounting.TrialBalanceSummary.md#debits) | decimal (38, 2) | Total debits for the period. `Required` 
| [DebitsBase](Finance.Accounting.TrialBalanceSummary.md#debitsbase) | decimal (38, 2) | Total debits (Base Currency). `Required` 
| [DebitsReporting](Finance.Accounting.TrialBalanceSummary.md#debitsreporting) | decimal (38, 2) | Total debits (Reporting Currency). `Required` 
| [FromDate](Finance.Accounting.TrialBalanceSummary.md#fromdate) | date | Period Start Date - Should be filtered with exact date. `Required` `Filter(eq)` 
| [Opening](Finance.Accounting.TrialBalanceSummary.md#opening) | decimal (38, 2) | Opening balance (debit balance is positive, credit - negative). `Required` 
| [OpeningBase](Finance.Accounting.TrialBalanceSummary.md#openingbase) | decimal (38, 2) | Opening balance in base currency (debit balance is positive, credit - negative). `Required` 
| [OpeningCredit](Finance.Accounting.TrialBalanceSummary.md#openingcredit) | decimal (38, 2) | Opening balance when it is credit. `Required` 
| [OpeningCreditBase](Finance.Accounting.TrialBalanceSummary.md#openingcreditbase) | decimal (38, 2) | Opening balance in base currency when it is credit. `Required` 
| [OpeningDebit](Finance.Accounting.TrialBalanceSummary.md#openingdebit) | decimal (38, 2) | Opening balance when it is debit. `Required` 
| [OpeningDebitBase](Finance.Accounting.TrialBalanceSummary.md#openingdebitbase) | decimal (38, 2) | Opening balance in base currency when it is debit. `Required` 
| [OpeningRepoirting](Finance.Accounting.TrialBalanceSummary.md#openingrepoirting) | decimal (38, 2) | Opening balance in reporting currency. `Required` 
| [ToDate](Finance.Accounting.TrialBalanceSummary.md#todate) | date | Period End Date - Should be filtered with exact date. `Required` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.TrialBalanceSummary.md#account) | [Accounts](Finance.Accounting.Accounts.md) | General Ledger Account. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id` |
| [Currency](Finance.Accounting.TrialBalanceSummary.md#currency) | [Currencies](General.Currencies.Currencies.md) | Currency. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Currencies_Table.Currency_Id` |
| [EnterpriseCompany](Finance.Accounting.TrialBalanceSummary.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Enterprise Company. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_<br />Companies_Table.Enterprise_Company_Id` |
| [EnterpriseCompanyLocation](Finance.Accounting.TrialBalanceSummary.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) | Enterprise Company Location. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cm_Company_Locations_Table.Company_Location_Id` |
| [Level1AccountGroup](Finance.Accounting.TrialBalanceSummary.md#level1accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 1 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` |
| [Level2AccountGroup](Finance.Accounting.TrialBalanceSummary.md#level2accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 2 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` |
| [Level3AccountGroup](Finance.Accounting.TrialBalanceSummary.md#level3accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 3 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` |
| [Level4AccountGroup](Finance.Accounting.TrialBalanceSummary.md#level4accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 4 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` |
| [Level5AccountGroup](Finance.Accounting.TrialBalanceSummary.md#level5accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 5 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` |
| [Level6AccountGroup](Finance.Accounting.TrialBalanceSummary.md#level6accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 6 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` |


## Attribute Details

### Closing

Closing Balance (debit balance is positive, credit - negative). `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ClosingBase

Closing balance in base currency (debit balance is positive, credit - negative). `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ClosingCredit

Closing balance when it is credit. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ClosingCreditBase

Closing balance in base currency when it is credit. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ClosingDebit

Closing balance when it is debit. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ClosingDebitBase

Closing balance in base currency when it is debit. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ClosingReporting

Closing balance in reporting currency. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Credits

Total credits for the period. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CreditsBase

Total credits (Base Currency). `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CreditsReporting

Total credits (Reporting Currency). `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Debits

Total debits for the period. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DebitsBase

Total debits (Base Currency). `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DebitsReporting

Total debits (Reporting Currency). `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### FromDate

Period Start Date - Should be filtered with exact date. `Required` `Filter(eq)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
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

### OpeningCredit

Opening balance when it is credit. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### OpeningCreditBase

Opening balance in base currency when it is credit. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### OpeningDebit

Opening balance when it is debit. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### OpeningDebitBase

Opening balance in base currency when it is debit. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### OpeningRepoirting

Opening balance in reporting currency. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
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

General Ledger Account. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id`

_Type_: **[Accounts](Finance.Accounting.Accounts.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Accounts_Table.Account_Id**  
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

Enterprise Company. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_Companies_Table.Enterprise_Company_Id`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Enterprise_Companies_Table.Enterprise_Company_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompanyLocation

Enterprise Company Location. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cm_Company_Locations_Table.Company_Location_Id`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md)**  
_Category_: **System**  
_Inherited From_: **Cm_Company_Locations_Table.Company_Location_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level1AccountGroup

Level 1 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Account_Groups_Table.Account_Group_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level2AccountGroup

Level 2 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Account_Groups_Table.Account_Group_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level3AccountGroup

Level 3 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Account_Groups_Table.Account_Group_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level4AccountGroup

Level 4 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Account_Groups_Table.Account_Group_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level5AccountGroup

Level 5 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Account_Groups_Table.Account_Group_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level6AccountGroup

Level 6 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Account_Groups_Table.Account_Group_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Accounting_TrialBalanceSummary?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Accounting_TrialBalanceSummary?$top=10>

