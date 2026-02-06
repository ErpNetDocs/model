---
uid: Logistics.Procurement.PurchaseControlDocumentLines
---
# Logistics.Procurement.PurchaseControlDocumentLines


The detail line of purchase control data. The purchase control is used to tally all orders and execuctions in the purchasing module.

## General
Namespace: [Logistics.Procurement](Logistics.Procurement.md)  
Repository: Logistics.Procurement.PurchaseControlDocumentLines  
Base Table: Scm_Purchase_Control_Document_Lines  
Introduced In Version: 18.2  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {PurchaseControlDocument.DocumentNo} {PurchaseControlDocument.DocumentType.TypeName:T}  
Search Members: PurchaseControlDocument.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Procurement.PurchaseControlDocuments](Logistics.Procurement.PurchaseControlDocuments.md)  
Aggregate Root:  
[Logistics.Procurement.PurchaseControlDocuments](Logistics.Procurement.PurchaseControlDocuments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConfirmedAmountBase](Logistics.Procurement.PurchaseControlDocumentLines.md#confirmedamountbase) | decimal (14, 2) __nullable__ | The amount (in base currency) of the ordered items, confirmed by the supplier (usually with Purchase Confirmation). Null when the logged operation did not involve confirming ordered items. 
| [ConfirmedStandard<br />QuantityBase](Logistics.Procurement.PurchaseControlDocumentLines.md#confirmedstandardquantitybase) | decimal (12, 3) __nullable__ | The standard quantity of the ordered items, confirmed by the supplier (usually with Purchase Confirmation) in base measurement unit. Null when the logged operation did not involve confirming ordered items. 
| [InvoicedAmountBase](Logistics.Procurement.PurchaseControlDocumentLines.md#invoicedamountbase) | decimal (14, 2) __nullable__ | The amount (in base currency) of the invoiced items (usually with Purchase Invoice). Null when the logged operation did not involve invoicing items. 
| [InvoicedStandard<br />QuantityBase](Logistics.Procurement.PurchaseControlDocumentLines.md#invoicedstandardquantitybase) | decimal (12, 3) __nullable__ | The standard quantity of the invoiced items (usually with Purchase Invoice) in base measurement unit. Null when the logged operation did not involve invoicing items. 
| [LineNo](Logistics.Procurement.PurchaseControlDocumentLines.md#lineno) | int32 | The consecutive line number within the control document. 
| [Notes](Logistics.Procurement.PurchaseControlDocumentLines.md#notes) | string (max) __nullable__ | Notes for this PurchaseControl<br />DocumentLine. 
| [OrderedAmountBase](Logistics.Procurement.PurchaseControlDocumentLines.md#orderedamountbase) | decimal (14, 2) __nullable__ | The amount (in base currency) of the ordered items (usually with Purchase Order). Null when the logged operation did not involve ordering items. 
| [OrderedStandard<br />QuantityBase](Logistics.Procurement.PurchaseControlDocumentLines.md#orderedstandardquantitybase) | decimal (12, 3) __nullable__ | The standard quantity of the ordered items (usually with Purchase Order) in base measurement unit. Null when the logged operation did not involve ordering items. 
| [ReceivedAmountBase](Logistics.Procurement.PurchaseControlDocumentLines.md#receivedamountbase) | decimal (14, 2) __nullable__ | The amount (in base currency) of the received items (usually with Receiving Order). Null when the logged operation did not involve receiving items. 
| [ReceivedStandard<br />QuantityBase](Logistics.Procurement.PurchaseControlDocumentLines.md#receivedstandardquantitybase) | decimal (12, 3) __nullable__ | The standard quantity of the received items (usually with Receiving Order) in base measurement unit. Null when the logged operation did not involve receiving items. 
| [RequestedAmountBase](Logistics.Procurement.PurchaseControlDocumentLines.md#requestedamountbase) | decimal (14, 2) __nullable__ | The amount (in base currency) of the requested items (usually with Purchase Requisition). Null when the logged operation did not involve requesting items. 
| [RequestedStandard<br />QuantityBase](Logistics.Procurement.PurchaseControlDocumentLines.md#requestedstandardquantitybase) | decimal (12, 3) __nullable__ | The standard quantity of the requested items (usually with Purchase Requisition) in base measurement unit. Null when the logged operation did not involve requesting items. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [<s>Document</s>](Logistics.Procurement.PurchaseControlDocumentLines.md#document) | [PurchaseControlDocuments](Logistics.Procurement.PurchaseControlDocuments.md) | **OBSOLETE! Do not use!** The owner document. The <see cref="Purchase<br />ControlDocument"/> to which this PurchaseControl<br />DocumentLine belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` |
| [<s>PurchaseControlDocument</s>](Logistics.Procurement.PurchaseControlDocumentLines.md#purchasecontroldocument) | [PurchaseControlDocuments](Logistics.Procurement.PurchaseControlDocuments.md) | **OBSOLETE! Do not use!** The <see cref="Purchase<br />ControlDocument"/> to which this PurchaseControl<br />DocumentLine belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` `Obsolete` `Owner` |
| [PurchaseInvoice](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaseinvoice) | [PurchaseInvoices](Logistics.Procurement.PurchaseInvoices.md) (nullable) | The purchase invoice which is to be or was executed. Null when the data is unknown. |
| [PurchaseInvoiceLine](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaseinvoiceline) | [PurchaseInvoiceLines](Logistics.Procurement.PurchaseInvoiceLines.md) (nullable) | The purchase invoice line which is to be or was executed. Null when the data is unknown. |
| [<s>PurchaseOperationType</s>](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaseoperationtype) | [PurchaseOperationTypes](Logistics.Procurement.PurchaseOperationTypes.md) (nullable) | **OBSOLETE! Do not use!** The user-defined operation type, which is being recorded by the current line. Used for better grouping of the control entries. NULL when the operation type was not specified by the user. |
| [PurchaseOrder](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaseorder) | [PurchaseOrders](Logistics.Procurement.PurchaseOrders.md) (nullable) | The purchase order which is to be or was executed. Null when the data is unknown. |
| [PurchaseOrderLine](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaseorderline) | [PurchaseOrderLines](Logistics.Procurement.PurchaseOrderLines.md) (nullable) | The purchase order line which is to be or was executed. Null when the data is unknown. |
| [PurchaseRequisition](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaserequisition) | [Requisitions](Logistics.Procurement.Requisitions.md) (nullable) | The purchase requisition which is to be or was executed. Null when the data is unknown. |
| [PurchaseRequisitionLine](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaserequisitionline) | [RequisitionLines](Logistics.Procurement.RequisitionLines.md) (nullable) | The purchase requisition line which is to be or was executed. Null when the data is unknown. |
| [ReceivingOrder](Logistics.Procurement.PurchaseControlDocumentLines.md#receivingorder) | [ReceivingOrders](Logistics.Procurement.ReceivingOrders.md) (nullable) | The receiving order which is to be or was executed. Null when the data is unknown. |
| [ReceivingOrderLine](Logistics.Procurement.PurchaseControlDocumentLines.md#receivingorderline) | [ReceivingOrderLines](Logistics.Procurement.ReceivingOrderLines.md) (nullable) | The receiving order line which is to be or was executed. Null when the data is unknown. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Procurement.PurchaseControlDocumentLines.md#id) | guid |  
| [ObjectVersion](Logistics.Procurement.PurchaseControlDocumentLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Procurement.PurchaseControlDocumentLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConfirmedAmountBase

The amount (in base currency) of the ordered items, confirmed by the supplier (usually with Purchase Confirmation). Null when the logged operation did not involve confirming ordered items.

Type: **decimal (14, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConfirmedStandardQuantityBase

The standard quantity of the ordered items, confirmed by the supplier (usually with Purchase Confirmation) in base measurement unit. Null when the logged operation did not involve confirming ordered items.

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InvoicedAmountBase

The amount (in base currency) of the invoiced items (usually with Purchase Invoice). Null when the logged operation did not involve invoicing items.

Type: **decimal (14, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InvoicedStandardQuantityBase

The standard quantity of the invoiced items (usually with Purchase Invoice) in base measurement unit. Null when the logged operation did not involve invoicing items.

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineNo

The consecutive line number within the control document.

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this PurchaseControlDocumentLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### OrderedAmountBase

The amount (in base currency) of the ordered items (usually with Purchase Order). Null when the logged operation did not involve ordering items.

Type: **decimal (14, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OrderedStandardQuantityBase

The standard quantity of the ordered items (usually with Purchase Order) in base measurement unit. Null when the logged operation did not involve ordering items.

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReceivedAmountBase

The amount (in base currency) of the received items (usually with Receiving Order). Null when the logged operation did not involve receiving items.

Type: **decimal (14, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReceivedStandardQuantityBase

The standard quantity of the received items (usually with Receiving Order) in base measurement unit. Null when the logged operation did not involve receiving items.

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### RequestedAmountBase

The amount (in base currency) of the requested items (usually with Purchase Requisition). Null when the logged operation did not involve requesting items.

Type: **decimal (14, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### RequestedStandardQuantityBase

The standard quantity of the requested items (usually with Purchase Requisition) in base measurement unit. Null when the logged operation did not involve requesting items.

Type: **decimal (12, 3) __nullable__**  
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

### Document

**OBSOLETE! Do not use!** The owner document. The <see cref="PurchaseControlDocument"/> to which this PurchaseControlDocumentLine belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.1.2`

Type: **[PurchaseControlDocuments](Logistics.Procurement.PurchaseControlDocuments.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PurchaseControlDocument

**OBSOLETE! Do not use!** The <see cref="PurchaseControlDocument"/> to which this PurchaseControlDocumentLine belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` `Obsolete` `Owner`

Type: **[PurchaseControlDocuments](Logistics.Procurement.PurchaseControlDocuments.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### PurchaseInvoice

The purchase invoice which is to be or was executed. Null when the data is unknown.

Type: **[PurchaseInvoices](Logistics.Procurement.PurchaseInvoices.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PurchaseInvoiceLine

The purchase invoice line which is to be or was executed. Null when the data is unknown.

Type: **[PurchaseInvoiceLines](Logistics.Procurement.PurchaseInvoiceLines.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PurchaseOperationType

**OBSOLETE! Do not use!** The user-defined operation type, which is being recorded by the current line. Used for better grouping of the control entries. NULL when the operation type was not specified by the user.

Type: **[PurchaseOperationTypes](Logistics.Procurement.PurchaseOperationTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PurchaseOrder

The purchase order which is to be or was executed. Null when the data is unknown.

Type: **[PurchaseOrders](Logistics.Procurement.PurchaseOrders.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PurchaseOrderLine

The purchase order line which is to be or was executed. Null when the data is unknown.

Type: **[PurchaseOrderLines](Logistics.Procurement.PurchaseOrderLines.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PurchaseRequisition

The purchase requisition which is to be or was executed. Null when the data is unknown.

Type: **[Requisitions](Logistics.Procurement.Requisitions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PurchaseRequisitionLine

The purchase requisition line which is to be or was executed. Null when the data is unknown.

Type: **[RequisitionLines](Logistics.Procurement.RequisitionLines.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ReceivingOrder

The receiving order which is to be or was executed. Null when the data is unknown.

Type: **[ReceivingOrders](Logistics.Procurement.ReceivingOrders.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ReceivingOrderLine

The receiving order line which is to be or was executed. Null when the data is unknown.

Type: **[ReceivingOrderLines](Logistics.Procurement.ReceivingOrderLines.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Logistics.Procurement.PurchaseControlDocumentLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Procurement.PurchaseControlDocumentLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Procurement_PurchaseControlDocumentLines

Domain API Entity Type: 
Logistics_Procurement_PurchaseControlDocumentLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Procurement_PurchaseControlDocumentLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Procurement_PurchaseControlDocumentLines?$top=10>

