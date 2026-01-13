---
uid: Finance.Payments.BulkPaymentOrderLines
---
# Finance.Payments.BulkPaymentOrderLines Entity

**Namespace:** [Finance.Payments](Finance.Payments.md)  

Bulk payment order document line. Each line usually creates one payment order. Entity: Cash_Bulk_Payment_Order_Lines

## Default Visualization
Default Display Text Format:  
_{BulkPaymentOrder.EntityName}_  
Default Search Members:  
_BulkPaymentOrder.EntityName_  
Name Data Member:  
_BulkPaymentOrder.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Payments.BulkPaymentOrders](Finance.Payments.BulkPaymentOrders.md)  
Aggregate Root:  
[Finance.Payments.BulkPaymentOrders](Finance.Payments.BulkPaymentOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BillTo](Finance.Payments.BulkPaymentOrderLines.md#billto) | [BillTo](Finance.Payments.BulkPaymentOrderLines.md#billto) __nullable__ | If filled indicates which party is billed for the total amount. Possible values: 'C' = Company (means the Party_Id), 'L' = Company location (the Location_Party_Id), null = unidentified. 
| [Direction](Finance.Payments.BulkPaymentOrderLines.md#direction) | [Direction](Finance.Payments.BulkPaymentOrderLines.md#direction) | Indicates whether the remaining balance is an incoming receivable (to be collected) or an outgoing payable (to be paid). `Required` `Default("I")` `Filter(eq)` 
| [DisplayText](Finance.Payments.BulkPaymentOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DueDate](Finance.Payments.BulkPaymentOrderLines.md#duedate) | datetime __nullable__ | The due date of the payment. null means there is no due date. `Filter(ge;le)` 
| [Id](Finance.Payments.BulkPaymentOrderLines.md#id) | guid |  
| [InstallmentNumber](Finance.Payments.BulkPaymentOrderLines.md#installmentnumber) | int32 __nullable__ | Consequtive installment number. Used for identifying the payment when using payment plans. null means that the payment is not part of a payment plan. 
| [InvoiceAmount](Finance.Payments.BulkPaymentOrderLines.md#invoiceamount) | [Amount (18, 2)](../data-types.md#amount) __nullable__ | The specified invoice amount. (the invoice amount converted to the Total_Amount_Currency_Id must be equal to the Total_Amount). `Currency: InvoiceAmountCurrency` 
| [IsAmountWithVAT](Finance.Payments.BulkPaymentOrderLines.md#isamountwithvat) | boolean | Is_Amount_With_VAT=true if the requested amount includes VAT. `Required` `Default(true)` `Filter(eq)` 
| [Notes](Finance.Payments.BulkPaymentOrderLines.md#notes) | string (254) __nullable__ | Notes for this BulkPaymentOrderLine. 
| [ObjectVersion](Finance.Payments.BulkPaymentOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RefDocumentDate](Finance.Payments.BulkPaymentOrderLines.md#refdocumentdate) | datetime __nullable__ | The date of the base document. null means that it is unknown. `Filter(ge;le)` 
| [RefDocumentNo](Finance.Payments.BulkPaymentOrderLines.md#refdocumentno) | string (20) | The number of the document which is the basis for the payment. `Required` 
| [RefInvoiceApplyDate](Finance.Payments.BulkPaymentOrderLines.md#refinvoiceapplydate) | datetime __nullable__ | The apply date of the related invoice. Not specified when the payment order isn't related to any invoice or the apply date is unknown. `Filter(ge;le)` 
| [RefInvoiceDocumentDate](Finance.Payments.BulkPaymentOrderLines.md#refinvoicedocumentdate) | datetime __nullable__ | The date of the related invoice. null means that the payment order isn't related to any invoice or the date is unknown. `Filter(ge;le)` 
| [RefInvoiceDocumentNo](Finance.Payments.BulkPaymentOrderLines.md#refinvoicedocumentno) | string (20) __nullable__ | The number of the invoice which is related and is the basis for the payment. null means that the payment order isn't created or related to any invoice. 
| [TotalAmount](Finance.Payments.BulkPaymentOrderLines.md#totalamount) | [Amount (18, 2)](../data-types.md#amount) | Total amount that should be payed. `Currency: TotalAmountCurrency` `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BulkPaymentOrder](Finance.Payments.BulkPaymentOrderLines.md#bulkpaymentorder) | [BulkPaymentOrders](Finance.Payments.BulkPaymentOrders.md) | The <see cref="BulkPaymentOrder"/> to which this BulkPaymentOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [InvoiceAmountCurrency](Finance.Payments.BulkPaymentOrderLines.md#invoiceamountcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | The currency of Invoice Amount. `Filter(multi eq)` |
| [LocationParty](Finance.Payments.BulkPaymentOrderLines.md#locationparty) | [Parties](General.Contacts.Parties.md) (nullable) | Location or sub-party of the Party_Id. `Filter(multi eq)` |
| [Party](Finance.Payments.BulkPaymentOrderLines.md#party) | [Parties](General.Contacts.Parties.md) | The party which is to pay or receive the amount. `Required` `Filter(multi eq)` |
| [PaymentAccount](Finance.Payments.BulkPaymentOrderLines.md#paymentaccount) | [PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable) | When not null, specifies the payment account that is expected or will be used by the payment transaction. `Filter(multi eq)` |
| [PaymentType](Finance.Payments.BulkPaymentOrderLines.md#paymenttype) | [PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable) | Expected payment type. When null, there is no expectation for payment type. `Filter(multi eq)` |
| [RefDocumentType](Finance.Payments.BulkPaymentOrderLines.md#refdocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The type of the document which is the basis for the payment. `Required` `Filter(multi eq)` |
| [RefInvoiceDocumentType](Finance.Payments.BulkPaymentOrderLines.md#refinvoicedocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | The document type of the invoice which is related and is the basis for the payment. null means that the payment order isn't created or related to any invoice. `Filter(multi eq)` |
| [TotalAmountCurrency](Finance.Payments.BulkPaymentOrderLines.md#totalamountcurrency) | [Currencies](General.Currencies.Currencies.md) | The currency of Total Amount. `Required` `Filter(multi eq)` |


## Attribute Details

### BillTo

If filled indicates which party is billed for the total amount. Possible values: 'C' = Company (means the Party_Id), 'L' = Company location (the Location_Party_Id), null = unidentified.

_Type_: **[BillTo](Finance.Payments.BulkPaymentOrderLines.md#billto) __nullable__**  
_Category_: **System**  
Allowed values for the `BillTo`(Finance.Payments.BulkPaymentOrderLines.md#billto) data attribute  
_Allowed Values (Finance.Payments.BulkPaymentOrderLinesRepository.BillTo Enum Members)_  

| Value | Description |
| ---- | --- |
| Company | Company value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Company' |
| CompanyLocation | CompanyLocation value. Stored as 'L'. <br /> _Database Value:_ 'L' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'CompanyLocation' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### Direction

Indicates whether the remaining balance is an incoming receivable (to be collected) or an outgoing payable (to be paid). `Required` `Default("I")` `Filter(eq)`

_Type_: **[Direction](Finance.Payments.BulkPaymentOrderLines.md#direction)**  
_Category_: **System**  
Allowed values for the `Direction`(Finance.Payments.BulkPaymentOrderLines.md#direction) data attribute  
_Allowed Values (Finance.Payments.BulkPaymentOrderLinesRepository.Direction Enum Members)_  

| Value | Description |
| ---- | --- |
| Outgoing | Outgoing value. Stored as 'I'. <br /> _Database Value:_ 'I' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Outgoing' |
| Incoming | Incoming value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Incoming' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Outgoing**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DueDate

The due date of the payment. null means there is no due date. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### InstallmentNumber

Consequtive installment number. Used for identifying the payment when using payment plans. null means that the payment is not part of a payment plan.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### InvoiceAmount

The specified invoice amount. (the invoice amount converted to the Total_Amount_Currency_Id must be equal to the Total_Amount). `Currency: InvoiceAmountCurrency`

_Type_: **[Amount (18, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### IsAmountWithVAT

Is_Amount_With_VAT=true if the requested amount includes VAT. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this BulkPaymentOrderLine.

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

### RefDocumentDate

The date of the base document. null means that it is unknown. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### RefDocumentNo

The number of the document which is the basis for the payment. `Required`

_Type_: **string (20)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **20**  
_Show in UI_: **ShownByDefault**  

### RefInvoiceApplyDate

The apply date of the related invoice. Not specified when the payment order isn't related to any invoice or the apply date is unknown. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### RefInvoiceDocumentDate

The date of the related invoice. null means that the payment order isn't related to any invoice or the date is unknown. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### RefInvoiceDocumentNo

The number of the invoice which is related and is the basis for the payment. null means that the payment order isn't created or related to any invoice.

_Type_: **string (20) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **20**  
_Show in UI_: **HiddenByDefault**  

### TotalAmount

Total amount that should be payed. `Currency: TotalAmountCurrency` `Required` `Default(0)`

_Type_: **[Amount (18, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### BulkPaymentOrder

The <see cref="BulkPaymentOrder"/> to which this BulkPaymentOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[BulkPaymentOrders](Finance.Payments.BulkPaymentOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### InvoiceAmountCurrency

The currency of Invoice Amount. `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### LocationParty

Location or sub-party of the Party_Id. `Filter(multi eq)`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Party

The party which is to pay or receive the amount. `Required` `Filter(multi eq)`

_Type_: **[Parties](General.Contacts.Parties.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.LocationParty.ParentParty`
### PaymentAccount

When not null, specifies the payment account that is expected or will be used by the payment transaction. `Filter(multi eq)`

_Type_: **[PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.PaymentType.GetDefaultPaymentAccount( ).IfNullThen( obj.PaymentAccount)`
### PaymentType

Expected payment type. When null, there is no expectation for payment type. `Filter(multi eq)`

_Type_: **[PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### RefDocumentType

The type of the document which is the basis for the payment. `Required` `Filter(multi eq)`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### RefInvoiceDocumentType

The document type of the invoice which is related and is the basis for the payment. null means that the payment order isn't created or related to any invoice. `Filter(multi eq)`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### TotalAmountCurrency

The currency of Total Amount. `Required` `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.PaymentAccount.Currency`

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

