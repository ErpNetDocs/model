---
uid: Finance.Accounting.TrialBalanceDetailed
---
# Finance.Accounting.TrialBalanceDetailed (View)


Shows debit and credit turnovers and balances per account, broken down by analytical dimensions, cost and profit centers. Designed for detailed analysis and managerial reporting.

## General
Namespace: [Finance.Accounting](Finance.Accounting.md)  
Repository: Finance.Accounting.TrialBalanceDetailed  
Introduced In Version: 25.1.3.22  
API access:  ReadWrite  

## Visualization
Display Format: {FromDate}: {ToDate}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Accounting.TrialBalanceDetailed](Finance.Accounting.TrialBalanceDetailed.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Closing](Finance.Accounting.TrialBalanceDetailed.md#closing) | decimal (38, 2) __nullable__ | Closing Balance (debit balance is positive, credit - negative) |
| [ClosingBase](Finance.Accounting.TrialBalanceDetailed.md#closingbase) | decimal (38, 2) __nullable__ | Closing balance in base currency (debit balance is positive, credit - negative) |
| [ClosingCredit](Finance.Accounting.TrialBalanceDetailed.md#closingcredit) | decimal (38, 2) __nullable__ | Closing balance when it is credit |
| [ClosingCreditBase](Finance.Accounting.TrialBalanceDetailed.md#closingcreditbase) | decimal (38, 2) __nullable__ | Closing balance in base currency when it is credit |
| [ClosingDebit](Finance.Accounting.TrialBalanceDetailed.md#closingdebit) | decimal (38, 2) __nullable__ | Closing balance when it is debit |
| [ClosingDebitBase](Finance.Accounting.TrialBalanceDetailed.md#closingdebitbase) | decimal (38, 2) __nullable__ | Closing balance in base currency when it is debit |
| [ClosingReporting](Finance.Accounting.TrialBalanceDetailed.md#closingreporting) | decimal (38, 2) __nullable__ | Closing balance in reporting currency |
| [Credit](Finance.Accounting.TrialBalanceDetailed.md#credit) | decimal (38, 2) __nullable__ | Credit |
| [CreditBase](Finance.Accounting.TrialBalanceDetailed.md#creditbase) | decimal (38, 2) __nullable__ | Credit Base |
| [CreditReporting](Finance.Accounting.TrialBalanceDetailed.md#creditreporting) | decimal (38, 2) __nullable__ | Credit Reporting |
| [Debit](Finance.Accounting.TrialBalanceDetailed.md#debit) | decimal (38, 2) __nullable__ | Debit |
| [DebitBase](Finance.Accounting.TrialBalanceDetailed.md#debitbase) | decimal (38, 2) __nullable__ | Debit Base |
| [DebitReporting](Finance.Accounting.TrialBalanceDetailed.md#debitreporting) | decimal (38, 2) __nullable__ | Debit Reporting |
| [FromDate](Finance.Accounting.TrialBalanceDetailed.md#fromdate) | date __nullable__ | Period Start Date - Should be filtered with exact date`Filter(eq)` |
| [ItemKey](Finance.Accounting.TrialBalanceDetailed.md#itemkey) | string (64) __nullable__ | Item Key`Filter(eq;like)` |
| [ItemKeyLevel1Code](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel1code) | string (40) __nullable__ | Item Key Level 1 Code`Filter(multi eq)` |
| [ItemKeyLevel1Name](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel1name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Item Key Level 1 Name`Filter(multi eq)` |
| [ItemKeyLevel2Code](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel2code) | string (40) __nullable__ | Item Key Level 2 Code`Filter(multi eq)` |
| [ItemKeyLevel2Name](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel2name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Item Key Level 2 Name`Filter(multi eq)` |
| [ItemKeyLevel3Code](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel3code) | string (40) __nullable__ | Item Key Level 3 Code`Filter(multi eq)` |
| [ItemKeyLevel3Name](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel3name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Item Key Level 3 Name`Filter(multi eq)` |
| [ItemKeyLevel4Code](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel4code) | string (40) __nullable__ | Item Key Level 4 Code`Filter(multi eq)` |
| [ItemKeyLevel4Name](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel4name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Item Key Level 4 Name`Filter(multi eq)` |
| [ItemKeyLevel5Code](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel5code) | string (40) __nullable__ | Item Key Level 5 Code`Filter(multi eq)` |
| [ItemKeyLevel5Name](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel5name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Item Key Level 5 Name`Filter(multi eq)` |
| [Opening](Finance.Accounting.TrialBalanceDetailed.md#opening) | decimal (38, 2) __nullable__ | Opening balance (debit balance is positive, credit - negative) |
| [OpeningBase](Finance.Accounting.TrialBalanceDetailed.md#openingbase) | decimal (38, 2) __nullable__ | Opening balance in base currency (debit balance is positive, credit - negative) |
| [OpeningCredit](Finance.Accounting.TrialBalanceDetailed.md#openingcredit) | decimal (38, 2) __nullable__ | Opening balance when it is credit |
| [OpeningCreditBase](Finance.Accounting.TrialBalanceDetailed.md#openingcreditbase) | decimal (38, 2) __nullable__ | Opening balance in base currency when it is credit |
| [OpeningDebit](Finance.Accounting.TrialBalanceDetailed.md#openingdebit) | decimal (38, 2) __nullable__ | Opening balance when it is debit |
| [OpeningDebitBase](Finance.Accounting.TrialBalanceDetailed.md#openingdebitbase) | decimal (38, 2) __nullable__ | Opening balance in base currency when it is debit |
| [OpeningReporting](Finance.Accounting.TrialBalanceDetailed.md#openingreporting) | decimal (38, 2) __nullable__ | Opening balance in reporting currency`Introduced in version 25.1.3.29` |
| [ToDate](Finance.Accounting.TrialBalanceDetailed.md#todate) | date __nullable__ | Period End Date - Should be filtered with exact date`Filter(eq)` |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.TrialBalanceDetailed.md#account) | [Accounts](Finance.Accounting.Accounts.md) | General Ledger Account |
| [CostCenter](Finance.Accounting.TrialBalanceDetailed.md#costcenter) | [CostCenters](Finance.Accounting.CostCenters.md) (nullable) | Cost Center |
| [Currency](Finance.Accounting.TrialBalanceDetailed.md#currency) | [Currencies](General.Currencies.Currencies.md) | Currency |
| [EnterpriseCompany](Finance.Accounting.TrialBalanceDetailed.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Enterprise Company |
| [ExampleVoucherLine](Finance.Accounting.TrialBalanceDetailed.md#examplevoucherline) | [AccountingVoucherLines](Finance.Accounting.AccountingVoucherLines.md) (nullable) | This is one (any) of the voucher lines grouped for the current Item Key (it could be from the opening balances or transactions) - it will be used to display the user-defined characteristics of this line. |
| [Level1AccountGroup](Finance.Accounting.TrialBalanceDetailed.md#level1accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) (nullable) | Level 1 Account Group |
| [Level1AccountProperty](Finance.Accounting.TrialBalanceDetailed.md#level1accountproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | Level 1 Account Property |
| [Level2AccountGroup](Finance.Accounting.TrialBalanceDetailed.md#level2accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) (nullable) | Level 2 Account Group |
| [Level2AccountProperty](Finance.Accounting.TrialBalanceDetailed.md#level2accountproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | Level 2 Account Property |
| [Level3AccountGroup](Finance.Accounting.TrialBalanceDetailed.md#level3accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) (nullable) | Level 3 Account Group |
| [Level3AccountProperty](Finance.Accounting.TrialBalanceDetailed.md#level3accountproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | Level 3 Account Property |
| [Level4AccountGroup](Finance.Accounting.TrialBalanceDetailed.md#level4accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) (nullable) | Level 4 Account Group |
| [Level4AccountProperty](Finance.Accounting.TrialBalanceDetailed.md#level4accountproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | Level 4 Account Property |
| [Level5AccountGroup](Finance.Accounting.TrialBalanceDetailed.md#level5accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) (nullable) | Level 5 Account Group |
| [Level5AccountProperty](Finance.Accounting.TrialBalanceDetailed.md#level5accountproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | Level 5 Account Property |
| [Level6AccountGroup](Finance.Accounting.TrialBalanceDetailed.md#level6accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) (nullable) | Level 6 Account Group |
| [ProfitCenter](Finance.Accounting.TrialBalanceDetailed.md#profitcenter) | [ProfitCenters](Finance.Accounting.ProfitCenters.md) (nullable) | Profit Center |


## Attribute Details

### Closing

Closing Balance (debit balance is positive, credit - negative)

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingBase

Closing balance in base currency (debit balance is positive, credit - negative)

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingCredit

Closing balance when it is credit

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingCreditBase

Closing balance in base currency when it is credit

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingDebit

Closing balance when it is debit

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingDebitBase

Closing balance in base currency when it is debit

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ClosingReporting

Closing balance in reporting currency

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Credit

Credit

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreditBase

Credit Base

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreditReporting

Credit Reporting

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Debit

Debit

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DebitBase

Debit Base

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DebitReporting

Debit Reporting

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FromDate

Period Start Date - Should be filtered with exact date`Filter(eq)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ItemKey

Item Key`Filter(eq;like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### ItemKeyLevel1Code

Item Key Level 1 Code`Filter(multi eq)`

Type: **string (40) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **40**  
Show in UI: **ShownByDefault**  

### ItemKeyLevel1Name

Item Key Level 1 Name`Filter(multi eq)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ItemKeyLevel2Code

Item Key Level 2 Code`Filter(multi eq)`

Type: **string (40) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **40**  
Show in UI: **ShownByDefault**  

### ItemKeyLevel2Name

Item Key Level 2 Name`Filter(multi eq)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ItemKeyLevel3Code

Item Key Level 3 Code`Filter(multi eq)`

Type: **string (40) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **40**  
Show in UI: **ShownByDefault**  

### ItemKeyLevel3Name

Item Key Level 3 Name`Filter(multi eq)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ItemKeyLevel4Code

Item Key Level 4 Code`Filter(multi eq)`

Type: **string (40) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **40**  
Show in UI: **ShownByDefault**  

### ItemKeyLevel4Name

Item Key Level 4 Name`Filter(multi eq)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ItemKeyLevel5Code

Item Key Level 5 Code`Filter(multi eq)`

Type: **string (40) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **40**  
Show in UI: **ShownByDefault**  

### ItemKeyLevel5Name

Item Key Level 5 Name`Filter(multi eq)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Opening

Opening balance (debit balance is positive, credit - negative)

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OpeningBase

Opening balance in base currency (debit balance is positive, credit - negative)

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OpeningCredit

Opening balance when it is credit

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OpeningCreditBase

Opening balance in base currency when it is credit

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OpeningDebit

Opening balance when it is debit

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OpeningDebitBase

Opening balance in base currency when it is debit

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OpeningReporting

Opening balance in reporting currency`Introduced in version 25.1.3.29`

Type: **decimal (38, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ToDate

Period End Date - Should be filtered with exact date`Filter(eq)`

Type: **date __nullable__**  
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

### CostCenter

Cost Center

Type: **[CostCenters](Finance.Accounting.CostCenters.md) (nullable)**  
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
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### ExampleVoucherLine

This is one (any) of the voucher lines grouped for the current Item Key (it could be from the opening balances or transactions) - it will be used to display the user-defined characteristics of this line.

Type: **[AccountingVoucherLines](Finance.Accounting.AccountingVoucherLines.md) (nullable)**  
Category: **System**  
Inherited From: **Acc_Voucher_Lines_Table.Voucher_Line_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level1AccountGroup

Level 1 Account Group

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md) (nullable)**  
Category: **System**  
Inherited From: **Acc_Account_Groups_Table.Account_Group_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level1AccountProperty

Level 1 Account Property

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
Category: **System**  
Inherited From: **Gen_Properties_Table.Property_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level2AccountGroup

Level 2 Account Group

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md) (nullable)**  
Category: **System**  
Inherited From: **Acc_Account_Groups_Table.Account_Group_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level2AccountProperty

Level 2 Account Property

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
Category: **System**  
Inherited From: **Gen_Properties_Table.Property_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level3AccountGroup

Level 3 Account Group

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md) (nullable)**  
Category: **System**  
Inherited From: **Acc_Account_Groups_Table.Account_Group_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level3AccountProperty

Level 3 Account Property

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
Category: **System**  
Inherited From: **Gen_Properties_Table.Property_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level4AccountGroup

Level 4 Account Group

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md) (nullable)**  
Category: **System**  
Inherited From: **Acc_Account_Groups_Table.Account_Group_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level4AccountProperty

Level 4 Account Property

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
Category: **System**  
Inherited From: **Gen_Properties_Table.Property_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level5AccountGroup

Level 5 Account Group

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md) (nullable)**  
Category: **System**  
Inherited From: **Acc_Account_Groups_Table.Account_Group_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level5AccountProperty

Level 5 Account Property

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
Category: **System**  
Inherited From: **Gen_Properties_Table.Property_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Level6AccountGroup

Level 6 Account Group

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md) (nullable)**  
Category: **System**  
Inherited From: **Acc_Account_Groups_Table.Account_Group_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### ProfitCenter

Profit Center

Type: **[ProfitCenters](Finance.Accounting.ProfitCenters.md) (nullable)**  
Category: **System**  
Inherited From: **Acc_Profit_Centers_Table.Profit_Center_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Finance_Accounting_TrialBalanceDetailed

Domain API Entity Type: 
Finance_Accounting_TrialBalanceDetailedEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Accounting_TrialBalanceDetailed?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Accounting_TrialBalanceDetailed?$top=10>

