---
uid: Crm.Sales.SalesOrderPaymentPlans
---
# Crm.Sales.SalesOrderPaymentPlans


Payment plan of a sales order

## General
Namespace: [Crm.Sales](Crm.Sales.md)  
Repository: Crm.Sales.SalesOrderPaymentPlans  
Base Table: Crm_Sales_Order_Payment_Plans  
API access:  ReadWrite  

## Visualization
Display Format: {Id}. {SalesOrder.DocumentNo} {SalesOrder.DocumentType.TypeName:T}  
Search Members: SalesOrder.DocumentNo  
Name Member: SalesOrder.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Sales.SalesOrders](Crm.Sales.SalesOrders.md)  
Aggregate Root:  
[Crm.Sales.SalesOrders](Crm.Sales.SalesOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Amount](Crm.Sales.SalesOrderPaymentPlans.md#amount) | [Amount (14, 2)](../data-types.md#amount) | Amount to be payed.[Currency: SalesOrder.DocumentCurrency] [Required] 
| [AmountPercent](Crm.Sales.SalesOrderPaymentPlans.md#amountpercent) | decimal (7, 6) __nullable__ | Percent of the sales order amount to be payed. 
| [DueDateFormMethod](Crm.Sales.SalesOrderPaymentPlans.md#duedateformmethod) | [PaymentPlanDueDateSource](Crm.Sales.SalesOrderPaymentPlans.md#duedateformmethod) | Method to determine the payment due date.[Required] 
| [ExplicitPaymentDueDate](Crm.Sales.SalesOrderPaymentPlans.md#explicitpaymentduedate) | datetime __nullable__ | Explicitly specified payment due date. Must be filled if and only if explicitly setting the date is chosen in due date form method.[Filter(ge;le)] 
| [ExplicitPayment<br />DueStartDate](Crm.Sales.SalesOrderPaymentPlans.md#explicitpaymentduestartdate) | date __nullable__ | Explicitly specified date on which the payment becomes executable. Can be specified only when date formation method is 'Set explicit date'.[Filter(ge;le)] 
| [InstallmentNumber](Crm.Sales.SalesOrderPaymentPlans.md#installmentnumber) | int32 | Consequtive installment number. Used for identifying different payments generated according this payment plan.[Required] 
| [Notes](Crm.Sales.SalesOrderPaymentPlans.md#notes) | string (254) __nullable__ | Notes for this SalesOrderPaymentPlan. 
| [PaymentAmount](Crm.Sales.SalesOrderPaymentPlans.md#paymentamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | The amount the customer is expected to pay in that specific payment currency.[Currency: PaymentCurrency] [Filter(eq;ge;le)] [Introduced in version 26.2.0.53] 
| [PaymentStartDays](Crm.Sales.SalesOrderPaymentPlans.md#paymentstartdays) | int32 | Number of days until the payment becomes executable. The days are counted, starting with the date, specified by due date formation method.[Required] [Default(0)] 
| [PaymentTermDays](Crm.Sales.SalesOrderPaymentPlans.md#paymenttermdays) | int32 | Payment term in days, which are to be added to form the payment due date. 0 means that the date determined by the due date form method and the explicit payment due date is taken as due date.[Required] [Default(0)] 
| [Remainder](Crm.Sales.SalesOrderPaymentPlans.md#remainder) | boolean | Indicates whether this amount is the remainder of the document - e. g. the total amount of the sales order minus explicitly specified by 'Amount percent' or 'Amount' columns amounts in the payment plan.[Required] [Default(false)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Crm.Sales.SalesOrderPaymentPlans.md#document) | [SalesOrders](Crm.Sales.SalesOrders.md) | The owner document. The <see cref="SalesOrder"/> to which this SalesOrderPaymentPlan belongs. `Required` `Filter(multi eq)` |
| [PaymentAccount](Crm.Sales.SalesOrderPaymentPlans.md#paymentaccount) | [PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable) | Specifies the payment account towards which the payment is expected. NULL means that there is no expectation for payment account. For POS implementations, this can be used to denote the payment account in which the payment actually occurred. |
| [PaymentCurrency](Crm.Sales.SalesOrderPaymentPlans.md#paymentcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Defines the currency of the PaymentAmount. |
| [PaymentType](Crm.Sales.SalesOrderPaymentPlans.md#paymenttype) | [PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable) | Specifies the expected payment type. NULL means that there is no expected payment type. For POS implementations, this can be used to denote the payment type which actually occurred. |
| [SalesOrder](Crm.Sales.SalesOrderPaymentPlans.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) | The <see cref="SalesOrder"/> to which this SalesOrderPaymentPlan belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Sales.SalesOrderPaymentPlans.md#id) | guid |  
| [ObjectVersion](Crm.Sales.SalesOrderPaymentPlans.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Sales.SalesOrderPaymentPlans.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Amount

Amount to be payed.[Currency: SalesOrder.DocumentCurrency] [Required]

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.PaymentCurrency == null) OrElse ( obj.PaymentAmount == null)), obj.Amount, obj.SetAmount( ))`
### AmountPercent

Percent of the sales order amount to be payed.

Type: **decimal (7, 6) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DueDateFormMethod

Method to determine the payment due date.[Required]

Type: **[PaymentPlanDueDateSource](Crm.Sales.SalesOrderPaymentPlans.md#duedateformmethod)**  
Category: **System**  
Generic enum type for PaymentPlanDueDateSource properties  
Allowed Values (Crm.Sales.PaymentPlanDueDateSource Enum Members)  

| Value | Description |
| ---- | --- |
| SpecifyTheDateExplicitly | SpecifyTheDateExplicitly value. Stored as 'EXP'. <br /> Database Value: 'EXP' <br /> Model Value: 0 <br /> Domain API Value: 'SpecifyTheDateExplicitly' |
| UseInvoiceDate | UseInvoiceDate value. Stored as 'INV'. <br /> Database Value: 'INV' <br /> Model Value: 1 <br /> Domain API Value: 'UseInvoiceDate' |
| UseSalesOrderDate | UseSalesOrderDate value. Stored as 'SLS'. <br /> Database Value: 'SLS' <br /> Model Value: 2 <br /> Domain API Value: 'UseSalesOrderDate' |
| UseSalesOrderDueDate | UseSalesOrderDueDate value. Stored as 'SDD'. <br /> Database Value: 'SDD' <br /> Model Value: 3 <br /> Domain API Value: 'UseSalesOrderDueDate' |
| UseInvoiceDueDate | UseInvoiceDueDate value. Stored as 'IDD'. <br /> Database Value: 'IDD' <br /> Model Value: 4 <br /> Domain API Value: 'UseInvoiceDueDate' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExplicitPaymentDueDate

Explicitly specified payment due date. Must be filled if and only if explicitly setting the date is chosen in due date form method.[Filter(ge;le)]

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( Convert( obj.DueDateFormMethod, Int32) != 0), null, obj.ExplicitPaymentDueDate)`
### ExplicitPaymentDueStartDate

Explicitly specified date on which the payment becomes executable. Can be specified only when date formation method is 'Set explicit date'.[Filter(ge;le)]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( Convert( obj.DueDateFormMethod, Int32) != 0), null, obj.ExplicitPaymentDueStartDate)`
### InstallmentNumber

Consequtive installment number. Used for identifying different payments generated according this payment plan.[Required]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.SalesOrder.PaymentPlans.Select( c => c.InstallmentNumber).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.SalesOrder.PaymentPlans.Select( c => c.InstallmentNumber).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this SalesOrderPaymentPlan.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### PaymentAmount

The amount the customer is expected to pay in that specific payment currency.[Currency: PaymentCurrency] [Filter(eq;ge;le)] [Introduced in version 26.2.0.53]

Type: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.PaymentCurrency == null), null, IIF( ( ( obj.Amount != null) OrElse True), obj.SetPaymentAmount( ), obj.PaymentAmount))`
### PaymentStartDays

Number of days until the payment becomes executable. The days are counted, starting with the date, specified by due date formation method.[Required] [Default(0)]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### PaymentTermDays

Payment term in days, which are to be added to form the payment due date. 0 means that the date determined by the due date form method and the explicit payment due date is taken as due date.[Required] [Default(0)]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( ( Convert( obj.DueDateFormMethod, Int32) == 3) OrElse ( Convert( obj.DueDateFormMethod, Int32) == 4)), 0, obj.PaymentTermDays)`

Front-End Recalc Expressions:  
`IIF( ( ( Convert( obj.DueDateFormMethod, Int32) == 3) OrElse ( Convert( obj.DueDateFormMethod, Int32) == 4)), 0, obj.PaymentTermDays)`
### Remainder

Indicates whether this amount is the remainder of the document - e. g. the total amount of the sales order minus explicitly specified by 'Amount percent' or 'Amount' columns amounts in the payment plan.[Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( obj.AmountPercent != null), False, obj.Remainder)`

Front-End Recalc Expressions:  
`IIF( ( obj.AmountPercent != null), False, obj.Remainder)`
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

### Document

The owner document. The <see cref="SalesOrder"/> to which this SalesOrderPaymentPlan belongs. `Required` `Filter(multi eq)`

Type: **[SalesOrders](Crm.Sales.SalesOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PaymentAccount

Specifies the payment account towards which the payment is expected. NULL means that there is no expectation for payment account. For POS implementations, this can be used to denote the payment account in which the payment actually occurred.

Type: **[PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SalesOrder.PaymentAccount`

Front-End Recalc Expressions:  
`obj.SalesOrder.PaymentAccount.IfNullThen( obj.PaymentType.DefaultPaymentAccount.IfNullThen( obj.PaymentAccount))`
`obj.SalesOrder.PaymentAccount`
### PaymentCurrency

Defines the currency of the PaymentAmount.

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.PaymentAccount != null), obj.PaymentAccount.Currency, null)`
### PaymentType

Specifies the expected payment type. NULL means that there is no expected payment type. For POS implementations, this can be used to denote the payment type which actually occurred.

Type: **[PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SalesOrder.PaymentType`

Front-End Recalc Expressions:  
`obj.SalesOrder.PaymentType`
### SalesOrder

The <see cref="SalesOrder"/> to which this SalesOrderPaymentPlan belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[SalesOrders](Crm.Sales.SalesOrders.md)**  
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

[!list limit=1000 erp.entity=Crm.Sales.SalesOrderPaymentPlans erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Sales.SalesOrderPaymentPlans erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Sales_SalesOrderPaymentPlans

Domain API Entity Type: 
Crm_Sales_SalesOrderPaymentPlan

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Sales_SalesOrderPaymentPlans?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Sales_SalesOrderPaymentPlans?$top=10>

