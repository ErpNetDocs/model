---
uid: Crm.Sales.SalesOrderPaymentPlans
---
# Crm.Sales.SalesOrderPaymentPlans Entity

**Namespace:** [Crm.Sales](Crm.Sales.md)  

Payment plan of a sales order. Entity: Crm_Sales_Order_Payment_Plans

## Default Visualization
Default Display Text Format:  
_{Id}. {SalesOrder.DocumentNo} {SalesOrder.DocumentType.TypeName:T}_  
Default Search Members:  
_SalesOrder.DocumentNo_  
Name Data Member:  
_SalesOrder.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Sales.SalesOrders](Crm.Sales.SalesOrders.md)  
Aggregate Root:  
[Crm.Sales.SalesOrders](Crm.Sales.SalesOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Amount](Crm.Sales.SalesOrderPaymentPlans.md#amount) | [Amount (14, 2)](../data-types.md#amount) | Amount to be payed. `Currency: SalesOrder.DocumentCurrency` `Required` 
| [AmountPercent](Crm.Sales.SalesOrderPaymentPlans.md#amountpercent) | decimal (7, 6) __nullable__ | Percent of the sales order amount to be payed. 
| [DisplayText](Crm.Sales.SalesOrderPaymentPlans.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DueDateFormMethod](Crm.Sales.SalesOrderPaymentPlans.md#duedateformmethod) | [PaymentPlanDueDateSource](Crm.Sales.SalesOrderPaymentPlans.md#duedateformmethod) | Method to determine the payment due date. SLS = Use sales order date, INV = Use invoice date, EXP = Specify the date explicitly, SDD = Sales order due date, IDD = Invoice due date. `Required` 
| [ExplicitPaymentDueDate](Crm.Sales.SalesOrderPaymentPlans.md#explicitpaymentduedate) | datetime __nullable__ | Explicitly specified payment due date. Must be filled if and only if Due_Date_Form_Method = 'EXP'. `Filter(ge;le)` 
| [ExplicitPayment<br />DueStartDate](Crm.Sales.SalesOrderPaymentPlans.md#explicitpaymentduestartdate) | date __nullable__ | Explicitly specified date on which the payment becomes executable. Can be specified only when date formation method is 'Set explicit date'. `Filter(ge;le)` 
| [Id](Crm.Sales.SalesOrderPaymentPlans.md#id) | guid |  
| [InstallmentNumber](Crm.Sales.SalesOrderPaymentPlans.md#installmentnumber) | int32 | Consequtive installment number. Used for identifying different payments generated according this payment plan. `Required` 
| [Notes](Crm.Sales.SalesOrderPaymentPlans.md#notes) | string (254) __nullable__ | Notes for this SalesOrderPaymentPlan. 
| [ObjectVersion](Crm.Sales.SalesOrderPaymentPlans.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PaymentAmount](Crm.Sales.SalesOrderPaymentPlans.md#paymentamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | The amount the customer is expected to pay in that specific payment currency. `Currency: PaymentCurrency` `Filter(eq;ge;le)` `Introduced in version 26.2.0.53` 
| [PaymentStartDays](Crm.Sales.SalesOrderPaymentPlans.md#paymentstartdays) | int32 | Number of days until the payment becomes executable. The days are counted, starting with the date, specified by due date formation method. `Required` `Default(0)` 
| [PaymentTermDays](Crm.Sales.SalesOrderPaymentPlans.md#paymenttermdays) | int32 | Payment term in days, which are to be added to form the payment due date. 0 means that the date determined by Due_Date_Form_Method and Explicit_Payment_Due_Date is taken as due date. `Required` `Default(0)` 
| [Remainder](Crm.Sales.SalesOrderPaymentPlans.md#remainder) | boolean | Indicates wheather this amount is the remainder of the document. Amount = Total amount of the sales order - explicitly specified amounts in the plan (by Amount_Percent or Amount). `Required` `Default(false)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Crm.Sales.SalesOrderPaymentPlans.md#document) | [SalesOrders](Crm.Sales.SalesOrders.md) | The owner document. The <see cref="SalesOrder"/> to which this SalesOrderPaymentPlan belongs. `Required` `Filter(multi eq)` |
| [PaymentAccount](Crm.Sales.SalesOrderPaymentPlans.md#paymentaccount) | [PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable) | Specifies the payment account towards which the payment is expected. null means that there is no expectation for payment account. For POS implementations, this can be used to denote the payment account in which the payment actually occurred. `Filter(multi eq)` |
| [PaymentCurrency](Crm.Sales.SalesOrderPaymentPlans.md#paymentcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Defines the currency of the PaymentAmount. `Filter(multi eq)` `Introduced in version 26.2.0.53` |
| [PaymentType](Crm.Sales.SalesOrderPaymentPlans.md#paymenttype) | [PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable) | Specifies the expected payment type. null means that there is no expected payment type. For POS implementations, this can be used to denote the payment type which actually occurred. `Filter(multi eq)` |
| [SalesOrder](Crm.Sales.SalesOrderPaymentPlans.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) | The <see cref="SalesOrder"/> to which this SalesOrderPaymentPlan belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### Amount

Amount to be payed. `Currency: SalesOrder.DocumentCurrency` `Required`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### AmountPercent

Percent of the sales order amount to be payed.

_Type_: **decimal (7, 6) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DueDateFormMethod

Method to determine the payment due date. SLS = Use sales order date, INV = Use invoice date, EXP = Specify the date explicitly, SDD = Sales order due date, IDD = Invoice due date. `Required`

_Type_: **[PaymentPlanDueDateSource](Crm.Sales.SalesOrderPaymentPlans.md#duedateformmethod)**  
_Category_: **System**  
Generic enum type for PaymentPlanDueDateSource properties  
_Allowed Values (Crm.Sales.PaymentPlanDueDateSource Enum Members)_  

| Value | Description |
| ---- | --- |
| SpecifyTheDateExplicitly | SpecifyTheDateExplicitly value. Stored as 'EXP'. <br /> _Database Value:_ 'EXP' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'SpecifyTheDateExplicitly' |
| UseInvoiceDate | UseInvoiceDate value. Stored as 'INV'. <br /> _Database Value:_ 'INV' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'UseInvoiceDate' |
| UseSalesOrderDate | UseSalesOrderDate value. Stored as 'SLS'. <br /> _Database Value:_ 'SLS' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'UseSalesOrderDate' |
| UseSalesOrderDueDate | UseSalesOrderDueDate value. Stored as 'SDD'. <br /> _Database Value:_ 'SDD' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'UseSalesOrderDueDate' |
| UseInvoiceDueDate | UseInvoiceDueDate value. Stored as 'IDD'. <br /> _Database Value:_ 'IDD' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'UseInvoiceDueDate' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ExplicitPaymentDueDate

Explicitly specified payment due date. Must be filled if and only if Due_Date_Form_Method = 'EXP'. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( Convert( obj.DueDateFormMethod, Int32) != 0), null, obj.ExplicitPaymentDueDate)`
### ExplicitPaymentDueStartDate

Explicitly specified date on which the payment becomes executable. Can be specified only when date formation method is 'Set explicit date'. `Filter(ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( Convert( obj.DueDateFormMethod, Int32) != 0), null, obj.ExplicitPaymentDueStartDate)`
### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### InstallmentNumber

Consequtive installment number. Used for identifying different payments generated according this payment plan. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.SalesOrder.PaymentPlans.Select( c => c.InstallmentNumber).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.SalesOrder.PaymentPlans.Select( c => c.InstallmentNumber).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this SalesOrderPaymentPlan.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PaymentAmount

The amount the customer is expected to pay in that specific payment currency. `Currency: PaymentCurrency` `Filter(eq;ge;le)` `Introduced in version 26.2.0.53`

_Type_: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### PaymentStartDays

Number of days until the payment becomes executable. The days are counted, starting with the date, specified by due date formation method. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### PaymentTermDays

Payment term in days, which are to be added to form the payment due date. 0 means that the date determined by Due_Date_Form_Method and Explicit_Payment_Due_Date is taken as due date. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( Convert( obj.DueDateFormMethod, Int32) == 3) OrElse ( Convert( obj.DueDateFormMethod, Int32) == 4)), 0, obj.PaymentTermDays)`

_Front-End Recalc Expressions:_  
`IIF( ( ( Convert( obj.DueDateFormMethod, Int32) == 3) OrElse ( Convert( obj.DueDateFormMethod, Int32) == 4)), 0, obj.PaymentTermDays)`
### Remainder

Indicates wheather this amount is the remainder of the document. Amount = Total amount of the sales order - explicitly specified amounts in the plan (by Amount_Percent or Amount). `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`IIF( ( obj.AmountPercent != null), False, obj.Remainder)`

_Front-End Recalc Expressions:_  
`IIF( ( obj.AmountPercent != null), False, obj.Remainder)`

## Reference Details

### Document

The owner document. The <see cref="SalesOrder"/> to which this SalesOrderPaymentPlan belongs. `Required` `Filter(multi eq)`

_Type_: **[SalesOrders](Crm.Sales.SalesOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PaymentAccount

Specifies the payment account towards which the payment is expected. null means that there is no expectation for payment account. For POS implementations, this can be used to denote the payment account in which the payment actually occurred. `Filter(multi eq)`

_Type_: **[PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.SalesOrder.PaymentAccount`

_Front-End Recalc Expressions:_  
`obj.SalesOrder.PaymentAccount.IfNullThen( obj.PaymentType.DefaultPaymentAccount.IfNullThen( obj.PaymentAccount))`
`obj.SalesOrder.PaymentAccount`
### PaymentCurrency

Defines the currency of the PaymentAmount. `Filter(multi eq)` `Introduced in version 26.2.0.53`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.PaymentAccount != null), obj.PaymentAccount.Currency, null)`
### PaymentType

Specifies the expected payment type. null means that there is no expected payment type. For POS implementations, this can be used to denote the payment type which actually occurred. `Filter(multi eq)`

_Type_: **[PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.SalesOrder.PaymentType`

_Front-End Recalc Expressions:_  
`obj.SalesOrder.PaymentType`
### SalesOrder

The <see cref="SalesOrder"/> to which this SalesOrderPaymentPlan belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[SalesOrders](Crm.Sales.SalesOrders.md)**  
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

