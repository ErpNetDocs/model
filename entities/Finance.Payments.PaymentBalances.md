---
uid: Finance.Payments.PaymentBalances
---
# Finance.Payments.PaymentBalances (View)


The Payment Balances report provides an overview of all outstanding payment amounts and their statuses. It includes both incoming (receivables) and outgoing (payables) balances, consolidating data from various financial documents such as invoices, credit notes, and general payment orders.

## General
Namespace: [Finance.Payments](Finance.Payments.md)  
Repository: Finance.Payments.PaymentBalances  
Introduced In Version: 23.1.0.79  
API access:  ReadWrite  

## Renames

Old name: Finance.Payments.OrderBalances  
New name: Finance.Payments.PaymentBalances  
Version: 25.1.2.86  
Case: 38515  



## Visualization
Display Format: {OrderAmountValue}: {PaidAmountValue}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

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

Type: **[Direction](Finance.Payments.PaymentBalances.md#direction)**  
Category: **System**  
Allowed values for the `Direction`(Finance.Payments.PaymentBalances.md#direction) data attribute  
Allowed Values (Finance.Payments.PaymentBalancesRepository.Direction Enum Members)  

| Value | Description |
| ---- | --- |
| Outgoing | Outgoing value. Stored as 'I'. <br /> Database Value: 'I' <br /> Model Value: 0 <br /> Domain API Value: 'Outgoing' |
| Incoming | Incoming value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 1 <br /> Domain API Value: 'Incoming' |

Inherited From: **Cash_Payment_Orders_Table.Direction**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Outgoing**  
Show in UI: **ShownByDefault**  

### DueDate

The due date of the payment. null means there is no due date. `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Due_Date`

Type: **datetime __nullable__**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Due_Date**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DueStartDate

The date at which the payment becomes executable. null means the payment is executable at all times. `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Due_Start_Date`

Type: **date __nullable__**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Due_Start_Date**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DueStatus

Due status of requested payment. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.74`

Type: **[DueStatus](Finance.Payments.PaymentBalances.md#duestatus)**  
Category: **System**  
Allowed values for the `DueStatus`(Finance.Payments.PaymentBalances.md#duestatus) data attribute  
Allowed Values (Finance.Payments.PaymentBalancesRepository.DueStatus Enum Members)  

| Value | Description |
| ---- | --- |
| Scheduled | Payment is not yet applicable (before due start date).. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 0 <br /> Domain API Value: 'Scheduled' |
| Due | Payment is now payable and should be made before the due date.. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 1 <br /> Domain API Value: 'Due' |
| GracePeriod | Due date has passed, but still within the grace period (no penalties yet).. Stored as 'G'. <br /> Database Value: 'G' <br /> Model Value: 2 <br /> Domain API Value: 'GracePeriod' |
| Overdue | Grace period has ended, and payment is now late.. Stored as 'O'. <br /> Database Value: 'O' <br /> Model Value: 3 <br /> Domain API Value: 'Overdue' |
| NotApplicable | Not Applicable for payment. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 4 <br /> Domain API Value: 'NotApplicable' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsInvoiced

When Is_Invoiced = true, then in the view results will be included only the Payment Orders which do have a RefInvoiceDocument. If Is_Invoiced = false, then in the view results will be included only the Payment Orders which do NOT have a RefInvoiceDocument. `Required` `Filter(multi eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OrderAmount

The total amount that should be paid. `Currency: Currency` `Required` `Default(0)` `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Total_Amount`

Type: **[Amount (18, 2)](../data-types.md#amount)**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Total_Amount**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### PaidAmount

The paid amount. Taken from released payment transactions. `Currency: Currency` `Required` `Filter(eq;ge;le)`

Type: **[Amount (38, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PaymentStatus

Payment Status	. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.76`

Type: **[PaymentStatus](Finance.Payments.PaymentBalances.md#paymentstatus)**  
Category: **System**  
Allowed values for the `PaymentStatus`(Finance.Payments.PaymentBalances.md#paymentstatus) data attribute  
Allowed Values (Finance.Payments.PaymentBalancesRepository.PaymentStatus Enum Members)  

| Value | Description |
| ---- | --- |
| Unpaid | No payment has been made yet.. Stored as 'UN'. <br /> Database Value: 'UN' <br /> Model Value: 0 <br /> Domain API Value: 'Unpaid' |
| PartiallyPaid | A partial payment has been made, but the full amount is still outstanding.. Stored as 'PP'. <br /> Database Value: 'PP' <br /> Model Value: 1 <br /> Domain API Value: 'PartiallyPaid' |
| Paid | The full payment has been completed.. Stored as 'PA'. <br /> Database Value: 'PA' <br /> Model Value: 2 <br /> Domain API Value: 'Paid' |
| Overpaid | More than the required amount has been paid.. Stored as 'OV'. <br /> Database Value: 'OV' <br /> Model Value: 3 <br /> Domain API Value: 'Overpaid' |
| Other | The payment is made in the opposite direction.. Stored as 'ER'. <br /> Database Value: 'ER' <br /> Model Value: 4 <br /> Domain API Value: 'Other' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### RefDocumentDate

The date of the original document. null means that it is unknown. `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Ref_Document_Date`

Type: **datetime __nullable__**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Ref_Document_Date**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.RefDocument.DocumentDate`

Front-End Recalc Expressions:  
`obj.RefDocument.DocumentDate`
### RefDocumentNo

The number of the document which has created the payment order and is the basis for the payment. `Required` `Filter(eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Document_No`

Type: **string (20)**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Ref_Document_No**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **20**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.RefDocument.DocumentNo`

Front-End Recalc Expressions:  
`obj.RefDocument.DocumentNo`
### RefInvoiceDocumentDate

The date of the related invoice. null means that the payment order isn't related to any invoice or the date is unknown. `Filter(eq;ge;le)` `Inherited from Cash_Payment_Orders_Table.Ref_Invoice_Document_Date`

Type: **datetime __nullable__**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Ref_Invoice_Document_Date**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.RefInvoiceDocument.DocumentDate`

Front-End Recalc Expressions:  
`obj.RefInvoiceDocument.DocumentDate`
### RefInvoiceDocumentNo

The number of the invoice which has created or is related to the payment order and is the basis for the payment. null means that the payment order isn't created or related to any invoice. `Filter(eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Invoice_Document_No`

Type: **string (20) __nullable__**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Ref_Invoice_Document_No**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **20**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.RefInvoiceDocument.DocumentNo`

Front-End Recalc Expressions:  
`obj.RefInvoiceDocument.DocumentNo`
### RemainingAmount

The amount that remains to be paid. `Currency: Currency` `Required` `Filter(eq;ge;le)` `Introduced in version 25.1.2.79`

Type: **[Amount (18, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### Currency

The currency of amounts. `Required` `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Total_Amount_Currency_Id`

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Total_Amount_Currency_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The enterprise company which issued the document. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Inherited From: **Gen_Documents_Table.Enterprise_Company_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LocationParty

Location or sub-party of the Party_Id in the order. `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Location_Party_Id`

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Location_Party_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Party

The party which is to pay or receive the amount. `Required` `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Party_Id`

Type: **[Parties](General.Contacts.Parties.md)**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Party_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PaymentOrder

The payment order. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Payment_Order_Id`

Type: **[PaymentOrders](Finance.Payments.PaymentOrders.md)**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Payment_Order_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### RefDocument

The document which has created the payment order and is the basis for the payment. If this column is filled then Ref_Document_Type_Id, Ref_Document_No and Ref_Document_Date must be equal to the type, number and date of the specified document. `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Document_Id`

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Ref_Document_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### RefDocumentType

The type of the document which has created the payment order and is the basis for the payment. `Required` `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Document_Type_Id`

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Ref_Document_Type_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.RefDocument.DocumentType`

Front-End Recalc Expressions:  
`obj.RefDocument.DocumentType`
### RefInvoiceDocument

The invoice document which has created or is related to the payment order and is the basis for the payment. null means that the payment order isn't created or related to any invoice or the invoice isn't present in the database. If this column is filled then Ref_Invoice_Document_Type_Id, Ref_Invoice_Document_No and Ref_Invoice_Document_Date must be equal to the type, number and date of the specified invoice document. `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Invoice_Document_Id`

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Ref_Invoice_Document_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### RefInvoiceDocumentType

The document type of the invoice which has created or is related to the payment order and is the basis for the payment. null means that the payment order isn't created or related to any invoice. `Filter(multi eq)` `Inherited from Cash_Payment_Orders_Table.Ref_Invoice_Document_Type_Id`

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
Category: **System**  
Inherited From: **Cash_Payment_Orders_Table.Ref_Invoice_Document_Type_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.RefInvoiceDocument.DocumentType`

Front-End Recalc Expressions:  
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

