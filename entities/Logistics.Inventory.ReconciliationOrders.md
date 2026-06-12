---
uid: Logistics.Inventory.ReconciliationOrders
---
# Logistics.Inventory.ReconciliationOrders Entity

Obsolete. Not used. (Orders for store reconciliations. After an order is executed, store reconciliation is created). Entity: Inv_Reconciliation_Orders

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DueDate](Logistics.Inventory.ReconciliationOrders.md#duedate) | datetime | Date, when the transaction is scheduled to occur. [Required] [Default(Today)] 
| [Id](Logistics.Inventory.ReconciliationOrders.md#id) | guid |  
| [IsReleased](Logistics.Inventory.ReconciliationOrders.md#isreleased) | boolean | True if the document is not void and its state is released or greater. [Required] [Default(false)] [Filter(eq)] [ReadOnly] 
| [IsSingleExecution](Logistics.Inventory.ReconciliationOrders.md#issingleexecution) | boolean | Specifies whether the document is a single execution of its order document. [Required] [Default(false)] [Filter(eq)] [ReadOnly] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Inventory.ReconciliationOrders.md#document) | [Documents](General.Documents.md) | The Id of the base document. [Required] [Filter(multi eq)] [Owner] |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Lines | [ReconciliationOrderLines](Logistics.Inventory.ReconciliationOrderLines.md) | List of [ReconciliationOrderLine](Logistics.Inventory.ReconciliationOrderLines.md) child objects, based on the [Logistics.Inventory.ReconciliationOrderLine.ReconciliationOrder](Logistics.Inventory.ReconciliationOrderLines.md#reconciliationorder) back reference 


## Attribute Details

### DueDate

Date, when the transaction is scheduled to occur. [Required] [Default(Today)]

_Type_: **datetime**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDate**  

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsReleased

True if the document is not void and its state is released or greater. [Required] [Default(false)] [Filter(eq)] [ReadOnly]

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### IsSingleExecution

Specifies whether the document is a single execution of its order document. [Required] [Default(false)] [Filter(eq)] [ReadOnly]

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  


## Reference Details

### Document

The Id of the base document. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Documents](General.Documents.md)**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list erp.entity=Logistics.Inventory.ReconciliationOrders erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Logistics.Inventory.ReconciliationOrders erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Inventory_ReconciliationOrders?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_ReconciliationOrders?$top=10>

