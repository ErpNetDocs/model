---
uid: Finance.Payments.BulkPaymentOrderLines
---
# Finance.Payments.BulkPaymentOrderLines


Bulk payment order document line. Each line usually creates one payment order.

## General
Namespace: [Finance.Payments](Finance.Payments.md)  
Repository: Finance.Payments.BulkPaymentOrderLines  
Base Table: Cash_Bulk_Payment_Order_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {BulkPaymentOrder.EntityName}  
Search Members: BulkPaymentOrder.EntityName  
Name Member: BulkPaymentOrder.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Payments.BulkPaymentOrders](Finance.Payments.BulkPaymentOrders.md)  
Aggregate Root:  
[Finance.Payments.BulkPaymentOrders](Finance.Payments.BulkPaymentOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BillTo](Finance.Payments.BulkPaymentOrderLines.md#billto) | [BillTo](Finance.Payments.BulkPaymentOrderLines.md#billto) __nullable__ | If filled indicates which party is billed for the total amount. Possible values: 'C' = Company (means the Party_Id), 'L' = Company location (the Location_Party_Id), NULL = unidentified 
| [Direction](Finance.Payments.BulkPaymentOrderLines.md#direction) | [Direction](Finance.Payments.BulkPaymentOrderLines.md#direction) | Indicates whether the remaining balance is an incoming receivable (to be collected) or an outgoing payable (to be paid). 
| [DueDate](Finance.Payments.BulkPaymentOrderLines.md#duedate) | datetime __nullable__ | The due date of the payment. NULL means there is no due date 
| [InstallmentNumber](Finance.Payments.BulkPaymentOrderLines.md#installmentnumber) | int32 __nullable__ | Consequtive installment number. Used for identifying the payment when using payment plans. NULL means that the payment is not part of a payment plan 
| [InvoiceAmount](Finance.Payments.BulkPaymentOrderLines.md#invoiceamount) | [Amount (18, 2)](../data-types.md#amount) __nullable__ | The specified invoice amount. (the invoice amount converted to the Total_Amount_Currency_Id must be equal to the Total_Amount) 
| [IsAmountWithVAT](Finance.Payments.BulkPaymentOrderLines.md#isamountwithvat) | boolean | Is_Amount_With_VAT=1 if the requested amount includes VAT 
| [Notes](Finance.Payments.BulkPaymentOrderLines.md#notes) | string (254) __nullable__ | Notes for this BulkPaymentOrderLine. 
| [RefDocumentDate](Finance.Payments.BulkPaymentOrderLines.md#refdocumentdate) | datetime __nullable__ | The date of the base document. NULL means that it is unknown 
| [RefDocumentNo](Finance.Payments.BulkPaymentOrderLines.md#refdocumentno) | string (20) | The number of the document which is the basis for the payment 
| [RefInvoiceApplyDate](Finance.Payments.BulkPaymentOrderLines.md#refinvoiceapplydate) | datetime __nullable__ | The apply date of the related invoice. Not specified when the payment order isn't related to any invoice or the apply date is unknown. 
| [RefInvoiceDocumentDate](Finance.Payments.BulkPaymentOrderLines.md#refinvoicedocumentdate) | datetime __nullable__ | The date of the related invoice. NULL means that the payment order isn't related to any invoice or the date is unknown. 
| [RefInvoiceDocumentNo](Finance.Payments.BulkPaymentOrderLines.md#refinvoicedocumentno) | string (20) __nullable__ | The number of the invoice which is related and is the basis for the payment. NULL means that the payment order isn't created or related to any invoice. 
| [TotalAmount](Finance.Payments.BulkPaymentOrderLines.md#totalamount) | [Amount (18, 2)](../data-types.md#amount) | Total amount that should be payed 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BulkPaymentOrder](Finance.Payments.BulkPaymentOrderLines.md#bulkpaymentorder) | [BulkPaymentOrders](Finance.Payments.BulkPaymentOrders.md) | The <see cref="BulkPaymentOrder"/> to which this BulkPaymentOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [InvoiceAmountCurrency](Finance.Payments.BulkPaymentOrderLines.md#invoiceamountcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | The currency of Invoice Amount |
| [LocationParty](Finance.Payments.BulkPaymentOrderLines.md#locationparty) | [Parties](General.Contacts.Parties.md) (nullable) | Location or sub-party of the Party_Id |
| [Party](Finance.Payments.BulkPaymentOrderLines.md#party) | [Parties](General.Contacts.Parties.md) | The party which is to pay or receive the amount |
| [PaymentAccount](Finance.Payments.BulkPaymentOrderLines.md#paymentaccount) | [PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable) | When not NULL, specifies the payment account that is expected or will be used by the payment transaction |
| [PaymentType](Finance.Payments.BulkPaymentOrderLines.md#paymenttype) | [PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable) | Expected payment type. When null, there is no expectation for payment type. |
| [RefDocumentType](Finance.Payments.BulkPaymentOrderLines.md#refdocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The type of the document which is the basis for the payment |
| [RefInvoiceDocumentType](Finance.Payments.BulkPaymentOrderLines.md#refinvoicedocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | The document type of the invoice which is related and is the basis for the payment. NULL means that the payment order isn't created or related to any invoice. |
| [TotalAmountCurrency](Finance.Payments.BulkPaymentOrderLines.md#totalamountcurrency) | [Currencies](General.Currencies.Currencies.md) | The currency of Total Amount |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Payments.BulkPaymentOrderLines.md#id) | guid |  
| [ObjectVersion](Finance.Payments.BulkPaymentOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Payments.BulkPaymentOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BillTo

If filled indicates which party is billed for the total amount. Possible values: 'C' = Company (means the Party_Id), 'L' = Company location (the Location_Party_Id), NULL = unidentified

Type: **[BillTo](Finance.Payments.BulkPaymentOrderLines.md#billto) __nullable__**  
Category: **System**  
Allowed values for the `BillTo`(Finance.Payments.BulkPaymentOrderLines.md#billto) data attribute  
Allowed Values (Finance.Payments.BulkPaymentOrderLinesRepository.BillTo Enum Members)  

| Value | Description |
| ---- | --- |
| Company | Company value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 0 <br /> Domain API Value: 'Company' |
| CompanyLocation | CompanyLocation value. Stored as 'L'. <br /> Database Value: 'L' <br /> Model Value: 1 <br /> Domain API Value: 'CompanyLocation' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Direction

Indicates whether the remaining balance is an incoming receivable (to be collected) or an outgoing payable (to be paid).

Type: **[Direction](Finance.Payments.BulkPaymentOrderLines.md#direction)**  
Category: **System**  
Allowed values for the `Direction`(Finance.Payments.BulkPaymentOrderLines.md#direction) data attribute  
Allowed Values (Finance.Payments.BulkPaymentOrderLinesRepository.Direction Enum Members)  

| Value | Description |
| ---- | --- |
| Outgoing | Outgoing value. Stored as 'I'. <br /> Database Value: 'I' <br /> Model Value: 0 <br /> Domain API Value: 'Outgoing' |
| Incoming | Incoming value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 1 <br /> Domain API Value: 'Incoming' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Outgoing**  
Show in UI: **ShownByDefault**  

### DueDate

The due date of the payment. NULL means there is no due date

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InstallmentNumber

Consequtive installment number. Used for identifying the payment when using payment plans. NULL means that the payment is not part of a payment plan

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InvoiceAmount

The specified invoice amount. (the invoice amount converted to the Total_Amount_Currency_Id must be equal to the Total_Amount)

Type: **[Amount (18, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### IsAmountWithVAT

Is_Amount_With_VAT=1 if the requested amount includes VAT

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this BulkPaymentOrderLine.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### RefDocumentDate

The date of the base document. NULL means that it is unknown

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### RefDocumentNo

The number of the document which is the basis for the payment

Type: **string (20)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **20**  
Show in UI: **ShownByDefault**  

### RefInvoiceApplyDate

The apply date of the related invoice. Not specified when the payment order isn't related to any invoice or the apply date is unknown.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### RefInvoiceDocumentDate

The date of the related invoice. NULL means that the payment order isn't related to any invoice or the date is unknown.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### RefInvoiceDocumentNo

The number of the invoice which is related and is the basis for the payment. NULL means that the payment order isn't created or related to any invoice.

Type: **string (20) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **20**  
Show in UI: **HiddenByDefault**  

### TotalAmount

Total amount that should be payed

Type: **[Amount (18, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
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

### BulkPaymentOrder

The <see cref="BulkPaymentOrder"/> to which this BulkPaymentOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[BulkPaymentOrders](Finance.Payments.BulkPaymentOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### InvoiceAmountCurrency

The currency of Invoice Amount

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### LocationParty

Location or sub-party of the Party_Id

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Party

The party which is to pay or receive the amount

Type: **[Parties](General.Contacts.Parties.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.LocationParty.ParentParty`
### PaymentAccount

When not NULL, specifies the payment account that is expected or will be used by the payment transaction

Type: **[PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.PaymentType.GetDefaultPaymentAccount( ).IfNullThen( obj.PaymentAccount)`
### PaymentType

Expected payment type. When null, there is no expectation for payment type.

Type: **[PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### RefDocumentType

The type of the document which is the basis for the payment

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### RefInvoiceDocumentType

The document type of the invoice which is related and is the basis for the payment. NULL means that the payment order isn't created or related to any invoice.

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### TotalAmountCurrency

The currency of Total Amount

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.PaymentAccount.Currency`

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

[!list limit=1000 erp.entity=Finance.Payments.BulkPaymentOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Payments.BulkPaymentOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Payments_BulkPaymentOrderLines

Domain API Entity Type: 
Finance_Payments_BulkPaymentOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Payments_BulkPaymentOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Payments_BulkPaymentOrderLines?$top=10>

