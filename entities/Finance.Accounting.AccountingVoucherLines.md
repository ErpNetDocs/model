---
uid: Finance.Accounting.AccountingVoucherLines
---
# Finance.Accounting.AccountingVoucherLines


Contains the individual debit or credit lines that make up an accounting voucher. Each line records a single entry to a specific account, possibly with analytical dimensions.

## General
Namespace: [Finance.Accounting](Finance.Accounting.md)  
Repository: Finance.Accounting.AccountingVoucherLines  
Base Table: Acc_Voucher_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {Voucher.DocumentNo} {Voucher.DocumentType.TypeName:T}  
Search Members: Voucher.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Accounting.AccountingVouchers](Finance.Accounting.AccountingVouchers.md)  
Aggregate Root:  
[Finance.Accounting.AccountingVouchers](Finance.Accounting.AccountingVouchers.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CorrespondanceNo](Finance.Accounting.AccountingVoucherLines.md#correspondanceno) | int32 | The number of the correspondence group within the accounting voucher. For each correspondence group, the debits are equal to the credits 
| [CorrespondantAmount](Finance.Accounting.AccountingVoucherLines.md#correspondantamount) | decimal (18, 2) __nullable__ | The amount (in the currency of the correspondent line) to which the amount in this line is corresponding if the current line is corresponding to only one line. 
| [Credit](Finance.Accounting.AccountingVoucherLines.md#credit) | [Amount (18, 2)](../data-types.md#amount) | The amount of the credit in the currency of the account. 0 means that the account is not credited 
| [CreditBase](Finance.Accounting.AccountingVoucherLines.md#creditbase) | [Amount (18, 2)](../data-types.md#amount) | The amount of credit in base currency 
| [CreditReporting](Finance.Accounting.AccountingVoucherLines.md#creditreporting) | [Amount (18, 2)](../data-types.md#amount) __nullable__ | The amount of credit in reporting currency. 
| [Debit](Finance.Accounting.AccountingVoucherLines.md#debit) | [Amount (18, 2)](../data-types.md#amount) | The amount of the debit in the currency of the account. 0 means that the account is not debited 
| [DebitBase](Finance.Accounting.AccountingVoucherLines.md#debitbase) | [Amount (18, 2)](../data-types.md#amount) | The amount of debit in base currency 
| [DebitReporting](Finance.Accounting.AccountingVoucherLines.md#debitreporting) | [Amount (18, 2)](../data-types.md#amount) __nullable__ | The amount of debit in reporting currency. 
| [ItemKey](Finance.Accounting.AccountingVoucherLines.md#itemkey) | string (64) __nullable__ | The item (grouping) key for the account in the line. Account_Id + Item_Key - the smallest unit of calculation for account balance. 
| [LineNo](Finance.Accounting.AccountingVoucherLines.md#lineno) | int32 | Consecutive number of the line within the voucher 
| [RateDivisor](Finance.Accounting.AccountingVoucherLines.md#ratedivisor) | decimal (18, 6) | The divisor for conversion from Debit/Credit to base currency 
| [RateDivisorRC](Finance.Accounting.AccountingVoucherLines.md#ratedivisorrc) | decimal (18, 6) __nullable__ | The divisor for conversion from Debit/Credit to Reporting currency. 
| [RateMultiplier](Finance.Accounting.AccountingVoucherLines.md#ratemultiplier) | decimal (18, 6) | The multiplier for conversion from Debit/Credit to base currency 
| [RateMultiplierRC](Finance.Accounting.AccountingVoucherLines.md#ratemultiplierrc) | decimal (18, 6) __nullable__ | The multiplier for conversion from Debit/Credit to Reporting currency. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.AccountingVoucherLines.md#account) | [Accounts](Finance.Accounting.Accounts.md) | The account being debited or credited |
| [CostCenter](Finance.Accounting.AccountingVoucherLines.md#costcenter) | [CostCenters](Finance.Accounting.CostCenters.md) (nullable) | The cost center to which this cost is related |
| [Currency](Finance.Accounting.AccountingVoucherLines.md#currency) | [Currencies](General.Currencies.Currencies.md) | The currency of the movement in this line. If there is defined currency for the account in the line that it should be equal to the value in this field. |
| [Document](Finance.Accounting.AccountingVoucherLines.md#document) | [AccountingVouchers](Finance.Accounting.AccountingVouchers.md) | The owner document. The voucher to which this line is attached. `Required` `Filter(multi eq)` |
| [ProfitCenter](Finance.Accounting.AccountingVoucherLines.md#profitcenter) | [ProfitCenters](Finance.Accounting.ProfitCenters.md) (nullable) | The profit center to which this revenue is related |
| [ReferencedDocument](Finance.Accounting.AccountingVoucherLines.md#referenceddocument) | [Documents](General.Documents.Documents.md) | The document which is referenced by the line. By default, this is the document of the voucher |
| [Voucher](Finance.Accounting.AccountingVoucherLines.md#voucher) | [AccountingVouchers](Finance.Accounting.AccountingVouchers.md) | The voucher to which this line is attached |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Accounting.AccountingVoucherLines.md#id) | guid |  
| [ObjectVersion](Finance.Accounting.AccountingVoucherLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Accounting.AccountingVoucherLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CorrespondanceNo

The number of the correspondence group within the accounting voucher. For each correspondence group, the debits are equal to the credits

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### CorrespondantAmount

The amount (in the currency of the correspondent line) to which the amount in this line is corresponding if the current line is corresponding to only one line.

Type: **decimal (18, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Credit

The amount of the credit in the currency of the account. 0 means that the account is not credited

Type: **[Amount (18, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### CreditBase

The amount of credit in base currency

Type: **[Amount (18, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

### CreditReporting

The amount of credit in reporting currency.

Type: **[Amount (18, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SetDefaultsToRCattributes( obj.CreditReporting, "CreditReporting")`

### Debit

The amount of the debit in the currency of the account. 0 means that the account is not debited

Type: **[Amount (18, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### DebitBase

The amount of debit in base currency

Type: **[Amount (18, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

### DebitReporting

The amount of debit in reporting currency.

Type: **[Amount (18, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SetDefaultsToRCattributes( obj.DebitReporting, "DebitReporting")`

### ItemKey

The item (grouping) key for the account in the line. Account_Id + Item_Key - the smallest unit of calculation for account balance.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### LineNo

Consecutive number of the line within the voucher

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Voucher.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.Voucher.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### RateDivisor

The divisor for conversion from Debit/Credit to base currency

Type: **decimal (18, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **HiddenByDefault**  

### RateDivisorRC

The divisor for conversion from Debit/Credit to Reporting currency.

Type: **decimal (18, 6) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.SetDefaultsToRCattributes( Convert( obj.RateDivisorRC, Object), "RateDivisorRC")`

Front-End Recalc Expressions:  
`IIF( ( ( ( ( ( ( ( ( obj.Account != null) AndAlso ( obj.Currency != null)) AndAlso ( obj.Voucher.EnterpriseCompany.ReportingCurrency != null)) AndAlso Not( obj.Voucher.EnterpriseCompany.ReportingCurrency.IsGhost)) AndAlso ( ( obj.ItemKey != null) OrElse True)) AndAlso ( ( obj.ReferencedDocument == null) OrElse True)) AndAlso ( ( obj.Debit.Value != 0) OrElse True)) AndAlso ( ( obj.Credit.Value != 0) OrElse True)), obj.SetMultiplierAndDivisorRC( ).Item2, obj.RateDivisorRC)`
### RateMultiplier

The multiplier for conversion from Debit/Credit to base currency

Type: **decimal (18, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **HiddenByDefault**  

### RateMultiplierRC

The multiplier for conversion from Debit/Credit to Reporting currency.

Type: **decimal (18, 6) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.SetDefaultsToRCattributes( Convert( obj.RateMultiplierRC, Object), "RateMultiplierRC")`

Front-End Recalc Expressions:  
`IIF( ( ( ( ( ( ( ( ( obj.Account != null) AndAlso ( obj.Currency != null)) AndAlso ( obj.Voucher.EnterpriseCompany.ReportingCurrency != null)) AndAlso Not( obj.Voucher.EnterpriseCompany.ReportingCurrency.IsGhost)) AndAlso ( ( obj.ItemKey != null) OrElse True)) AndAlso ( ( obj.ReferencedDocument == null) OrElse True)) AndAlso ( ( obj.Debit.Value != 0) OrElse True)) AndAlso ( ( obj.Credit.Value != 0) OrElse True)), obj.SetMultiplierAndDivisorRC( ).Item1, obj.RateMultiplierRC)`
### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

Type: **int32**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Account

The account being debited or credited

Type: **[Accounts](Finance.Accounting.Accounts.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CostCenter

The cost center to which this cost is related

Type: **[CostCenters](Finance.Accounting.CostCenters.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Currency

The currency of the movement in this line. If there is defined currency for the account in the line that it should be equal to the value in this field.

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Document

The owner document. The voucher to which this line is attached. `Required` `Filter(multi eq)`

Type: **[AccountingVouchers](Finance.Accounting.AccountingVouchers.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProfitCenter

The profit center to which this revenue is related

Type: **[ProfitCenters](Finance.Accounting.ProfitCenters.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ReferencedDocument

The document which is referenced by the line. By default, this is the document of the voucher

Type: **[Documents](General.Documents.Documents.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( obj.Voucher.DefaultReferencedDocument != null), obj.Voucher.DefaultReferencedDocument, Convert( obj.Voucher, Document))`

### Voucher

The voucher to which this line is attached

Type: **[AccountingVouchers](Finance.Accounting.AccountingVouchers.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
Return Type: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    Type: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    Type: string  
     Optional: True  
    Default Value: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **top**  
    The top clause - default is 10  
    Type: int32  
     Optional: True  
    Default Value: 10  

  * **skip**  
    The skip clause - default is 0  
    Type: int32  
     Optional: True  
    Default Value: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
Return Type: **void**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

**Parameters**  
  * **user**  
    The user.  
    Type: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    Type: string  

  * **subject**  
    The notification subject.  
    Type: string  

  * **priority**  
    The notification priority.  
    Type: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> Model Value: 1 <br /> Domain API Value: 'Background' |
    | Low | Low value. Stored as 2. <br /> Model Value: 2 <br /> Domain API Value: 'Low' |
    | Normal | Normal value. Stored as 3. <br /> Model Value: 3 <br /> Domain API Value: 'Normal' |
    | High | High value. Stored as 4. <br /> Model Value: 4 <br /> Domain API Value: 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> Model Value: 5 <br /> Domain API Value: 'Urgent' |

     Optional: True  
    Default Value: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Finance.Accounting.AccountingVoucherLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Accounting.AccountingVoucherLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Accounting_AccountingVoucherLines

Domain API Entity Type: 
Finance_Accounting_AccountingVoucherLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Accounting_AccountingVoucherLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Accounting_AccountingVoucherLines?$top=10>

