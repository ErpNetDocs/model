---
uid: Logistics.Procurement.PurchaseControlDocumentLines
---
# Logistics.Procurement.PurchaseControlDocumentLines Entity

**Namespace:** [Logistics.Procurement](Logistics.Procurement.md)  

The detail line of purchase control data. The purchase control is used to tally all orders and execuctions in the purchasing module. Entity: Scm_Purchase_Control_Document_Lines (Introduced in version 18.2)

## Default Visualization
Default Display Text Format:  
_{LineNo}. {PurchaseControlDocument.DocumentNo} {PurchaseControlDocument.DocumentType.TypeName:T}_  
Default Search Members:  
_PurchaseControlDocument.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Logistics.Procurement.PurchaseControlDocumentLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Logistics.Procurement.PurchaseControlDocumentLines.md#id) | guid |  
| [InvoicedAmountBase](Logistics.Procurement.PurchaseControlDocumentLines.md#invoicedamountbase) | decimal (14, 2) __nullable__ | The amount (in base currency) of the invoiced items (usually with Purchase Invoice). Null when the logged operation did not involve invoicing items. 
| [InvoicedStandard<br />QuantityBase](Logistics.Procurement.PurchaseControlDocumentLines.md#invoicedstandardquantitybase) | decimal (12, 3) __nullable__ | The standard quantity of the invoiced items (usually with Purchase Invoice) in base measurement unit. Null when the logged operation did not involve invoicing items. 
| [LineNo](Logistics.Procurement.PurchaseControlDocumentLines.md#lineno) | int32 | The consecutive line number within the control document. `Required` 
| [Notes](Logistics.Procurement.PurchaseControlDocumentLines.md#notes) | string (max) __nullable__ | Notes for this PurchaseControl<br />DocumentLine. 
| [ObjectVersion](Logistics.Procurement.PurchaseControlDocumentLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [OrderedAmountBase](Logistics.Procurement.PurchaseControlDocumentLines.md#orderedamountbase) | decimal (14, 2) __nullable__ | The amount (in base currency) of the ordered items (usually with Purchase Order). Null when the logged operation did not involve ordering items. 
| [OrderedStandard<br />QuantityBase](Logistics.Procurement.PurchaseControlDocumentLines.md#orderedstandardquantitybase) | decimal (12, 3) __nullable__ | The standard quantity of the ordered items (usually with Purchase Order) in base measurement unit. Null when the logged operation did not involve ordering items. 
| [ReceivedAmountBase](Logistics.Procurement.PurchaseControlDocumentLines.md#receivedamountbase) | decimal (14, 2) __nullable__ | The amount (in base currency) of the received items (usually with Receiving Order). Null when the logged operation did not involve receiving items. 
| [ReceivedStandard<br />QuantityBase](Logistics.Procurement.PurchaseControlDocumentLines.md#receivedstandardquantitybase) | decimal (12, 3) __nullable__ | The standard quantity of the received items (usually with Receiving Order) in base measurement unit. Null when the logged operation did not involve receiving items. 
| [RequestedAmountBase](Logistics.Procurement.PurchaseControlDocumentLines.md#requestedamountbase) | decimal (14, 2) __nullable__ | The amount (in base currency) of the requested items (usually with Purchase Requisition). Null when the logged operation did not involve requesting items. 
| [RequestedStandard<br />QuantityBase](Logistics.Procurement.PurchaseControlDocumentLines.md#requestedstandardquantitybase) | decimal (12, 3) __nullable__ | The standard quantity of the requested items (usually with Purchase Requisition) in base measurement unit. Null when the logged operation did not involve requesting items. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [<s>Document</s>](Logistics.Procurement.PurchaseControlDocumentLines.md#document) | [PurchaseControlDocuments](Logistics.Procurement.PurchaseControlDocuments.md) | **OBSOLETE! Do not use!** The owner document. The <see cref="Purchase<br />ControlDocument"/> to which this PurchaseControl<br />DocumentLine belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.0.46` |
| [<s>PurchaseControlDocument</s>](Logistics.Procurement.PurchaseControlDocumentLines.md#purchasecontroldocument) | [PurchaseControlDocuments](Logistics.Procurement.PurchaseControlDocuments.md) | **OBSOLETE! Do not use!** The <see cref="Purchase<br />ControlDocument"/> to which this PurchaseControl<br />DocumentLine belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.0.46` `Obsolete` `Owner` |
| [PurchaseInvoice](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaseinvoice) | [PurchaseInvoices](Logistics.Procurement.PurchaseInvoices.md) (nullable) | The purchase invoice which is to be or was executed. Null when the data is unknown. `Filter(multi eq)` |
| [PurchaseInvoiceLine](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaseinvoiceline) | [PurchaseInvoiceLines](Logistics.Procurement.PurchaseInvoiceLines.md) (nullable) | The purchase invoice line which is to be or was executed. Null when the data is unknown. `Filter(multi eq)` |
| [<s>PurchaseOperationType</s>](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaseoperationtype) | [PurchaseOperationTypes](Logistics.Procurement.PurchaseOperationTypes.md) (nullable) | **OBSOLETE! Do not use!** The user-defined operation type, which is being recorded by the current line. Used for better grouping of the control entries. null when the operation type was not specified by the user. `Obsolete` `Filter(multi eq)` `Obsoleted in version 26.2.0.46` `Obsolete` |
| [PurchaseOrder](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaseorder) | [PurchaseOrders](Logistics.Procurement.PurchaseOrders.md) (nullable) | The purchase order which is to be or was executed. Null when the data is unknown. `Filter(multi eq)` |
| [PurchaseOrderLine](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaseorderline) | [PurchaseOrderLines](Logistics.Procurement.PurchaseOrderLines.md) (nullable) | The purchase order line which is to be or was executed. Null when the data is unknown. `Filter(multi eq)` |
| [PurchaseRequisition](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaserequisition) | [Requisitions](Logistics.Procurement.Requisitions.md) (nullable) | The purchase requisition which is to be or was executed. Null when the data is unknown. `Filter(multi eq)` |
| [PurchaseRequisitionLine](Logistics.Procurement.PurchaseControlDocumentLines.md#purchaserequisitionline) | [RequisitionLines](Logistics.Procurement.RequisitionLines.md) (nullable) | The purchase requisition line which is to be or was executed. Null when the data is unknown. `Filter(multi eq)` |
| [ReceivingOrder](Logistics.Procurement.PurchaseControlDocumentLines.md#receivingorder) | [ReceivingOrders](Logistics.Procurement.ReceivingOrders.md) (nullable) | The receiving order which is to be or was executed. Null when the data is unknown. `Filter(multi eq)` |
| [ReceivingOrderLine](Logistics.Procurement.PurchaseControlDocumentLines.md#receivingorderline) | [ReceivingOrderLines](Logistics.Procurement.ReceivingOrderLines.md) (nullable) | The receiving order line which is to be or was executed. Null when the data is unknown. `Filter(multi eq)` |


## Attribute Details

### ConfirmedAmountBase

The amount (in base currency) of the ordered items, confirmed by the supplier (usually with Purchase Confirmation). Null when the logged operation did not involve confirming ordered items.

_Type_: **decimal (14, 2) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ConfirmedStandardQuantityBase

The standard quantity of the ordered items, confirmed by the supplier (usually with Purchase Confirmation) in base measurement unit. Null when the logged operation did not involve confirming ordered items.

_Type_: **decimal (12, 3) __nullable__**  
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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### InvoicedAmountBase

The amount (in base currency) of the invoiced items (usually with Purchase Invoice). Null when the logged operation did not involve invoicing items.

_Type_: **decimal (14, 2) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### InvoicedStandardQuantityBase

The standard quantity of the invoiced items (usually with Purchase Invoice) in base measurement unit. Null when the logged operation did not involve invoicing items.

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LineNo

The consecutive line number within the control document. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this PurchaseControlDocumentLine.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### OrderedAmountBase

The amount (in base currency) of the ordered items (usually with Purchase Order). Null when the logged operation did not involve ordering items.

_Type_: **decimal (14, 2) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### OrderedStandardQuantityBase

The standard quantity of the ordered items (usually with Purchase Order) in base measurement unit. Null when the logged operation did not involve ordering items.

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ReceivedAmountBase

The amount (in base currency) of the received items (usually with Receiving Order). Null when the logged operation did not involve receiving items.

_Type_: **decimal (14, 2) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ReceivedStandardQuantityBase

The standard quantity of the received items (usually with Receiving Order) in base measurement unit. Null when the logged operation did not involve receiving items.

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### RequestedAmountBase

The amount (in base currency) of the requested items (usually with Purchase Requisition). Null when the logged operation did not involve requesting items.

_Type_: **decimal (14, 2) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### RequestedStandardQuantityBase

The standard quantity of the requested items (usually with Purchase Requisition) in base measurement unit. Null when the logged operation did not involve requesting items.

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Document

**OBSOLETE! Do not use!** The owner document. The <see cref="PurchaseControlDocument"/> to which this PurchaseControlDocumentLine belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.0.46`

_Type_: **[PurchaseControlDocuments](Logistics.Procurement.PurchaseControlDocuments.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PurchaseControlDocument

**OBSOLETE! Do not use!** The <see cref="PurchaseControlDocument"/> to which this PurchaseControlDocumentLine belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.0.46` `Obsolete` `Owner`

_Type_: **[PurchaseControlDocuments](Logistics.Procurement.PurchaseControlDocuments.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### PurchaseInvoice

The purchase invoice which is to be or was executed. Null when the data is unknown. `Filter(multi eq)`

_Type_: **[PurchaseInvoices](Logistics.Procurement.PurchaseInvoices.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PurchaseInvoiceLine

The purchase invoice line which is to be or was executed. Null when the data is unknown. `Filter(multi eq)`

_Type_: **[PurchaseInvoiceLines](Logistics.Procurement.PurchaseInvoiceLines.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PurchaseOperationType

**OBSOLETE! Do not use!** The user-defined operation type, which is being recorded by the current line. Used for better grouping of the control entries. null when the operation type was not specified by the user. `Obsolete` `Filter(multi eq)` `Obsoleted in version 26.2.0.46` `Obsolete`

_Type_: **[PurchaseOperationTypes](Logistics.Procurement.PurchaseOperationTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PurchaseOrder

The purchase order which is to be or was executed. Null when the data is unknown. `Filter(multi eq)`

_Type_: **[PurchaseOrders](Logistics.Procurement.PurchaseOrders.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PurchaseOrderLine

The purchase order line which is to be or was executed. Null when the data is unknown. `Filter(multi eq)`

_Type_: **[PurchaseOrderLines](Logistics.Procurement.PurchaseOrderLines.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PurchaseRequisition

The purchase requisition which is to be or was executed. Null when the data is unknown. `Filter(multi eq)`

_Type_: **[Requisitions](Logistics.Procurement.Requisitions.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PurchaseRequisitionLine

The purchase requisition line which is to be or was executed. Null when the data is unknown. `Filter(multi eq)`

_Type_: **[RequisitionLines](Logistics.Procurement.RequisitionLines.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ReceivingOrder

The receiving order which is to be or was executed. Null when the data is unknown. `Filter(multi eq)`

_Type_: **[ReceivingOrders](Logistics.Procurement.ReceivingOrders.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ReceivingOrderLine

The receiving order line which is to be or was executed. Null when the data is unknown. `Filter(multi eq)`

_Type_: **[ReceivingOrderLines](Logistics.Procurement.ReceivingOrderLines.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

