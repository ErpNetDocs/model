---
uid: Finance.Payments.PaymentTypes
---
# Finance.Payments.PaymentTypes


Describes the way of payment. For example: in cash, by bank transfer, with credit card, etc.

## General
Namespace: [Finance.Payments](Finance.Payments.md)  
Repository: Finance.Payments.PaymentTypes  
Base Table: Cash_Payment_Types  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  2 - Track object changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Payments.PaymentTypes](Finance.Payments.PaymentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Finance.Payments.PaymentTypes.md#code) | string (16) | The payment type unique code[Required] [Filter(eq;like)] [ORD] 
| [IsActive](Finance.Payments.PaymentTypes.md#isactive) | boolean | Indicates wheather the payment type is active and usable for choosing in new documents.[Required] [Default(true)] [Filter(eq)] [Introduced in version 19.1] 
| [Name](Finance.Payments.PaymentTypes.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this PaymentType. `Required` `Filter(like)` 
| [SystemType](Finance.Payments.PaymentTypes.md#systemtype) | [SystemType](Finance.Payments.PaymentTypes.md#systemtype) __nullable__ | Not NULL only when this is one of the system payment types. CS=Cash; CD=By Card; BT=Bank Transfer 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultPaymentAccount](Finance.Payments.PaymentTypes.md#defaultpaymentaccount) | [PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable) | When not NULL specifies the default payment account to use associated with this payment type |
| [EnterpriseCompany](Finance.Payments.PaymentTypes.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this PaymentType applies, or null if it is for all enterprise companies. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Payments.PaymentTypes.md#id) | guid |  
| [ObjectVersion](Finance.Payments.PaymentTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Finance.Payments.PaymentTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Payments.PaymentTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Finance.Payments.PaymentTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Finance.Payments.PaymentTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Code

The payment type unique code[Required] [Filter(eq;like)] [ORD]

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

Indicates wheather the payment type is active and usable for choosing in new documents.[Required] [Default(true)] [Filter(eq)] [Introduced in version 19.1]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

The name of this PaymentType. `Required` `Filter(like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SystemType

Not NULL only when this is one of the system payment types. CS=Cash; CD=By Card; BT=Bank Transfer

Type: **[SystemType](Finance.Payments.PaymentTypes.md#systemtype) __nullable__**  
Category: **System**  
Allowed values for the `SystemType`(Finance.Payments.PaymentTypes.md#systemtype) data attribute  
Allowed Values (Finance.Payments.PaymentTypesRepository.SystemType Enum Members)  

| Value | Description |
| ---- | --- |
| Cash | Cash value. Stored as 'CH'. <br /> Database Value: 'CH' <br /> Model Value: 0 <br /> Domain API Value: 'Cash' |
| ByCard | ByCard value. Stored as 'CD'. <br /> Database Value: 'CD' <br /> Model Value: 1 <br /> Domain API Value: 'ByCard' |
| BankTransfer | BankTransfer value. Stored as 'BT'. <br /> Database Value: 'BT' <br /> Model Value: 2 <br /> Domain API Value: 'BankTransfer' |
| Coupons | Coupons value. Stored as 'TK'. <br /> Database Value: 'TK' <br /> Model Value: 3 <br /> Domain API Value: 'Coupons' |
| Check | Check value. Stored as 'CK'. <br /> Database Value: 'CK' <br /> Model Value: 4 <br /> Domain API Value: 'Check' |
| UserDefined1 | UserDefined1 value. Stored as 'U1'. <br /> Database Value: 'U1' <br /> Model Value: 5 <br /> Domain API Value: 'UserDefined1' |
| UserDefined2 | UserDefined2 value. Stored as 'U2'. <br /> Database Value: 'U2' <br /> Model Value: 6 <br /> Domain API Value: 'UserDefined2' |
| Vouchers | Vouchers value. Stored as 'U3'. <br /> Database Value: 'U3' <br /> Model Value: 7 <br /> Domain API Value: 'Vouchers' |
| Packaging | Packaging value. Stored as 'PK'. <br /> Database Value: 'PK' <br /> Model Value: 8 <br /> Domain API Value: 'Packaging' |
| InternalUsage | InternalUsage value. Stored as 'IU'. <br /> Database Value: 'IU' <br /> Model Value: 9 <br /> Domain API Value: 'InternalUsage' |
| Damage | Damage value. Stored as 'DG'. <br /> Database Value: 'DG' <br /> Model Value: 10 <br /> Domain API Value: 'Damage' |
| Other | Other value. Stored as 'OT'. <br /> Database Value: 'OT' <br /> Model Value: 11 <br /> Domain API Value: 'Other' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
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

### DefaultPaymentAccount

When not NULL specifies the default payment account to use associated with this payment type

Type: **[PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company to which this PaymentType applies, or null if it is for all enterprise companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  


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

[!list limit=1000 erp.entity=Finance.Payments.PaymentTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Payments.PaymentTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Payments_PaymentTypes

Domain API Entity Type: 
Finance_Payments_PaymentType

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Payments_PaymentTypes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Payments_PaymentTypes?$top=10>

