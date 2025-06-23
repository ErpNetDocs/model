---
uid: Finance.Accounting.TrialBalanceDetailed
---
# Finance.Accounting.TrialBalanceDetailed View

**Namespace:** [Finance.Accounting](Finance.Accounting.md)  

Shows debit and credit turnovers and balances per account, broken down by analytical dimensions, cost and profit centers. Designed for detailed analysis and managerial reporting. Entity: Acc_Trial_Balance_Detailed (Introduced in version 25.1.3.22)

## Default Visualization
Default Display Text Format:  
_{FromDate}: {ToDate}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Accounting.TrialBalanceDetailed](Finance.Accounting.TrialBalanceDetailed.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Closing](Finance.Accounting.TrialBalanceDetailed.md#closing) | decimal (38, 2) | Closing Balance (debit balance is positive, credit - negative). `Required` 
| [ClosingBase](Finance.Accounting.TrialBalanceDetailed.md#closingbase) | decimal (38, 2) | Closing balance in base currency (debit balance is positive, credit - negative). `Required` 
| [ClosingCredit](Finance.Accounting.TrialBalanceDetailed.md#closingcredit) | decimal (38, 2) | Closing balance when it is credit. `Required` 
| [ClosingCreditBase](Finance.Accounting.TrialBalanceDetailed.md#closingcreditbase) | decimal (38, 2) | Closing balance in base currency when it is credit. `Required` 
| [ClosingDebit](Finance.Accounting.TrialBalanceDetailed.md#closingdebit) | decimal (38, 2) | Closing balance when it is debit. `Required` 
| [ClosingDebitBase](Finance.Accounting.TrialBalanceDetailed.md#closingdebitbase) | decimal (38, 2) | Closing balance in base currency when it is debit. `Required` 
| [ClosingReporting](Finance.Accounting.TrialBalanceDetailed.md#closingreporting) | decimal (38, 2) | Closing balance in reporting currency. `Required` 
| [Credit](Finance.Accounting.TrialBalanceDetailed.md#credit) | decimal (38, 2) | Credit. `Required` 
| [CreditBase](Finance.Accounting.TrialBalanceDetailed.md#creditbase) | decimal (38, 2) | Credit Base. `Required` 
| [CreditReporting](Finance.Accounting.TrialBalanceDetailed.md#creditreporting) | decimal (38, 2) | Credit Reporting. `Required` 
| [Debit](Finance.Accounting.TrialBalanceDetailed.md#debit) | decimal (38, 2) | Debit. `Required` 
| [DebitBase](Finance.Accounting.TrialBalanceDetailed.md#debitbase) | decimal (38, 2) | Debit Base. `Required` 
| [DebitReporting](Finance.Accounting.TrialBalanceDetailed.md#debitreporting) | decimal (38, 2) | Debit Reporting. `Required` 
| [FromDate](Finance.Accounting.TrialBalanceDetailed.md#fromdate) | date | Period Start Date - Should be filtered with exact date. `Required` `Filter(eq)` 
| [ItemKey](Finance.Accounting.TrialBalanceDetailed.md#itemkey) | string (64) | Item Key. `Required` `Filter(eq;like)` 
| [ItemKeyLevel1Code](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel1code) | string (40) | Item Key Level 1 Code. `Required` 
| [ItemKeyLevel1Name](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel1name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Item Key Level 1 Name. `Required` 
| [ItemKeyLevel2Code](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel2code) | string (40) | Item Key Level 2 Code. `Required` 
| [ItemKeyLevel2Name](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel2name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Item Key Level 2 Name. `Required` 
| [ItemKeyLevel3Code](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel3code) | string (40) | Item Key Level 3 Code. `Required` 
| [ItemKeyLevel3Name](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel3name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Item Key Level 3 Name. `Required` 
| [ItemKeyLevel4Code](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel4code) | string (40) | Item Key Level 4 Code. `Required` 
| [ItemKeyLevel4Name](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel4name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Item Key Level 4 Name. `Required` 
| [ItemKeyLevel5Code](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel5code) | string (40) | Item Key Level 5 Code. `Required` 
| [ItemKeyLevel5Name](Finance.Accounting.TrialBalanceDetailed.md#itemkeylevel5name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Item Key Level 5 Name. `Required` 
| [Opening](Finance.Accounting.TrialBalanceDetailed.md#opening) | decimal (38, 2) | Opening balance (debit balance is positive, credit - negative). `Required` 
| [OpeningBase](Finance.Accounting.TrialBalanceDetailed.md#openingbase) | decimal (38, 2) | Opening balance in base currency (debit balance is positive, credit - negative). `Required` 
| [OpeningCredit](Finance.Accounting.TrialBalanceDetailed.md#openingcredit) | decimal (38, 2) | Opening balance when it is credit. `Required` 
| [OpeningCreditBase](Finance.Accounting.TrialBalanceDetailed.md#openingcreditbase) | decimal (38, 2) | Opening balance in base currency when it is credit. `Required` 
| [OpeningDebit](Finance.Accounting.TrialBalanceDetailed.md#openingdebit) | decimal (38, 2) | Opening balance when it is debit. `Required` 
| [OpeningDebitBase](Finance.Accounting.TrialBalanceDetailed.md#openingdebitbase) | decimal (38, 2) | Opening balance in base currency when it is debit. `Required` 
| [OpeningReporting](Finance.Accounting.TrialBalanceDetailed.md#openingreporting) | decimal (38, 2) | Opening balance in reporting currency. `Required` `Introduced in version 25.1.3.29` 
| [ToDate](Finance.Accounting.TrialBalanceDetailed.md#todate) | date | Period End Date - Should be filtered with exact date. `Required` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.TrialBalanceDetailed.md#account) | [Accounts](Finance.Accounting.Accounts.md) | General Ledger Account. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id` `Introduced in version 25.1.3.28` |
| [CostCenter](Finance.Accounting.TrialBalanceDetailed.md#costcenter) | [CostCenters](Finance.Accounting.CostCenters.md) | Cost Center. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Cost_Centers_Table.Cost_Center_Id` `Introduced in version 25.1.3.28` |
| [Currency](Finance.Accounting.TrialBalanceDetailed.md#currency) | [Currencies](General.Currencies.Currencies.md) | Currency. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Currencies_Table.Currency_Id` `Introduced in version 25.1.3.28` |
| [EnterpriseCompany](Finance.Accounting.TrialBalanceDetailed.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Enterprise Company. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_<br />Companies_Table.Enterprise_Company_Id` `Introduced in version 25.1.3.28` |
| [EnterpriseCompanyLocation](Finance.Accounting.TrialBalanceDetailed.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) | Company Location / Branch. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cm_Company_Locations_Table.Company_Location_Id` `Introduced in version 25.1.3.28` |
| [ExampleVoucherLine](Finance.Accounting.TrialBalanceDetailed.md#examplevoucherline) | [AccountingVoucherLines](Finance.Accounting.AccountingVoucherLines.md) | This is one (any) of the voucher lines grouped for the current Item Key (it could be from the opening balances or transactions) - it will be used to display the user-defined characteristics of this line. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Voucher_Lines_Table.Voucher_Line_Id` `Introduced in version 25.1.3.28` |
| [Level1AccountGroup](Finance.Accounting.TrialBalanceDetailed.md#level1accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 1 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` `Introduced in version 25.1.3.28` |
| [Level1AccountProperty](Finance.Accounting.TrialBalanceDetailed.md#level1accountproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) | Level 1 Account Property. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Properties_Table.Property_Id` `Introduced in version 25.1.3.28` |
| [Level2AccountGroup](Finance.Accounting.TrialBalanceDetailed.md#level2accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 2 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` `Introduced in version 25.1.3.28` |
| [Level2AccountProperty](Finance.Accounting.TrialBalanceDetailed.md#level2accountproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) | Level 2 Account Property. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Properties_Table.Property_Id` `Introduced in version 25.1.3.28` |
| [Level3AccountGroup](Finance.Accounting.TrialBalanceDetailed.md#level3accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 3 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` `Introduced in version 25.1.3.28` |
| [Level3AccountProperty](Finance.Accounting.TrialBalanceDetailed.md#level3accountproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) | Level 3 Account Property. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Properties_Table.Property_Id` `Introduced in version 25.1.3.28` |
| [Level4AccountGroup](Finance.Accounting.TrialBalanceDetailed.md#level4accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 4 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` `Introduced in version 25.1.3.28` |
| [Level4AccountProperty](Finance.Accounting.TrialBalanceDetailed.md#level4accountproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) | Level 4 Account Property. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Properties_Table.Property_Id` `Introduced in version 25.1.3.28` |
| [Level5AccountGroup](Finance.Accounting.TrialBalanceDetailed.md#level5accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 5 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` `Introduced in version 25.1.3.28` |
| [Level5AccountProperty](Finance.Accounting.TrialBalanceDetailed.md#level5accountproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) | Level 5 Account Property. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Properties_Table.Property_Id` `Introduced in version 25.1.3.28` |
| [Level6AccountGroup](Finance.Accounting.TrialBalanceDetailed.md#level6accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | Level 6 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` `Introduced in version 25.1.3.28` |
| [ProfitCenter](Finance.Accounting.TrialBalanceDetailed.md#profitcenter) | [ProfitCenters](Finance.Accounting.ProfitCenters.md) | Profit Center. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Profit_Centers_Table.Profit_Center_Id` `Introduced in version 25.1.3.28` |


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

### Credit

Credit. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CreditBase

Credit Base. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CreditReporting

Credit Reporting. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Debit

Debit. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DebitBase

Debit Base. `Required`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DebitReporting

Debit Reporting. `Required`

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

### ItemKey

Item Key. `Required` `Filter(eq;like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### ItemKeyLevel1Code

Item Key Level 1 Code. `Required`

_Type_: **string (40)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **40**  
_Show in UI_: **ShownByDefault**  

### ItemKeyLevel1Name

Item Key Level 1 Name. `Required`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ItemKeyLevel2Code

Item Key Level 2 Code. `Required`

_Type_: **string (40)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **40**  
_Show in UI_: **ShownByDefault**  

### ItemKeyLevel2Name

Item Key Level 2 Name. `Required`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ItemKeyLevel3Code

Item Key Level 3 Code. `Required`

_Type_: **string (40)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **40**  
_Show in UI_: **ShownByDefault**  

### ItemKeyLevel3Name

Item Key Level 3 Name. `Required`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ItemKeyLevel4Code

Item Key Level 4 Code. `Required`

_Type_: **string (40)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **40**  
_Show in UI_: **ShownByDefault**  

### ItemKeyLevel4Name

Item Key Level 4 Name. `Required`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ItemKeyLevel5Code

Item Key Level 5 Code. `Required`

_Type_: **string (40)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **40**  
_Show in UI_: **ShownByDefault**  

### ItemKeyLevel5Name

Item Key Level 5 Name. `Required`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
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

### OpeningReporting

Opening balance in reporting currency. `Required` `Introduced in version 25.1.3.29`

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

General Ledger Account. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Accounts_Table.Account_Id` `Introduced in version 25.1.3.28`

_Type_: **[Accounts](Finance.Accounting.Accounts.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Accounts_Table.Account_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### CostCenter

Cost Center. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Cost_Centers_Table.Cost_Center_Id` `Introduced in version 25.1.3.28`

_Type_: **[CostCenters](Finance.Accounting.CostCenters.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Cost_Centers_Table.Cost_Center_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Currency

Currency. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Currencies_Table.Currency_Id` `Introduced in version 25.1.3.28`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Currencies_Table.Currency_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

Enterprise Company. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Enterprise_Companies_Table.Enterprise_Company_Id` `Introduced in version 25.1.3.28`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Enterprise_Companies_Table.Enterprise_Company_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompanyLocation

Company Location / Branch. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cm_Company_Locations_Table.Company_Location_Id` `Introduced in version 25.1.3.28`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md)**  
_Category_: **System**  
_Inherited From_: **Cm_Company_Locations_Table.Company_Location_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### ExampleVoucherLine

This is one (any) of the voucher lines grouped for the current Item Key (it could be from the opening balances or transactions) - it will be used to display the user-defined characteristics of this line. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Voucher_Lines_Table.Voucher_Line_Id` `Introduced in version 25.1.3.28`

_Type_: **[AccountingVoucherLines](Finance.Accounting.AccountingVoucherLines.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Voucher_Lines_Table.Voucher_Line_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level1AccountGroup

Level 1 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` `Introduced in version 25.1.3.28`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Account_Groups_Table.Account_Group_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level1AccountProperty

Level 1 Account Property. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Properties_Table.Property_Id` `Introduced in version 25.1.3.28`

_Type_: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Properties_Table.Property_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level2AccountGroup

Level 2 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` `Introduced in version 25.1.3.28`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Account_Groups_Table.Account_Group_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level2AccountProperty

Level 2 Account Property. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Properties_Table.Property_Id` `Introduced in version 25.1.3.28`

_Type_: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Properties_Table.Property_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level3AccountGroup

Level 3 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` `Introduced in version 25.1.3.28`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Account_Groups_Table.Account_Group_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level3AccountProperty

Level 3 Account Property. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Properties_Table.Property_Id` `Introduced in version 25.1.3.28`

_Type_: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Properties_Table.Property_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level4AccountGroup

Level 4 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` `Introduced in version 25.1.3.28`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Account_Groups_Table.Account_Group_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level4AccountProperty

Level 4 Account Property. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Properties_Table.Property_Id` `Introduced in version 25.1.3.28`

_Type_: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Properties_Table.Property_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level5AccountGroup

Level 5 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` `Introduced in version 25.1.3.28`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Account_Groups_Table.Account_Group_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level5AccountProperty

Level 5 Account Property. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Gen_Properties_Table.Property_Id` `Introduced in version 25.1.3.28`

_Type_: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Properties_Table.Property_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Level6AccountGroup

Level 6 Account Group. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Account_Groups_Table.Account_Group_Id` `Introduced in version 25.1.3.28`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Account_Groups_Table.Account_Group_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### ProfitCenter

Profit Center. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Acc_Profit_Centers_Table.Profit_Center_Id` `Introduced in version 25.1.3.28`

_Type_: **[ProfitCenters](Finance.Accounting.ProfitCenters.md)**  
_Category_: **System**  
_Inherited From_: **Acc_Profit_Centers_Table.Profit_Center_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Accounting_TrialBalanceDetailed?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Accounting_TrialBalanceDetailed?$top=10>

