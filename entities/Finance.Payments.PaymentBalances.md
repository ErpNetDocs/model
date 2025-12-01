---
uid: Finance.Payments.PaymentBalances
---
# Finance.Payments.PaymentBalances View

**Namespace:** [Finance.Payments](Finance.Payments.md)  

Represents the payment orders with their covered amounts. Entity: Cash_Payment_Balances_View (Introduced in version 23.1.0.79)

## Renames

Old name: **Finance.Payments.OrderBalances**  
New name: **Finance.Payments.PaymentBalances**  
Version: **25.1.2.86**  
Case: **38515**  



## Default Visualization
Default Display Text Format:  
_{OrderAmountValue}: {PaidAmountValue}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Payments.PaymentBalances](Finance.Payments.PaymentBalances.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Direction](Finance.Payments.PaymentBalances.md#direction) | [Direction](Finance.Payments.PaymentBalances.md#direction) | Indicates whether the remaining balance is an incoming receivable (to be collected) or an outgoing payable (to be paid). `Required` `Default("I")` `Filter(eq)` `Inherited from Cash_Payment_Orders_Table.Direction` 
| [DueDate](Finance.Payments.PaymentBalances.md#duedate) | datetime __nullable__ | The due date of the payment. null means there is no due date. `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Due_Date` 
| [DueStartDate](Finance.Payments.PaymentBalances.md#duestartdate) | date __nullable__ | The date at which the payment becomes executable. null means the payment is executable at all times. `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Due_Start_Date` 
| [DueStatus](Finance.Payments.PaymentBalances.md#duestatus) | [DueStatus](Finance.Payments.PaymentBalances.md#duestatus) | Due status of requested payment. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.74` 
| [IsInvoiced](Finance.Payments.PaymentBalances.md#isinvoiced) | boolean | When Is_Invoiced = true, then in the view results will be included only the Payment Orders which do have a RefInvoiceDocument. If Is_Invoiced = false, then in the view results will be included only the Payment Orders which do NOT have a RefInvoiceDocument. `Required` `Filter(multi eq)` 
| [OrderAmount](Finance.Payments.PaymentBalances.md#orderamount) | [Amount (18, 2)](../data-types.md#amount) | The total amount that should be paid. `Currency: Currency` `Required` `Default(0)` `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Total_Amount` 
| [PaidAmount](Finance.Payments.PaymentBalances.md#paidamount) | [Amount (38, 2)](../data-types.md#amount) | The paid amount. Taken from released payment transactions. `Currency: Currency` `Required` `Filter(eq;ge;le)` 
| [PaymentStatus](Finance.Payments.PaymentBalances.md#paymentstatus) | [PaymentStatus](Finance.Payments.PaymentBalances.md#paymentstatus) | Payment Status	. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.76` 
| [RefDocumentDate](Finance.Payments.PaymentBalances.md#refdocumentdate) | datetime __nullable__ | The date of the original document. null means that it is unknown. `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Ref_Document_Date` 
| [RefDocumentNo](Finance.Payments.PaymentBalances.md#refdocumentno) | string (20) | The number of the document which has created the payment order and is the basis for the payment. `Required` `Filter(eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Document_No` 
| [RefInvoiceDocumentDate](Finance.Payments.PaymentBalances.md#refinvoicedocumentdate) | datetime __nullable__ | The date of the related invoice. null means that the payment order isn't related to any invoice or the date is unknown. `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Ref_Invoice_Document_Date` 
| [RefInvoiceDocumentNo](Finance.Payments.PaymentBalances.md#refinvoicedocumentno) | string (20) __nullable__ | The number of the invoice which has created or is related to the payment order and is the basis for the payment. null means that the payment order isn't created or related to any invoice. `Filter(eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Invoice_Document_No` 
| [RemainingAmount](Finance.Payments.PaymentBalances.md#remainingamount) | [Amount (18, 2)](../data-types.md#amount) | The amount that remains to be paid. `Currency: Currency` `Required` `Filter(eq;ge;le)` `Introduced in version 25.1.2.79` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Currency](Finance.Payments.PaymentBalances.md#currency) | [Currencies](General.Currencies.Currencies.md) | The currency of amounts. `Required` `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Total_Amount_Currency_Id` |
| [EnterpriseCompany](Finance.Payments.PaymentBalances.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company which issued the document. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id` |
| [LocationParty](Finance.Payments.PaymentBalances.md#locationparty) | [Parties](General.Contacts.Parties.md) (nullable) | Location or sub-party of the Party_Id in the order. `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Location_Party_Id` |
| [Party](Finance.Payments.PaymentBalances.md#party) | [Parties](General.Contacts.Parties.md) | The party which is to pay or receive the amount. `Required` `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Party_Id` |
| [PaymentOrder](Finance.Payments.PaymentBalances.md#paymentorder) | [PaymentOrders](Finance.Payments.PaymentOrders.md) | The payment order. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Payment_Order_Id` |
| [RefDocument](Finance.Payments.PaymentBalances.md#refdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document which has created the payment order and is the basis for the payment. If this column is filled then Ref_Document_Type_Id, Ref_Document_No and Ref_Document_Date must be equal to the type, number and date of the specified document. `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Document_Id` |
| [RefDocumentType](Finance.Payments.PaymentBalances.md#refdocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The type of the document which has created the payment order and is the basis for the payment. `Required` `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Document_Type_Id` |
| [RefInvoiceDocument](Finance.Payments.PaymentBalances.md#refinvoicedocument) | [Documents](General.Documents.Documents.md) (nullable) | The invoice document which has created or is related to the payment order and is the basis for the payment. null means that the payment order isn't created or related to any invoice or the invoice isn't present in the database. If this column is filled then Ref_Invoice_Document_<br />Type_Id, Ref_Invoice_Document_No and Ref_Invoice_Document_Date must be equal to the type, number and date of the specified invoice document. `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Invoice_Document_Id` |
| [RefInvoiceDocumentType](Finance.Payments.PaymentBalances.md#refinvoicedocumenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | The document type of the invoice which has created or is related to the payment order and is the basis for the payment. null means that the payment order isn't created or related to any invoice. `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Invoice_Document_<br />Type_Id` |


## Attribute Details

### Direction

Indicates whether the remaining balance is an incoming receivable (to be collected) or an outgoing payable (to be paid). `Required` `Default("I")` `Filter(eq)` `Inherited from Cash_Payment_Orders_Table.Direction`

_Type_: **[Direction](Finance.Payments.PaymentBalances.md#direction)**  
_Category_: **System**  
Allowed values for the `Direction`(Finance.Payments.PaymentBalances.md#direction) data attribute  
_Allowed Values (Finance.Payments.PaymentBalancesRepository.Direction Enum Members)_  

| Value | Description |
| ---- | --- |
| Outgoing | Outgoing value. Stored as 'I'. <br /> _Database Value:_ 'I' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Outgoing' |
| Incoming | Incoming value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Incoming' |

_Inherited From_: **Cash_Payment_Orders_Table.Direction**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Outgoing**  
_Show in UI_: **ShownByDefault**  

### DueDate

The due date of the payment. null means there is no due date. `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Due_Date`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Due_Date**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DueStartDate

The date at which the payment becomes executable. null means the payment is executable at all times. `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Due_Start_Date`

_Type_: **date __nullable__**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Due_Start_Date**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DueStatus

Due status of requested payment. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.74`

_Type_: **[DueStatus](Finance.Payments.PaymentBalances.md#duestatus)**  
_Category_: **System**  
Allowed values for the `DueStatus`(Finance.Payments.PaymentBalances.md#duestatus) data attribute  
_Allowed Values (Finance.Payments.PaymentBalancesRepository.DueStatus Enum Members)_  

| Value | Description |
| ---- | --- |
| Scheduled | Payment is not yet applicable (before due start date).. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Scheduled' |
| Due | Payment is now payable and should be made before the due date.. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Due' |
| GracePeriod | Due date has passed, but still within the grace period (no penalties yet).. Stored as 'G'. <br /> _Database Value:_ 'G' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'GracePeriod' |
| Overdue | Grace period has ended, and payment is now late.. Stored as 'O'. <br /> _Database Value:_ 'O' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Overdue' |
| NotApplicable | Not Applicable for payment. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'NotApplicable' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### IsInvoiced

When Is_Invoiced = true, then in the view results will be included only the Payment Orders which do have a RefInvoiceDocument. If Is_Invoiced = false, then in the view results will be included only the Payment Orders which do NOT have a RefInvoiceDocument. `Required` `Filter(multi eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### OrderAmount

The total amount that should be paid. `Currency: Currency` `Required` `Default(0)` `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Total_Amount`

_Type_: **[Amount (18, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Total_Amount**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### PaidAmount

The paid amount. Taken from released payment transactions. `Currency: Currency` `Required` `Filter(eq;ge;le)`

_Type_: **[Amount (38, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### PaymentStatus

Payment Status	. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.76`

_Type_: **[PaymentStatus](Finance.Payments.PaymentBalances.md#paymentstatus)**  
_Category_: **System**  
Allowed values for the `PaymentStatus`(Finance.Payments.PaymentBalances.md#paymentstatus) data attribute  
_Allowed Values (Finance.Payments.PaymentBalancesRepository.PaymentStatus Enum Members)_  

| Value | Description |
| ---- | --- |
| Unpaid | No payment has been made yet.. Stored as 'UN'. <br /> _Database Value:_ 'UN' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Unpaid' |
| PartiallyPaid | A partial payment has been made, but the full amount is still outstanding.. Stored as 'PP'. <br /> _Database Value:_ 'PP' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'PartiallyPaid' |
| Paid | The full payment has been completed.. Stored as 'PA'. <br /> _Database Value:_ 'PA' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Paid' |
| Overpaid | More than the required amount has been paid.. Stored as 'OV'. <br /> _Database Value:_ 'OV' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Overpaid' |
| Other | The payment is made in the opposite direction.. Stored as 'ER'. <br /> _Database Value:_ 'ER' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Other' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### RefDocumentDate

The date of the original document. null means that it is unknown. `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Ref_Document_Date`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Ref_Document_Date**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.RefDocument.DocumentDate`

_Front-End Recalc Expressions:_  
`obj.RefDocument.DocumentDate`
### RefDocumentNo

The number of the document which has created the payment order and is the basis for the payment. `Required` `Filter(eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Document_No`

_Type_: **string (20)**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Ref_Document_No**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **20**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.RefDocument.DocumentNo`

_Front-End Recalc Expressions:_  
`obj.RefDocument.DocumentNo`
### RefInvoiceDocumentDate

The date of the related invoice. null means that the payment order isn't related to any invoice or the date is unknown. `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Ref_Invoice_Document_Date`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Ref_Invoice_Document_Date**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.RefInvoiceDocument.DocumentDate`

_Front-End Recalc Expressions:_  
`obj.RefInvoiceDocument.DocumentDate`
### RefInvoiceDocumentNo

The number of the invoice which has created or is related to the payment order and is the basis for the payment. null means that the payment order isn't created or related to any invoice. `Filter(eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Invoice_Document_No`

_Type_: **string (20) __nullable__**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Ref_Invoice_Document_No**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **20**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.RefInvoiceDocument.DocumentNo`

_Front-End Recalc Expressions:_  
`obj.RefInvoiceDocument.DocumentNo`
### RemainingAmount

The amount that remains to be paid. `Currency: Currency` `Required` `Filter(eq;ge;le)` `Introduced in version 25.1.2.79`

_Type_: **[Amount (18, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Currency

The currency of amounts. `Required` `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Total_Amount_Currency_Id`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Total_Amount_Currency_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

The enterprise company which issued the document. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Documents_Table.Enterprise_Company_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LocationParty

Location or sub-party of the Party_Id in the order. `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Location_Party_Id`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Location_Party_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Party

The party which is to pay or receive the amount. `Required` `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Party_Id`

_Type_: **[Parties](General.Contacts.Parties.md)**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Party_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PaymentOrder

The payment order. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Payment_Order_Id`

_Type_: **[PaymentOrders](Finance.Payments.PaymentOrders.md)**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Payment_Order_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### RefDocument

The document which has created the payment order and is the basis for the payment. If this column is filled then Ref_Document_Type_Id, Ref_Document_No and Ref_Document_Date must be equal to the type, number and date of the specified document. `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Document_Id`

_Type_: **[Documents](General.Documents.Documents.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Ref_Document_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### RefDocumentType

The type of the document which has created the payment order and is the basis for the payment. `Required` `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Document_Type_Id`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Ref_Document_Type_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.RefDocument.DocumentType`

_Front-End Recalc Expressions:_  
`obj.RefDocument.DocumentType`
### RefInvoiceDocument

The invoice document which has created or is related to the payment order and is the basis for the payment. null means that the payment order isn't created or related to any invoice or the invoice isn't present in the database. If this column is filled then Ref_Invoice_Document_Type_Id, Ref_Invoice_Document_No and Ref_Invoice_Document_Date must be equal to the type, number and date of the specified invoice document. `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Invoice_Document_Id`

_Type_: **[Documents](General.Documents.Documents.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Ref_Invoice_Document_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### RefInvoiceDocumentType

The document type of the invoice which has created or is related to the payment order and is the basis for the payment. null means that the payment order isn't created or related to any invoice. `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Invoice_Document_Type_Id`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Cash_Payment_Orders_Table.Ref_Invoice_Document_Type_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.RefInvoiceDocument.DocumentType`

_Front-End Recalc Expressions:_  
`obj.RefInvoiceDocument.DocumentType`

## API

Domain API Entity Set: 
Finance_Payments_PaymentBalances

Domain API Entity Type: 
Finance_Payments_PaymentBalance

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Payments_PaymentBalances?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Payments_PaymentBalances?$top=10>

