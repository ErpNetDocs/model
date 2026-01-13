---
uid: Crm.Pos.SalePayments
---
# Crm.Pos.SalePayments Entity

**Namespace:** [Crm.Pos](Crm.Pos.md)  

Specified only when a POS sale has multiple payments. Entity: Pos_Sale_Payments (Introduced in version 25.1.3.46)

## Default Visualization
Default Display Text Format:  
_{PosSale.DocumentNumber}_  
Default Search Members:  
_PosSale.DocumentNumber_  
Name Data Member:  
_PosSale.DocumentNumber_  
Category:  _Documents_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pos.Sales](Crm.Pos.Sales.md)  
Aggregate Root:  
[Crm.Pos.Sales](Crm.Pos.Sales.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Amount](Crm.Pos.SalePayments.md#amount) | [Amount (12, 2)](../data-types.md#amount) | Amount paid (in Amount Currency). `Currency: AmountCurrency` `Required` `Filter(eq;ge;le)` 
| [AmountBase](Crm.Pos.SalePayments.md#amountbase) | [Amount (12, 2)](../data-types.md#amount) | Amount in base currency. `Currency: PosSale.Location.EnterpriseCompany.BaseCurrency` `Required` `Filter(eq)` 
| [CreatedAt](Crm.Pos.SalePayments.md#createdat) | datetime | Timestamp of the payment event. `Required` `Default(Now)` `Filter(eq;ge;le)` 
| [DisplayText](Crm.Pos.SalePayments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Pos.SalePayments.md#id) | guid |  
| [Notes](Crm.Pos.SalePayments.md#notes) | string (128) __nullable__ | Notes for the sale payment. `Filter(like)` 
| [ObjectVersion](Crm.Pos.SalePayments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Reference](Crm.Pos.SalePayments.md#reference) | string (64) __nullable__ | Optional external reference (e.g. card transaction ID). `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AmountCurrency](Crm.Pos.SalePayments.md#amountcurrency) | [Currencies](General.Currencies.Currencies.md) | The currency of Amount. `Required` `Filter(multi eq)` |
| [PaymentType](Crm.Pos.SalePayments.md#paymenttype) | [PaymentTypes](Finance.Payments.PaymentTypes.md) | The payment type (method) for this payment. `Required` `Filter(multi eq)` |
| [PosSale](Crm.Pos.SalePayments.md#possale) | [Sales](Crm.Pos.Sales.md) | The POS sale to which this specifies a payment. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### Amount

Amount paid (in Amount Currency). `Currency: AmountCurrency` `Required` `Filter(eq;ge;le)`

_Type_: **[Amount (12, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### AmountBase

Amount in base currency. `Currency: PosSale.Location.EnterpriseCompany.BaseCurrency` `Required` `Filter(eq)`

_Type_: **[Amount (12, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CreatedAt

Timestamp of the payment event. `Required` `Default(Now)` `Filter(eq;ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

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
_Show in UI_: **CannotBeShown**  

### Notes

Notes for the sale payment. `Filter(like)`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Reference

Optional external reference (e.g. card transaction ID). `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AmountCurrency

The currency of Amount. `Required` `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PaymentType

The payment type (method) for this payment. `Required` `Filter(multi eq)`

_Type_: **[PaymentTypes](Finance.Payments.PaymentTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PosSale

The POS sale to which this specifies a payment. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Sales](Crm.Pos.Sales.md)**  
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

[!list limit=1000 erp.entity=Crm.Pos.SalePayments erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.SalePayments erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_SalePayments

Domain API Entity Type: 
Crm_Pos_SalePayment

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_SalePayments?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_SalePayments?$top=10>

