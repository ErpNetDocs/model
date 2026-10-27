---
uid: Regulatory.Saft.AccountBalanceCorrections
---
# Regulatory.Saft.AccountBalanceCorrections (View)


Signed SAF-T balance corrections and export activity grouped by account and full item key.

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.AccountBalanceCorrections  
Introduced In Version: 27.1.1.77  
API access:  ReadOnly  

## Visualization
Display Format: {FromDate}: {ToDate}  
Search Members:   
Category:  Views  
Show in UI:  CannotBeShown  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Saft.AccountBalanceCorrections](Regulatory.Saft.AccountBalanceCorrections.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountId](Regulatory.Saft.AccountBalanceCorrections.md#accountid) | guid | Account. `Required` `Filter(multi eq)` |
| [ClosingCorrectionBase](Regulatory.Saft.AccountBalanceCorrections.md#closingcorrectionbase) | decimal (38, 2) | Closing Correction Base`Required` |
| [EnterpriseCompanyId](Regulatory.Saft.AccountBalanceCorrections.md#enterprisecompanyid) | guid | Enterprise company. `Required` `Filter(multi eq)` |
| [FromDate](Regulatory.Saft.AccountBalanceCorrections.md#fromdate) | date | Filter date for start of period`Required` `Filter(eq)` |
| [FromReleaseTime](Regulatory.Saft.AccountBalanceCorrections.md#fromreleasetime) | datetime | Filter date for Release start time`Required` `Filter(eq)` |
| [ItemKey](Regulatory.Saft.AccountBalanceCorrections.md#itemkey) | string (64) __nullable__ | Item_Key |
| [OpeningCorrectionBase](Regulatory.Saft.AccountBalanceCorrections.md#openingcorrectionbase) | decimal (38, 2) | Opening Correction Base`Required` |
| [ToDate](Regulatory.Saft.AccountBalanceCorrections.md#todate) | date | Filter date for end of period`Required` `Filter(eq)` |
| [ToReleaseTime](Regulatory.Saft.AccountBalanceCorrections.md#toreleasetime) | datetime | Filter date for Release end time`Required` `Filter(eq)` |
| [VouchersInPeriod](Regulatory.Saft.AccountBalanceCorrections.md#vouchersinperiod) | int32 | Vouchers In Period`Required` |


## Attribute Details

### AccountId

Account. `Required` `Filter(multi eq)`

Type: **guid**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ClosingCorrectionBase

Closing Correction Base`Required`

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### EnterpriseCompanyId

Enterprise company. `Required` `Filter(multi eq)`

Type: **guid**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### FromDate

Filter date for start of period`Required` `Filter(eq)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FromReleaseTime

Filter date for Release start time`Required` `Filter(eq)`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ItemKey

Item_Key

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### OpeningCorrectionBase

Opening Correction Base`Required`

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ToDate

Filter date for end of period`Required` `Filter(eq)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ToReleaseTime

Filter date for Release end time`Required` `Filter(eq)`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### VouchersInPeriod

Vouchers In Period`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Regulatory_Saft_AccountBalanceCorrections

Domain API Entity Type: 
Regulatory_Saft_AccountBalanceCorrectionsEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_AccountBalanceCorrections?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_AccountBalanceCorrections?$top=10>

