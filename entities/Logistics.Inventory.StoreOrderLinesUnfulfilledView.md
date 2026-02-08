---
uid: Logistics.Inventory.StoreOrderLinesUnfulfilledView
---
# Logistics.Inventory.StoreOrderLinesUnfulfilledView (View)


Returns the remaining (unfulfilled) quantity and cost for each Store Order Line in Store Orders, which are Planned, FirmPlanned or Released. Is_Fulfilled and Is_QuantityFulfilled can be used to filter out lines which appear fulfilled. For best performance, the store orders should be finished after fulfilling.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.StoreOrderLinesUnfulfilledView  
Introduced In Version: 21.1.1.16  
API access:  ReadWrite  

## Visualization
Display Format: {StoreOrderLineId}: {StoreOrderId}  
Search Members:   
Category:  Views  
Show in UI:  HiddenByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.StoreOrderLinesUnfulfilledView](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentDate](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#documentdate) | datetime | The date on which the document was issued.`Required` `Default(Today)` `Filter(eq;ge;le)` `Inherited from Gen_Documents_Table.Document_Date` 
| [IsFulfilled](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#isfulfilled) | boolean | Returns 1/true when both the Quantity and Cost are fulfilled or only negligible (less than 0.001 for qty and 0.01 for cost) sums remain. Please note, that filtering by this fields forces full scan and calculation of remaining amounts for all non-finished store orders. For best performance, the store orders should be finished after fulfilling.`Required` `Filter(multi eq)` 
| [IsQuantityFulfilled](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#isquantityfulfilled) | boolean | Returns 1/true when the Quantity is fulfilled or only negligible (less than 0.001) sum remains. Please note, that filtering by this fields forces full scan and calculation of remaining amounts for all non-finished store orders. For best performance, the store orders should be finished after fulfilling.`Required` `Filter(multi eq)` 
| [MovementType](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#movementtype) | [MovementType](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#movementtype) | Store order movement type. R=RECEIPT, I=ISSUE`Required` `Default(&quot;R&quot;)` `Filter(multi eq)` `Inherited from Inv_Store_Orders_Table.Movement_Type` 
| [OrderRemainingLineCost](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#orderremaininglinecost) | decimal (38, 2) | The remaining (unfulfilled) line cost of the order line.`Required` `Filter(multi eq;ge;le)` 
| [OrderRemainingQuantityBase](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#orderremainingquantitybase) | decimal (38, 3) | The remaining (unfulfilled) quantity of the order line in base measurement unit.`Required` `Filter(multi eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company which issued the document. |
| [Lot](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If non-null, contains the specific lot to use for the movement |
| [Product](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#product) | [Products](General.Products.Products.md) | The product which should be received/issued. |
| [ProductVariant](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. |
| [SerialNumber](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Which serial number to receive/issue. NULL means that serial number is unknown or not applicable |
| [Store](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#store) | [Stores](Logistics.Inventory.Stores.md) | The designated warehouse for the operation. |
| [StoreOrder](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#storeorder) | [StoreOrders](Logistics.Inventory.StoreOrders.md) | Store Order |
| [StoreOrderLine](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#storeorderline) | [StoreOrderLines](Logistics.Inventory.StoreOrderLines.md) (nullable) | The line, containing the ordered quantity, which this execution line executes. |


## Attribute Details

### DocumentDate

The date on which the document was issued.`Required` `Default(Today)` `Filter(eq;ge;le)` `Inherited from Gen_Documents_Table.Document_Date`

Type: **datetime**  
Category: **System**  
Inherited From: **Gen_Documents_Table.Document_Date**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDate**  
Show in UI: **ShownByDefault**  

### IsFulfilled

Returns 1/true when both the Quantity and Cost are fulfilled or only negligible (less than 0.001 for qty and 0.01 for cost) sums remain. Please note, that filtering by this fields forces full scan and calculation of remaining amounts for all non-finished store orders. For best performance, the store orders should be finished after fulfilling.`Required` `Filter(multi eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsQuantityFulfilled

Returns 1/true when the Quantity is fulfilled or only negligible (less than 0.001) sum remains. Please note, that filtering by this fields forces full scan and calculation of remaining amounts for all non-finished store orders. For best performance, the store orders should be finished after fulfilling.`Required` `Filter(multi eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MovementType

Store order movement type. R=RECEIPT, I=ISSUE`Required` `Default(&quot;R&quot;)` `Filter(multi eq)` `Inherited from Inv_Store_Orders_Table.Movement_Type`

Type: **[MovementType](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#movementtype)**  
Category: **System**  
Specifies the movement type (direction) of a warehouse document.  
Allowed Values (Logistics.Inventory.MovementType Enum Members)  

| Value | Description |
| ---- | --- |
| Issue | Goods issue <br /> Database Value: 'I' <br /> Model Value: 0 <br /> Domain API Value: 'Issue' |
| Receipt | Goods receive <br /> Database Value: 'R' <br /> Model Value: 1 <br /> Domain API Value: 'Receipt' |

Inherited From: **Inv_Store_Orders_Table.Movement_Type**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Receipt**  
Show in UI: **ShownByDefault**  

### OrderRemainingLineCost

The remaining (unfulfilled) line cost of the order line.`Required` `Filter(multi eq;ge;le)`

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OrderRemainingQuantityBase

The remaining (unfulfilled) quantity of the order line in base measurement unit.`Required` `Filter(multi eq;ge;le)`

Type: **decimal (38, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

The enterprise company which issued the document.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Inherited From: **Gen_Documents_Table.Enterprise_Company_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

If non-null, contains the specific lot to use for the movement

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Store_Order_Lines_Table.Lot_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product which should be received/issued.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Inherited From: **Inv_Store_Order_Lines_Table.Product_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductVariant

If specified determines which product variant of the current product in this line is used.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Store_Order_Lines_Table.Product_Variant_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SerialNumber

Which serial number to receive/issue. NULL means that serial number is unknown or not applicable

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Store_Order_Lines_Table.Serial_Number_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Store

The designated warehouse for the operation.

Type: **[Stores](Logistics.Inventory.Stores.md)**  
Category: **System**  
Inherited From: **Inv_Store_Orders_Table.Store_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### StoreOrder

Store Order

Type: **[StoreOrders](Logistics.Inventory.StoreOrders.md)**  
Category: **System**  
Inherited From: **Inv_Store_Orders_Table.Store_Order_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### StoreOrderLine

The line, containing the ordered quantity, which this execution line executes.

Type: **[StoreOrderLines](Logistics.Inventory.StoreOrderLines.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Transaction_Lines_Table.Parent_Store_Order_Line_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Logistics_Inventory_StoreOrderLinesUnfulfilledView

Domain API Entity Type: 
Logistics_Inventory_StoreOrderLinesUnfulfilledViewEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_StoreOrderLinesUnfulfilledView?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_StoreOrderLinesUnfulfilledView?$top=10>

