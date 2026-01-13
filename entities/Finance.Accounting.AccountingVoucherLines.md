---
uid: Finance.Accounting.AccountingVoucherLines
---
# Finance.Accounting.AccountingVoucherLines Entity

**Namespace:** [Finance.Accounting](Finance.Accounting.md)  

Contains one debit or credit posting within an accounting voucher. Entity: Acc_Voucher_Lines

## Default Visualization
Default Display Text Format:  
_{LineNo}. {Voucher.DocumentNo} {Voucher.DocumentType.TypeName:T}_  
Default Search Members:  
_Voucher.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Accounting.AccountingVouchers](Finance.Accounting.AccountingVouchers.md)  
Aggregate Root:  
[Finance.Accounting.AccountingVouchers](Finance.Accounting.AccountingVouchers.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CorrespondanceNo](Finance.Accounting.AccountingVoucherLines.md#correspondanceno) | int32 | The number of the correspondance group within the accounting voucher. For each correspondance group, the debits are equal to the credits. `Required` `Default(0)` 
| [CorrespondantAmount](Finance.Accounting.AccountingVoucherLines.md#correspondantamount) | decimal (18, 2) __nullable__ | The amount (in the currency of the correspondant line) to which the amount in this line is corresponding. This field has value only when the current line is corresponding to only one line (e.g. null means that the current line is corresponding to many lines). `ReadOnly` 
| [Credit](Finance.Accounting.AccountingVoucherLines.md#credit) | [Amount (18, 2)](../data-types.md#amount) | The amount of the credit in the currency of the account. 0 means that the account is not credited. `Currency: Currency` `Required` `Default(0)` 
| [CreditBase](Finance.Accounting.AccountingVoucherLines.md#creditbase) | [Amount (18, 2)](../data-types.md#amount) | The amount of credit in base currency. `Currency: Voucher.EnterpriseCompany.BaseCurrency` `Required` `Default(0)` 
| [CreditReporting](Finance.Accounting.AccountingVoucherLines.md#creditreporting) | [Amount (18, 2)](../data-types.md#amount) __nullable__ | The amount of credit in reporting currency. `Currency: Voucher.EnterpriseCompany.ReportingCurrency` `Introduced in version 25.1.2.88` 
| [Debit](Finance.Accounting.AccountingVoucherLines.md#debit) | [Amount (18, 2)](../data-types.md#amount) | The amount of the debit in the currency of the account. 0 means that the account is not debited. `Currency: Currency` `Required` `Default(0)` 
| [DebitBase](Finance.Accounting.AccountingVoucherLines.md#debitbase) | [Amount (18, 2)](../data-types.md#amount) | The amount of debit in base currency. `Currency: Voucher.EnterpriseCompany.BaseCurrency` `Required` `Default(0)` 
| [DebitReporting](Finance.Accounting.AccountingVoucherLines.md#debitreporting) | [Amount (18, 2)](../data-types.md#amount) __nullable__ | The amount of debit in reporting currency. `Currency: Voucher.EnterpriseCompany.ReportingCurrency` `Introduced in version 25.1.2.88` 
| [DisplayText](Finance.Accounting.AccountingVoucherLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Finance.Accounting.AccountingVoucherLines.md#id) | guid |  
| [ItemKey](Finance.Accounting.AccountingVoucherLines.md#itemkey) | string (64) __nullable__ | The item (grouping) key for the account in the line. Account_Id + Item_Key - the smallest unit of calculation for account balance. `Filter(eq;like)` 
| [LineNo](Finance.Accounting.AccountingVoucherLines.md#lineno) | int32 | Consecutive number of the line within the voucher. `Required` 
| [ObjectVersion](Finance.Accounting.AccountingVoucherLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RateDivisor](Finance.Accounting.AccountingVoucherLines.md#ratedivisor) | decimal (18, 6) | The divisor for conversion from Debit/Credit to base currency. `Required` `Default(1)` 
| [RateDivisorRC](Finance.Accounting.AccountingVoucherLines.md#ratedivisorrc) | decimal (18, 6) __nullable__ | The divisor for conversion from Debit/Credit to Reporting currency. `Introduced in version 26.1.3.74` 
| [RateMultiplier](Finance.Accounting.AccountingVoucherLines.md#ratemultiplier) | decimal (18, 6) | The multiplier for conversion from Debit/Credit to base currency. `Required` `Default(1)` 
| [RateMultiplierRC](Finance.Accounting.AccountingVoucherLines.md#ratemultiplierrc) | decimal (18, 6) __nullable__ | The multiplier for conversion from Debit/Credit to Reporting currency. `Introduced in version 26.1.3.74` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.AccountingVoucherLines.md#account) | [Accounts](Finance.Accounting.Accounts.md) | The account being debited or credited. `Required` `Filter(multi eq)` |
| [CostCenter](Finance.Accounting.AccountingVoucherLines.md#costcenter) | [CostCenters](Finance.Accounting.CostCenters.md) (nullable) | The cost center to which this cost is related. `Filter(multi eq)` |
| [Currency](Finance.Accounting.AccountingVoucherLines.md#currency) | [Currencies](General.Currencies.Currencies.md) | The currency of the movement in this line. If there is defined currency for the account in the line that it should be equal to the value in this field. `Required` `Filter(multi eq)` |
| [Document](Finance.Accounting.AccountingVoucherLines.md#document) | [AccountingVouchers](Finance.Accounting.AccountingVouchers.md) | The owner document. The voucher to which this line is attached. `Required` `Filter(multi eq)` |
| [ProfitCenter](Finance.Accounting.AccountingVoucherLines.md#profitcenter) | [ProfitCenters](Finance.Accounting.ProfitCenters.md) (nullable) | The profit center to which this revenue is related. `Filter(multi eq)` |
| [ReferencedDocument](Finance.Accounting.AccountingVoucherLines.md#referenceddocument) | [Documents](General.Documents.Documents.md) | The document which is referenced by the line. By default, this is the document of the voucher. `Required` `Filter(multi eq)` |
| [Voucher](Finance.Accounting.AccountingVoucherLines.md#voucher) | [AccountingVouchers](Finance.Accounting.AccountingVouchers.md) | The voucher to which this line is attached. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### CorrespondanceNo

The number of the correspondance group within the accounting voucher. For each correspondance group, the debits are equal to the credits. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### CorrespondantAmount

The amount (in the currency of the correspondant line) to which the amount in this line is corresponding. This field has value only when the current line is corresponding to only one line (e.g. null means that the current line is corresponding to many lines). `ReadOnly`

_Type_: **decimal (18, 2) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### Credit

The amount of the credit in the currency of the account. 0 means that the account is not credited. `Currency: Currency` `Required` `Default(0)`

_Type_: **[Amount (18, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### CreditBase

The amount of credit in base currency. `Currency: Voucher.EnterpriseCompany.BaseCurrency` `Required` `Default(0)`

_Type_: **[Amount (18, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **HiddenByDefault**  

### CreditReporting

The amount of credit in reporting currency. `Currency: Voucher.EnterpriseCompany.ReportingCurrency` `Introduced in version 25.1.2.88`

_Type_: **[Amount (18, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.SetDefaultsToRCattributes( obj.CreditReporting, "CreditReporting")`

### Debit

The amount of the debit in the currency of the account. 0 means that the account is not debited. `Currency: Currency` `Required` `Default(0)`

_Type_: **[Amount (18, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### DebitBase

The amount of debit in base currency. `Currency: Voucher.EnterpriseCompany.BaseCurrency` `Required` `Default(0)`

_Type_: **[Amount (18, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **HiddenByDefault**  

### DebitReporting

The amount of debit in reporting currency. `Currency: Voucher.EnterpriseCompany.ReportingCurrency` `Introduced in version 25.1.2.88`

_Type_: **[Amount (18, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.SetDefaultsToRCattributes( obj.DebitReporting, "DebitReporting")`

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### ItemKey

The item (grouping) key for the account in the line. Account_Id + Item_Key - the smallest unit of calculation for account balance. `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **HiddenByDefault**  

### LineNo

Consecutive number of the line within the voucher. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.Voucher.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.Voucher.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### RateDivisor

The divisor for conversion from Debit/Credit to base currency. `Required` `Default(1)`

_Type_: **decimal (18, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **HiddenByDefault**  

### RateDivisorRC

The divisor for conversion from Debit/Credit to Reporting currency. `Introduced in version 26.1.3.74`

_Type_: **decimal (18, 6) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.SetDefaultsToRCattributes( Convert( obj.RateDivisorRC, Object), "RateDivisorRC")`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( ( ( ( ( ( obj.Account != null) AndAlso ( obj.Currency != null)) AndAlso ( obj.Voucher.EnterpriseCompany.ReportingCurrency != null)) AndAlso Not( obj.Voucher.EnterpriseCompany.ReportingCurrency.IsGhost)) AndAlso ( ( obj.ItemKey != null) OrElse True)) AndAlso ( ( obj.ReferencedDocument == null) OrElse True)) AndAlso ( ( obj.Debit.Value != 0) OrElse True)) AndAlso ( ( obj.Credit.Value != 0) OrElse True)), obj.SetMultiplierAndDivisorRC( ).Item2, obj.RateDivisorRC)`
### RateMultiplier

The multiplier for conversion from Debit/Credit to base currency. `Required` `Default(1)`

_Type_: **decimal (18, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **HiddenByDefault**  

### RateMultiplierRC

The multiplier for conversion from Debit/Credit to Reporting currency. `Introduced in version 26.1.3.74`

_Type_: **decimal (18, 6) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.SetDefaultsToRCattributes( Convert( obj.RateMultiplierRC, Object), "RateMultiplierRC")`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( ( ( ( ( ( obj.Account != null) AndAlso ( obj.Currency != null)) AndAlso ( obj.Voucher.EnterpriseCompany.ReportingCurrency != null)) AndAlso Not( obj.Voucher.EnterpriseCompany.ReportingCurrency.IsGhost)) AndAlso ( ( obj.ItemKey != null) OrElse True)) AndAlso ( ( obj.ReferencedDocument == null) OrElse True)) AndAlso ( ( obj.Debit.Value != 0) OrElse True)) AndAlso ( ( obj.Credit.Value != 0) OrElse True)), obj.SetMultiplierAndDivisorRC( ).Item1, obj.RateMultiplierRC)`

## Reference Details

### Account

The account being debited or credited. `Required` `Filter(multi eq)`

_Type_: **[Accounts](Finance.Accounting.Accounts.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### CostCenter

The cost center to which this cost is related. `Filter(multi eq)`

_Type_: **[CostCenters](Finance.Accounting.CostCenters.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Currency

The currency of the movement in this line. If there is defined currency for the account in the line that it should be equal to the value in this field. `Required` `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Document

The owner document. The voucher to which this line is attached. `Required` `Filter(multi eq)`

_Type_: **[AccountingVouchers](Finance.Accounting.AccountingVouchers.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProfitCenter

The profit center to which this revenue is related. `Filter(multi eq)`

_Type_: **[ProfitCenters](Finance.Accounting.ProfitCenters.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ReferencedDocument

The document which is referenced by the line. By default, this is the document of the voucher. `Required` `Filter(multi eq)`

_Type_: **[Documents](General.Documents.Documents.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`IIF( ( obj.Voucher.DefaultReferencedDocument != null), obj.Voucher.DefaultReferencedDocument, Convert( obj.Voucher, Document))`

### Voucher

The voucher to which this line is attached. `Required` `Filter(multi eq)` `Owner`

_Type_: **[AccountingVouchers](Finance.Accounting.AccountingVouchers.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    _Type_: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    _Type_: string  
     _Optional_: True  
    _Default Value_: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **top**  
    The top clause - default is 10  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 10  

  * **skip**  
    The skip clause - default is 0  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
_Return Type_: **void**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  

**Parameters**  
  * **user**  
    The user.  
    _Type_: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    _Type_: string  

  * **subject**  
    The notification subject.  
    _Type_: string  

  * **priority**  
    The notification priority.  
    _Type_: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    _Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)_  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Background' |
    | Low | Low value. Stored as 2. <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Low' |
    | Normal | Normal value. Stored as 3. <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Normal' |
    | High | High value. Stored as 4. <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Urgent' |

     _Optional_: True  
    _Default Value_: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


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

