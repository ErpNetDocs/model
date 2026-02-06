---
uid: Crm.Pos.SalePayments
---
# Crm.Pos.SalePayments


Specified only when a POS sale has multiple payments.

## General
Namespace: [Crm.Pos](Crm.Pos.md)  
Repository: Crm.Pos.SalePayments  
Base Table: Pos_Sale_Payments  
Introduced In Version: 25.1.3.46  
API access:  ReadWrite  

## Visualization
Display Format: {PosSale.DocumentNumber}  
Search Members: PosSale.DocumentNumber  
Name Member: PosSale.DocumentNumber  
Category:  Documents  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pos.Sales](Crm.Pos.Sales.md)  
Aggregate Root:  
[Crm.Pos.Sales](Crm.Pos.Sales.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Amount](Crm.Pos.SalePayments.md#amount) | [Amount (12, 2)](../data-types.md#amount) | Amount paid (in Amount Currency).[Currency: AmountCurrency] [Required] [Filter(eq;ge;le)] 
| [AmountBase](Crm.Pos.SalePayments.md#amountbase) | [Amount (12, 2)](../data-types.md#amount) | Amount in base currency.[Currency: PosSale.Location.EnterpriseCompany.BaseCurrency] [Required] [Filter(eq)] 
| [CreatedAt](Crm.Pos.SalePayments.md#createdat) | datetime | Timestamp of the payment event.[Required] [Default(Now)] [Filter(eq;ge;le)] 
| [Notes](Crm.Pos.SalePayments.md#notes) | string (128) __nullable__ | Notes for the sale payment.[Filter(like)] 
| [Reference](Crm.Pos.SalePayments.md#reference) | string (64) __nullable__ | Optional external reference (e.g. card transaction ID).[Filter(eq;like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AmountCurrency](Crm.Pos.SalePayments.md#amountcurrency) | [Currencies](General.Currencies.Currencies.md) | The currency of Amount. |
| [PaymentType](Crm.Pos.SalePayments.md#paymenttype) | [PaymentTypes](Finance.Payments.PaymentTypes.md) | The payment type (method) for this payment. |
| [PosSale](Crm.Pos.SalePayments.md#possale) | [Sales](Crm.Pos.Sales.md) | The POS sale to which this specifies a payment. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pos.SalePayments.md#id) | guid |  
| [ObjectVersion](Crm.Pos.SalePayments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Pos.SalePayments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Amount

Amount paid (in Amount Currency).[Currency: AmountCurrency] [Required] [Filter(eq;ge;le)]

Type: **[Amount (12, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AmountBase

Amount in base currency.[Currency: PosSale.Location.EnterpriseCompany.BaseCurrency] [Required] [Filter(eq)]

Type: **[Amount (12, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreatedAt

Timestamp of the payment event.[Required] [Default(Now)] [Filter(eq;ge;le)]

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### Notes

Notes for the sale payment.[Filter(like)]

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### Reference

Optional external reference (e.g. card transaction ID).[Filter(eq;like)]

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
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

### AmountCurrency

The currency of Amount.

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PaymentType

The payment type (method) for this payment.

Type: **[PaymentTypes](Finance.Payments.PaymentTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PosSale

The POS sale to which this specifies a payment.

Type: **[Sales](Crm.Pos.Sales.md)**  
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

