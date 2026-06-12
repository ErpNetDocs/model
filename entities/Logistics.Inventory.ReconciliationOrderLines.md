---
uid: Logistics.Inventory.ReconciliationOrderLines
---
# Logistics.Inventory.ReconciliationOrderLines Entity

Obsolete. Not used. Entity: Inv_Reconciliation_Order_Lines

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.ReconciliationOrderLines.md#id) | guid |  
| [LineNo](Logistics.Inventory.ReconciliationOrderLines.md#lineno) | int32 | Line number within the reconciliation order. [Required] [Filter(eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Product](Logistics.Inventory.ReconciliationOrderLines.md#product) | [Products](General.Products.Products.md) | The item which quantity should be reconciled. [Required] [Filter(multi eq)] |
| [ReconciliationOrder](Logistics.Inventory.ReconciliationOrderLines.md#reconciliationorder) | [ReconciliationOrders](Logistics.Inventory.ReconciliationOrders.md) | Reconciliation order header. [Required] [Filter(multi eq)] [Owner] |
| [SerialNumber](Logistics.Inventory.ReconciliationOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product, which should be reconciled. [Filter(multi eq)] |
| [Store](Logistics.Inventory.ReconciliationOrderLines.md#store) | [Stores](Logistics.Inventory.Stores.md) | Store, which should be checked. [Required] [Filter(multi eq)] |
| [StoreBin](Logistics.Inventory.ReconciliationOrderLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | Specifies store bin, that should be reconciled. null means to reconcile all or any bin. [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### LineNo

Line number within the reconciliation order. [Required] [Filter(eq;ge;le)]

_Type_: **int32**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`( obj.ReconciliationOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.ReconciliationOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

## Reference Details

### Product

The item which quantity should be reconciled. [Required] [Filter(multi eq)]

_Type_: **[Products](General.Products.Products.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### ReconciliationOrder

Reconciliation order header. [Required] [Filter(multi eq)] [Owner]

_Type_: **[ReconciliationOrders](Logistics.Inventory.ReconciliationOrders.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### SerialNumber

Serial number of the product, which should be reconciled. [Filter(multi eq)]

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Store

Store, which should be checked. [Required] [Filter(multi eq)]

_Type_: **[Stores](Logistics.Inventory.Stores.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### StoreBin

Specifies store bin, that should be reconciled. null means to reconcile all or any bin. [Filter(multi eq)]

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list erp.entity=Logistics.Inventory.ReconciliationOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Logistics.Inventory.ReconciliationOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Inventory_ReconciliationOrderLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_ReconciliationOrderLines?$top=10>

