---
uid: Finance.Accounting.Accounts
---
# Finance.Accounting.Accounts


Leaf-level financial accounts used for actual postings. Each account belongs to an account group and is used to record specific types of transactions in the general ledger.

## General
Namespace: [Finance.Accounting](Finance.Accounting.md)  
Repository: Finance.Accounting.Accounts  
Base Table: Acc_Accounts  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Number; Name  
Code Member: Number  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Accounting.Accounts](Finance.Accounting.Accounts.md)  
  * [Finance.Accounting.AccountRequiredProperties](Finance.Accounting.AccountRequiredProperties.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountFullNumber](Finance.Accounting.Accounts.md#accountfullnumber) | string (30) | The full number of the account, unique among all accounts. It consists of the group number, concatenated with the account number[Required] [Filter(like)] [ReadOnly] 
| [CurrencyValuationMethod](Finance.Accounting.Accounts.md#currencyvaluationmethod) | [CurrencyValuationMethod](Finance.Accounting.Accounts.md#currencyvaluationmethod) | Method for base currency valuation of non base currency amounts.[Required] [Default(&quot;ACB&quot;)] 
| [Description](Finance.Accounting.Accounts.md#description) | string (254) __nullable__ | The description of this Account. 
| [Discontinued](Finance.Accounting.Accounts.md#discontinued) | boolean | 1 means that the account won't be used any more and should not appear in combo boxes[Required] [Default(false)] [Filter(eq)] 
| [LimitToBaseCurrency](Finance.Accounting.Accounts.md#limittobasecurrency) | boolean | When enabled, this setting restricts the account to use only the base or reporting currency. By default, transactions are recorded in the base currency, but reporting currency is also allowed in accounting entries when this option is checked.[Required] [Default(false)] [Filter(eq)] [Introduced in version 26.1.3.78] 
| [Name](Finance.Accounting.Accounts.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The account name[Required] [Filter(like)] 
| [Number](Finance.Accounting.Accounts.md#number) | string (30) | The number of the account, unique within the account group[Required] [Filter(like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountGroup](Finance.Accounting.Accounts.md#accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | The account group to which this account belongs |
| [Currency](Finance.Accounting.Accounts.md#currency) | [Currencies](General.Currencies.Currencies.md) (nullable) | The currency of the account. If not specified, the account accepts movements in any currency. If specified, all movements are recorded in this currency. |
| [EnterpriseCompany](Finance.Accounting.Accounts.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this Account applies, or null if it is for all enterprise companies. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Accounting.Accounts.md#id) | guid |  
| [ObjectVersion](Finance.Accounting.Accounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Finance.Accounting.Accounts.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Accounting.Accounts.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Finance.Accounting.Accounts.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Finance.Accounting.Accounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| RequiredProperties | [AccountRequiredProperties](Finance.Accounting.AccountRequiredProperties.md) | List of `AccountRequiredProperty`(Finance.Accounting.AccountRequiredProperties.md) child objects, based on the `Finance.Accounting.AccountRequiredProperty.Account`(Finance.Accounting.AccountRequiredProperties.md#account) back reference 


## Attribute Details

### AccountFullNumber

The full number of the account, unique among all accounts. It consists of the group number, concatenated with the account number[Required] [Filter(like)] [ReadOnly]

Type: **string (30)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`( obj.AccountGroup.Number + obj.Number)`
### CurrencyValuationMethod

Method for base currency valuation of non base currency amounts.[Required] [Default(&quot;ACB&quot;)]

Type: **[CurrencyValuationMethod](Finance.Accounting.Accounts.md#currencyvaluationmethod)**  
Category: **System**  
Allowed values for the `CurrencyValuationMethod`(Finance.Accounting.Accounts.md#currencyvaluationmethod) data attribute  
Allowed Values (Finance.Accounting.AccountsRepository.CurrencyValuationMethod Enum Members)  

| Value | Description |
| ---- | --- |
| AccountCurrentBalance | AccountCurrentBalance value. Stored as 'ACB'. <br /> Database Value: 'ACB' <br /> Model Value: 0 <br /> Domain API Value: 'AccountCurrentBalance' |
| DocumentCurrencyDirectory | DocumentCurrencyDirectory value. Stored as 'DCD'. <br /> Database Value: 'DCD' <br /> Model Value: 1 <br /> Domain API Value: 'DocumentCurrencyDirectory' |
| BalanceReferenceDocument | BalanceReferenceDocument value. Stored as 'BRD'. <br /> Database Value: 'BRD' <br /> Model Value: 2 <br /> Domain API Value: 'BalanceReferenceDocument' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **AccountCurrentBalance**  
Show in UI: **ShownByDefault**  

### Description

The description of this Account.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Discontinued

1 means that the account won't be used any more and should not appear in combo boxes[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LimitToBaseCurrency

When enabled, this setting restricts the account to use only the base or reporting currency. By default, transactions are recorded in the base currency, but reporting currency is also allowed in accounting entries when this option is checked.[Required] [Default(false)] [Filter(eq)] [Introduced in version 26.1.3.78]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Name

The account name[Required] [Filter(like)]

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Number

The number of the account, unique within the account group[Required] [Filter(like)]

Type: **string (30)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  

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

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

### AccountGroup

The account group to which this account belongs

Type: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Currency

The currency of the account. If not specified, the account accepts movements in any currency. If specified, all movements are recorded in this currency.

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company to which this Account applies, or null if it is for all enterprise companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Finance.Accounting.Accounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Accounting.Accounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Accounting_Accounts

Domain API Entity Type: 
Finance_Accounting_Account

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Accounting_Accounts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Accounting_Accounts?$top=10>

