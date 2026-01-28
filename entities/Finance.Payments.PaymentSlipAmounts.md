---
uid: Finance.Payments.PaymentSlipAmounts
---
# Finance.Payments.PaymentSlipAmounts


Mass payment amount. Each record generates one payment transaction.

## General
Namespace: [Finance.Payments](Finance.Payments.md)  
Repository: Finance.Payments.PaymentSlipAmounts  
Base Table: Cash_Payment_Slip_Amounts  
API access:  ReadWrite  

## Visualization
Display Format: {PartyName:T}  
Search Members: PartyName  
Name Member: PartyName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Payments.PaymentSlips](Finance.Payments.PaymentSlips.md)  
Aggregate Root:  
[Finance.Payments.PaymentSlips](Finance.Payments.PaymentSlips.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](Finance.Payments.PaymentSlipAmounts.md#description) | string (254) __nullable__ | Description of the payed amount. The numbers of the documents which are payed for example. 
| [Direction](Finance.Payments.PaymentSlipAmounts.md#direction) | [Direction](Finance.Payments.PaymentSlipAmounts.md#direction) | Indicates whether the remaining balance is an incoming receivable (to be collected) or an outgoing payable (to be paid). `Required` `Filter(eq)` 
| [IsPartyPayment](Finance.Payments.PaymentSlipAmounts.md#ispartypayment) | boolean | Indicates whether the amount is payed or received by party or not (i.e. the amount is for fee, tax, etc.). `Required` `Default(true)` 
| [LineNo](Finance.Payments.PaymentSlipAmounts.md#lineno) | int32 | The number of the line within the payment. `Required` 
| [PartyName](Finance.Payments.PaymentSlipAmounts.md#partyname) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | The name of the party that is paying or receiving the money. The column can be left blank if there is no party involved (e.g. the amount is fee). 
| [PaymentDate](Finance.Payments.PaymentSlipAmounts.md#paymentdate) | datetime | The date on which the payment is done. `Required` `Filter(ge;le)` 
| [TotalAmount](Finance.Payments.PaymentSlipAmounts.md#totalamount) | [Amount (18, 2)](../data-types.md#amount) __nullable__ | The total amount payed. The distribution of the amount amongst the payment orders for this party is specified with payment slip lines. If null the total amount is calculated as sum of the amounts in the payment slip lines. `Currency: PaymentSlip.DocumentCurrency` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Party](Finance.Payments.PaymentSlipAmounts.md#party) | [Parties](General.Contacts.Parties.md) (nullable) | The party that is paying or receiving the money. The column can be left blank if there is no party involved (e.g. the amount is fee) or the party isn't present in the database yet. `Filter(multi eq)` |
| [PaymentReason](Finance.Payments.PaymentSlipAmounts.md#paymentreason) | [PaymentReasons](Finance.Payments.PaymentReasons.md) (nullable) | The reason for the payment, as defined in Payment Reasons. `Filter(multi eq)` |
| [PaymentSlip](Finance.Payments.PaymentSlipAmounts.md#paymentslip) | [PaymentSlips](Finance.Payments.PaymentSlips.md) | The <see cref="PaymentSlip"/> to which this PaymentSlipAmount belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Payments.PaymentSlipAmounts.md#id) | guid |  
| [ObjectVersion](Finance.Payments.PaymentSlipAmounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Payments.PaymentSlipAmounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| PaymentSlipLines | [PaymentSlipLines](Finance.Payments.PaymentSlipLines.md) | List of `PaymentSlipLine`(Finance.Payments.PaymentSlipLines.md) child objects, based on the `Finance.Payments.PaymentSlipLine.PaymentSlipAmount`(Finance.Payments.PaymentSlipLines.md#paymentslipamount) back reference 


## Attribute Details

### Description

Description of the payed amount. The numbers of the documents which are payed for example.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Direction

Indicates whether the remaining balance is an incoming receivable (to be collected) or an outgoing payable (to be paid). `Required` `Filter(eq)`

Type: **[Direction](Finance.Payments.PaymentSlipAmounts.md#direction)**  
Category: **System**  
Allowed values for the `Direction`(Finance.Payments.PaymentOrders.md#direction) data attribute  
Allowed Values (Finance.Payments.PaymentOrdersRepository.Direction Enum Members)  

| Value | Description |
| ---- | --- |
| Outgoing | Outgoing value. Stored as 'I'. <br /> Database Value: 'I' <br /> Model Value: 0 <br /> Domain API Value: 'Outgoing' |
| Incoming | Incoming value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 1 <br /> Domain API Value: 'Incoming' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsPartyPayment

Indicates whether the amount is payed or received by party or not (i.e. the amount is for fee, tax, etc.). `Required` `Default(true)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **CannotBeShown**  

### LineNo

The number of the line within the payment. `Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.PaymentSlip.Amounts.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.PaymentSlip.Amounts.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### PartyName

The name of the party that is paying or receiving the money. The column can be left blank if there is no party involved (e.g. the amount is fee).

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Party.ObtainPartyName( )`
### PaymentDate

The date on which the payment is done. `Required` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.PaymentSlip.DocumentDate`
### TotalAmount

The total amount payed. The distribution of the amount amongst the payment orders for this party is specified with payment slip lines. If null the total amount is calculated as sum of the amounts in the payment slip lines. `Currency: PaymentSlip.DocumentCurrency`

Type: **[Amount (18, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Party

The party that is paying or receiving the money. The column can be left blank if there is no party involved (e.g. the amount is fee) or the party isn't present in the database yet. `Filter(multi eq)`

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PaymentReason

The reason for the payment, as defined in Payment Reasons. `Filter(multi eq)`

Type: **[PaymentReasons](Finance.Payments.PaymentReasons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PaymentSlip

The <see cref="PaymentSlip"/> to which this PaymentSlipAmount belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[PaymentSlips](Finance.Payments.PaymentSlips.md)**  
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

[!list limit=1000 erp.entity=Finance.Payments.PaymentSlipAmounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Payments.PaymentSlipAmounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Payments_PaymentSlipAmounts

Domain API Entity Type: 
Finance_Payments_PaymentSlipAmount

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Payments_PaymentSlipAmounts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Payments_PaymentSlipAmounts?$top=10>

