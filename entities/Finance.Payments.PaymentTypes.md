---
uid: Finance.Payments.PaymentTypes
---
# Finance.Payments.PaymentTypes Entity

**Namespace:** [Finance.Payments](Finance.Payments.md)  

Describes the way of payment. For example: in cash, by bank transfer, with credit card, etc. Entity: Cash_Payment_Types

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _2 - Track object changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Payments.PaymentTypes](Finance.Payments.PaymentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Finance.Payments.PaymentTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [Code](Finance.Payments.PaymentTypes.md#code) | string (16) | The payment type unique code. `Required` `Filter(eq;like)` `ORD` 
| [DisplayText](Finance.Payments.PaymentTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Finance.Payments.PaymentTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Payments.PaymentTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Finance.Payments.PaymentTypes.md#id) | guid |  
| [IsActive](Finance.Payments.PaymentTypes.md#isactive) | boolean | Indicates wheather the payment type is active and usable for choosing in new documents. `Required` `Default(true)` `Filter(eq)` `Introduced in version 19.1` 
| [Name](Finance.Payments.PaymentTypes.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this PaymentType. `Required` `Filter(like)` 
| [ObjectVersion](Finance.Payments.PaymentTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [SystemType](Finance.Payments.PaymentTypes.md#systemtype) | [SystemType](Finance.Payments.PaymentTypes.md#systemtype) __nullable__ | Not null only when this is one of the system payment types. CS=Cash; CD=By Card; BT=Bank Transfer. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultPaymentAccount](Finance.Payments.PaymentTypes.md#defaultpaymentaccount) | [PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable) | When not null specifies the default payment account to use associated with this payment type. `Filter(multi eq)` |
| [EnterpriseCompany](Finance.Payments.PaymentTypes.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this PaymentType applies, or null if it is for all enterprise companies. `Filter(multi eq)` |


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Code

The payment type unique code. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (16)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.IncMax( o => o.Code, null, "00000")`

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

### IsActive

Indicates wheather the payment type is active and usable for choosing in new documents. `Required` `Default(true)` `Filter(eq)` `Introduced in version 19.1`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

The name of this PaymentType. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### SystemType

Not null only when this is one of the system payment types. CS=Cash; CD=By Card; BT=Bank Transfer.

_Type_: **[SystemType](Finance.Payments.PaymentTypes.md#systemtype) __nullable__**  
_Category_: **System**  
Allowed values for the `SystemType`(Finance.Payments.PaymentTypes.md#systemtype) data attribute  
_Allowed Values (Finance.Payments.PaymentTypesRepository.SystemType Enum Members)_  

| Value | Description |
| ---- | --- |
| Cash | Cash value. Stored as 'CH'. <br /> _Database Value:_ 'CH' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Cash' |
| ByCard | ByCard value. Stored as 'CD'. <br /> _Database Value:_ 'CD' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ByCard' |
| BankTransfer | BankTransfer value. Stored as 'BT'. <br /> _Database Value:_ 'BT' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'BankTransfer' |
| Coupons | Coupons value. Stored as 'TK'. <br /> _Database Value:_ 'TK' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Coupons' |
| Check | Check value. Stored as 'CK'. <br /> _Database Value:_ 'CK' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Check' |
| UserDefined1 | UserDefined1 value. Stored as 'U1'. <br /> _Database Value:_ 'U1' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'UserDefined1' |
| UserDefined2 | UserDefined2 value. Stored as 'U2'. <br /> _Database Value:_ 'U2' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'UserDefined2' |
| Vouchers | Vouchers value. Stored as 'U3'. <br /> _Database Value:_ 'U3' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'Vouchers' |
| Packaging | Packaging value. Stored as 'PK'. <br /> _Database Value:_ 'PK' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'Packaging' |
| InternalUsage | InternalUsage value. Stored as 'IU'. <br /> _Database Value:_ 'IU' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'InternalUsage' |
| Damage | Damage value. Stored as 'DG'. <br /> _Database Value:_ 'DG' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'Damage' |
| Other | Other value. Stored as 'OT'. <br /> _Database Value:_ 'OT' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'Other' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DefaultPaymentAccount

When not null specifies the default payment account to use associated with this payment type. `Filter(multi eq)`

_Type_: **[PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company to which this PaymentType applies, or null if it is for all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  


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

