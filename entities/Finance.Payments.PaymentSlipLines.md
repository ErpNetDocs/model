---
uid: Finance.Payments.PaymentSlipLines
---
# Finance.Payments.PaymentSlipLines


Mass payment line, which is distribution of an amount among payment orders. Each record generates one payment transaction line.

## General
Namespace: [Finance.Payments](Finance.Payments.md)  
Repository: Finance.Payments.PaymentSlipLines  
Base Table: Cash_Payment_Slip_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {PaymentSlipAmount.PartyName:T}  
Search Members: PaymentSlipAmount.PartyName  
Name Member: PaymentSlipAmount.PartyName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Payments.PaymentSlipAmounts](Finance.Payments.PaymentSlipAmounts.md)  
Aggregate Root:  
[Finance.Payments.PaymentSlips](Finance.Payments.PaymentSlips.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Amount](Finance.Payments.PaymentSlipLines.md#amount) | [Amount (10, 2)](../data-types.md#amount) | The part of the total amount in the payment slip amount, that is distributed to the specified payment order[Currency: PaymentSlipAmount.PaymentSlip.DocumentCurrency] [Required] [Default(0)] 
| [CoveredOrderAmount](Finance.Payments.PaymentSlipLines.md#coveredorderamount) | [Amount (10, 2)](../data-types.md#amount) | The part of the original payment order amount, that is covered by this payment slip line[Currency: PaymentOrder.TotalAmountCurrency] [Required] [Default(0)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [PaymentOrder](Finance.Payments.PaymentSlipLines.md#paymentorder) | [PaymentOrders](Finance.Payments.PaymentOrders.md) | The payment order, that is covered by this payment slip line |
| [PaymentSlipAmount](Finance.Payments.PaymentSlipLines.md#paymentslipamount) | [PaymentSlipAmounts](Finance.Payments.PaymentSlipAmounts.md) | The <see cref="PaymentSlipAmount"/> to which this PaymentSlipLine belongs. `Required` `Filter(multi eq)` `ReadOnly` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Payments.PaymentSlipLines.md#id) | guid |  
| [ObjectVersion](Finance.Payments.PaymentSlipLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Payments.PaymentSlipLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Amount

The part of the total amount in the payment slip amount, that is distributed to the specified payment order[Currency: PaymentSlipAmount.PaymentSlip.DocumentCurrency] [Required] [Default(0)]

Type: **[Amount (10, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.CoveredOrderAmount.ConvertTo( obj.PaymentSlipAmount.PaymentSlip.DocumentCurrency, obj.PaymentSlipAmount.PaymentSlip.CurrencyDirectory)`
### CoveredOrderAmount

The part of the original payment order amount, that is covered by this payment slip line[Currency: PaymentOrder.TotalAmountCurrency] [Required] [Default(0)]

Type: **[Amount (10, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Amount.ConvertTo( obj.PaymentOrder.TotalAmountCurrency, obj.PaymentSlipAmount.PaymentSlip.CurrencyDirectory)`
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

### PaymentOrder

The payment order, that is covered by this payment slip line

Type: **[PaymentOrders](Finance.Payments.PaymentOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PaymentSlipAmount

The <see cref="PaymentSlipAmount"/> to which this PaymentSlipLine belongs. `Required` `Filter(multi eq)` `ReadOnly` `Owner`

Type: **[PaymentSlipAmounts](Finance.Payments.PaymentSlipAmounts.md)**  
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

[!list limit=1000 erp.entity=Finance.Payments.PaymentSlipLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Payments.PaymentSlipLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Payments_PaymentSlipLines

Domain API Entity Type: 
Finance_Payments_PaymentSlipLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Payments_PaymentSlipLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Payments_PaymentSlipLines?$top=10>

