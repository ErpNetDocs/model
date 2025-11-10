---
uid: Finance.Payments.InvoiceReconciliationLines
---
# Finance.Payments.InvoiceReconciliationLines Entity

**Namespace:** [Finance.Payments](Finance.Payments.md)  

Obsolete. Not used. Entity: Cash_Invoice_Reconciliation_Lines (Obsoleted in version 20.1.0.0)

> [!NOTE]  
> **OBSOLETE! Do not use!**   


## Default Visualization
Default Display Text Format:  
_{InvoiceReconciliation.EntityName}_  
Default Search Members:  
_InvoiceReconciliation.EntityName_  
Name Data Member:  
_InvoiceReconciliation.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Payments.InvoiceReconciliations](Finance.Payments.InvoiceReconciliations.md)  
Aggregate Root:  
[Finance.Payments.InvoiceReconciliations](Finance.Payments.InvoiceReconciliations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CoveredInvoiceAmount](Finance.Payments.InvoiceReconciliationLines.md#coveredinvoiceamount) | decimal (14, 2) | Amount from the invoice that is covered by the payment. The amount is in the currency of the invoice. `Required` `Default(0)` 
| [DisplayText](Finance.Payments.InvoiceReconciliationLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Finance.Payments.InvoiceReconciliationLines.md#id) | guid |  
| [ObjectVersion](Finance.Payments.InvoiceReconciliationLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [InvoiceDocument](Finance.Payments.InvoiceReconciliationLines.md#invoicedocument) | [Documents](General.Documents.Documents.md) | Obsolete. Not used. `Required` `Filter(multi eq)` |
| [<s>InvoiceReconciliation</s>](Finance.Payments.InvoiceReconciliationLines.md#invoicereconciliation) | [InvoiceReconciliations](Finance.Payments.InvoiceReconciliations.md) | **OBSOLETE! Do not use!** The <see cref="InvoiceReconciliatio<br />n"/> to which this InvoiceReconciliationLine belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.0.45` `Obsolete` `Owner` |
| [PaymentTransactionDocument](Finance.Payments.InvoiceReconciliationLines.md#paymenttransactiondocument) | [Documents](General.Documents.Documents.md) | Obsolete. Not used. `Required` `Filter(multi eq)` |


## Attribute Details

### CoveredInvoiceAmount

Amount from the invoice that is covered by the payment. The amount is in the currency of the invoice. `Required` `Default(0)`

_Type_: **decimal (14, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### InvoiceDocument

Obsolete. Not used. `Required` `Filter(multi eq)`

_Type_: **[Documents](General.Documents.Documents.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### InvoiceReconciliation

**OBSOLETE! Do not use!** The <see cref="InvoiceReconciliation"/> to which this InvoiceReconciliationLine belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.0.45` `Obsolete` `Owner`

_Type_: **[InvoiceReconciliations](Finance.Payments.InvoiceReconciliations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### PaymentTransactionDocument

Obsolete. Not used. `Required` `Filter(multi eq)`

_Type_: **[Documents](General.Documents.Documents.md)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Finance.Payments.InvoiceReconciliationLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Payments.InvoiceReconciliationLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Payments_InvoiceReconciliationLines

Domain API Entity Type: 
Finance_Payments_InvoiceReconciliationLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Payments_InvoiceReconciliationLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Payments_InvoiceReconciliationLines?$top=10>

