---
uid: Finance.Accounting.Accounts
---
# Finance.Accounting.Accounts Entity

**Namespace:** [Finance.Accounting](Finance.Accounting.md)  

Contains the leaf level of the chart of accounts. Entity: Acc_Accounts

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Number; Name_  
Code Data Member:  
_Number_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Accounting.Accounts](Finance.Accounting.Accounts.md)  
  * [Finance.Accounting.AccountRequiredProperties](Finance.Accounting.AccountRequiredProperties.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountFullNumber](Finance.Accounting.Accounts.md#accountfullnumber) | string (30) | The full number of the account, unique among all accounts. It consists of the group number, concatenated with the account number. `Required` `Filter(like)` `ReadOnly` 
| [CurrencyValuationMethod](Finance.Accounting.Accounts.md#currencyvaluationmethod) | [CurrencyValuationMethod](Finance.Accounting.Accounts.md#currencyvaluationmethod) | Method for base currency valuation of non base currency amounts. ACB = Account_Current_Balance, DCD = Document_Currency_<br />Directory, BRD=Balance_Reference_<br />Document. `Required` `Default("ACB")` 
| [Description](Finance.Accounting.Accounts.md#description) | string (254) __nullable__ | The description of this Account. 
| [Discontinued](Finance.Accounting.Accounts.md#discontinued) | boolean | True means that the account won't be used any more and should not appear in combo boxes. `Required` `Default(false)` `Filter(eq)` 
| [DisplayText](Finance.Accounting.Accounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Finance.Accounting.Accounts.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Accounting.Accounts.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Finance.Accounting.Accounts.md#id) | guid |  
| [LimitToBaseCurrency](Finance.Accounting.Accounts.md#limittobasecurrency) | boolean | When enabled, this setting restricts the account to use only the base or reporting currency. By default, transactions are recorded in the base currency, but reporting currency is also allowed in accounting entries when this option is checked. `Required` `Default(false)` `Filter(eq)` `Introduced in version 26.1.3.78` 
| [Name](Finance.Accounting.Accounts.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The account name. `Required` `Filter(like)` 
| [Number](Finance.Accounting.Accounts.md#number) | string (30) | The number of the account, unique within the account group. `Required` `Filter(like)` 
| [ObjectVersion](Finance.Accounting.Accounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountGroup](Finance.Accounting.Accounts.md#accountgroup) | [AccountGroups](Finance.Accounting.AccountGroups.md) | The account group to which this account belongs. `Required` `Filter(multi eq)` |
| [Currency](Finance.Accounting.Accounts.md#currency) | [Currencies](General.Currencies.Currencies.md) (nullable) | The currency of the account. If not specified, the account accepts movements in any currency. If specified, all movements are recorded in this currency. `Filter(multi eq)` |
| [EnterpriseCompany](Finance.Accounting.Accounts.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this Account applies, or null if it is for all enterprise companies. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| RequiredProperties | [AccountRequiredProperties](Finance.Accounting.AccountRequiredProperties.md) | List of `AccountRequiredProperty`(Finance.Accounting.AccountRequiredProperties.md) child objects, based on the `Finance.Accounting.AccountRequiredProperty.Account`(Finance.Accounting.AccountRequiredProperties.md#account) back reference 


## Attribute Details

### AccountFullNumber

The full number of the account, unique among all accounts. It consists of the group number, concatenated with the account number. `Required` `Filter(like)` `ReadOnly`

_Type_: **string (30)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **30**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`( obj.AccountGroup.Number + obj.Number)`
### CurrencyValuationMethod

Method for base currency valuation of non base currency amounts. ACB = Account_Current_Balance, DCD = Document_Currency_Directory, BRD=Balance_Reference_Document. `Required` `Default("ACB")`

_Type_: **[CurrencyValuationMethod](Finance.Accounting.Accounts.md#currencyvaluationmethod)**  
_Category_: **System**  
Allowed values for the `CurrencyValuationMethod`(Finance.Accounting.Accounts.md#currencyvaluationmethod) data attribute  
_Allowed Values (Finance.Accounting.AccountsRepository.CurrencyValuationMethod Enum Members)_  

| Value | Description |
| ---- | --- |
| AccountCurrentBalance | AccountCurrentBalance value. Stored as 'ACB'. <br /> _Database Value:_ 'ACB' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AccountCurrentBalance' |
| DocumentCurrencyDirectory | DocumentCurrencyDirectory value. Stored as 'DCD'. <br /> _Database Value:_ 'DCD' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'DocumentCurrencyDirectory' |
| BalanceReferenceDocument | BalanceReferenceDocument value. Stored as 'BRD'. <br /> _Database Value:_ 'BRD' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'BalanceReferenceDocument' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **AccountCurrentBalance**  
_Show in UI_: **ShownByDefault**  

### Description

The description of this Account.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### Discontinued

True means that the account won't be used any more and should not appear in combo boxes. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
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

### LimitToBaseCurrency

When enabled, this setting restricts the account to use only the base or reporting currency. By default, transactions are recorded in the base currency, but reporting currency is also allowed in accounting entries when this option is checked. `Required` `Default(false)` `Filter(eq)` `Introduced in version 26.1.3.78`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Name

The account name. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Number

The number of the account, unique within the account group. `Required` `Filter(like)`

_Type_: **string (30)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **30**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### AccountGroup

The account group to which this account belongs. `Required` `Filter(multi eq)`

_Type_: **[AccountGroups](Finance.Accounting.AccountGroups.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Currency

The currency of the account. If not specified, the account accepts movements in any currency. If specified, all movements are recorded in this currency. `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company to which this Account applies, or null if it is for all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

