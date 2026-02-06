---
uid: Finance.Payments.PaymentAccounts
---
# Finance.Payments.PaymentAccounts


Payment accounts are cash, bank and other accounts, which are used in payments. Payment accounts are frequently used as analytical dimensions (properties) for general ledger accounts.

## General
Namespace: [Finance.Payments](Finance.Payments.md)  
Repository: Finance.Payments.PaymentAccounts  
Base Table: Cash_Payment_Accounts  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  2 - Track object changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Payments.PaymentAccounts](Finance.Payments.PaymentAccounts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Finance.Payments.PaymentAccounts.md#code) | string (16) | The unique code of the PaymentAccount. `Required` `Filter(eq;like)` `ORD` 
| [IsActive](Finance.Payments.PaymentAccounts.md#isactive) | boolean | Indicates whether this payment account is currently used.[Required] [Default(true)] [Filter(eq)] 
| [Name](Finance.Payments.PaymentAccounts.md#name) | [MultilanguageString (50)](../data-types.md#multilanguagestring) | The name of this PaymentAccount. `Required` `Filter(like)` 
| [UseBaseCurrency](Finance.Payments.PaymentAccounts.md#usebasecurrency) | boolean | When enabled, this setting restricts the payment account to use only the base currency.[Required] [Default(false)] [Introduced in version 26.1.4.36] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Finance.Payments.PaymentAccounts.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the permissions for this PaymentAccount. An empty value means that all users have unlimited permissions. `Filter(multi eq)` |
| [BankAccount](Finance.Payments.PaymentAccounts.md#bankaccount) | [PartyBankAccounts](General.Contacts.PartyBankAccounts.md) (nullable) | The bank account, which is represented by this payment account. |
| [Currency](Finance.Payments.PaymentAccounts.md#currency) | [Currencies](General.Currencies.Currencies.md) | The currency in which the movements for this payment account will be recorded. |
| [EnterpriseCompany](Finance.Payments.PaymentAccounts.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this PaymentAccount applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [EnterpriseCompanyLocation](Finance.Payments.PaymentAccounts.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The Enterprise Company Location to which this PaymentAccount applies, or null if it is for all enterprise company locations. `Filter(multi eq)` |
| [PaymentType](Finance.Payments.PaymentAccounts.md#paymenttype) | [PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable) | Specifies the payment type used to pay, when using this payment account. NULL when the payment type is unknown or unspecified. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Payments.PaymentAccounts.md#id) | guid |  
| [ObjectVersion](Finance.Payments.PaymentAccounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Finance.Payments.PaymentAccounts.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Payments.PaymentAccounts.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Finance.Payments.PaymentAccounts.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Finance.Payments.PaymentAccounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Code

The unique code of the PaymentAccount. `Required` `Filter(eq;like)` `ORD`

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.Code, null, "00000")`

### IsActive

Indicates whether this payment account is currently used.[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

The name of this PaymentAccount. `Required` `Filter(like)`

Type: **[MultilanguageString (50)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UseBaseCurrency

When enabled, this setting restricts the payment account to use only the base currency.[Required] [Default(false)] [Introduced in version 26.1.4.36]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
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

### AccessKey

The access key, containing the permissions for this PaymentAccount. An empty value means that all users have unlimited permissions. `Filter(multi eq)`

Type: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  


Remarks  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
| Release Payment Transactions | Permission1 |
### BankAccount

The bank account, which is represented by this payment account.

Type: **[PartyBankAccounts](General.Contacts.PartyBankAccounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Currency

The currency in which the movements for this payment account will be recorded.

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company to which this PaymentAccount applies, or null if it is for all enterprise companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### EnterpriseCompanyLocation

The Enterprise Company Location to which this PaymentAccount applies, or null if it is for all enterprise company locations. `Filter(multi eq)`

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PaymentType

Specifies the payment type used to pay, when using this payment account. NULL when the payment type is unknown or unspecified.

Type: **[PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable)**  
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

[!list limit=1000 erp.entity=Finance.Payments.PaymentAccounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Payments.PaymentAccounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Payments_PaymentAccounts

Domain API Entity Type: 
Finance_Payments_PaymentAccount

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Payments_PaymentAccounts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Payments_PaymentAccounts?$top=10>

