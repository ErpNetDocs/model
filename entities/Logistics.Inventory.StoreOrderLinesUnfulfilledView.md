---
uid: Logistics.Inventory.StoreOrderLinesUnfulfilledView
---
# Logistics.Inventory.StoreOrderLinesUnfulfilledView View

**Namespace:** [Logistics.Inventory](Logistics.Inventory.md)  

Returns the remaining (unfulfilled) quantity and cost for each Store Order Line in Store Orders, which are Planned, FirmPlanned or Released. Is_Fulfilled and Is_QuantityFulfilled can be used to filter out lines which appear fulfilled. For best performance, the store orders should be finished after fulfilling. Entity: Inv_Store_Order_Lines_Unfulfilled_View (Introduced in version 21.1.1.16)

## Default Visualization
Default Display Text Format:  
_{StoreOrderLineId}: {StoreOrderId}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _HiddenByDefault_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.StoreOrderLinesUnfulfilledView](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentDate](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#documentdate) | datetime | The date on which the document was issued. `Required` `Default(Today)` `Filter(eq;ge;le)` `Inherited from Gen_Documents_Table.Document_Date` 
| [IsFulfilled](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#isfulfilled) | boolean | Returns true/true when both the Quantity and Cost are fulfilled or only negligible (less than 0.001 for qty and 0.01 for cost) sums remain. Please note, that filtering by this fields forces full scan and calculation of remaining amounts for all non-finished store orders. For best performance, the store orders should be finished after fulfilling. `Required` `Filter(multi eq)` 
| [IsQuantityFulfilled](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#isquantityfulfilled) | boolean | Returns true/true when the Quantity is fulfilled or only negligible (less than 0.001) sum remains. Please note, that filtering by this fields forces full scan and calculation of remaining amounts for all non-finished store orders. For best performance, the store orders should be finished after fulfilling. `Required` `Filter(multi eq)` 
| [MovementType](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#movementtype) | [MovementType](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#movementtype) | Store order movement type. R=RECEIPT, I=ISSUE. `Required` `Default("R")` `Filter(multi eq)` `Inherited from Inv_Store_Orders_Table.Movement_Type` 
| [OrderRemainingLineCost](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#orderremaininglinecost) | decimal (38, 2) | The remaining (unfulfilled) line cost of the order line. `Required` `Filter(multi eq;ge;le)` 
| [OrderRemainingQuantityBase](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#orderremainingquantitybase) | decimal (38, 3) | The remaining (unfulfilled) quantity of the order line in base measurement unit. `Required` `Filter(multi eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company which issued the document. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id` |
| [Lot](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If non-null, contains the specific lot to use for the movement. `Filter(multi eq)` `Inherited from Inv_Store_Order_<br />Lines_Table.Lot_Id` |
| [Product](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#product) | [Products](General.Products.Products.md) | The product which should be received/issued. `Required` `Filter(multi eq)` `Inherited from Inv_Store_Order_<br />Lines_Table.Product_Id` |
| [ProductVariant](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. `Filter(multi eq)` `Inherited from Inv_Store_Order_<br />Lines_Table.Product_Variant_Id` |
| [SerialNumber](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Which serial number to receive/issue. null means that serial number is unknown or not applicable. `Filter(multi eq)` `Inherited from Inv_Store_Order_<br />Lines_Table.Serial_Number_Id` |
| [Store](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#store) | [Stores](Logistics.Inventory.Stores.md) | The designated warehouse for the operation. `Required` `Filter(multi eq)` `Inherited from Inv_Store_Orders_Table.Store_Id` |
| [StoreOrder](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#storeorder) | [StoreOrders](Logistics.Inventory.StoreOrders.md) | Store Order. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Inv_Store_Orders_Table.Store_Order_Id` `Introduced in version 24.1.1.78` |
| [StoreOrderLine](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#storeorderline) | [StoreOrderLines](Logistics.Inventory.StoreOrderLines.md) (nullable) | The line, containing the ordered quantity, which this execution line executes. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Parent_Store_Order_<br />Line_Id` `FilterableReference` |


## Attribute Details

### DocumentDate

The date on which the document was issued. `Required` `Default(Today)` `Filter(eq;ge;le)` `Inherited from Gen_Documents_Table.Document_Date`

_Type_: **datetime**  
_Category_: **System**  
_Inherited From_: **Gen_Documents_Table.Document_Date**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDate**  
_Show in UI_: **ShownByDefault**  

### IsFulfilled

Returns true/true when both the Quantity and Cost are fulfilled or only negligible (less than 0.001 for qty and 0.01 for cost) sums remain. Please note, that filtering by this fields forces full scan and calculation of remaining amounts for all non-finished store orders. For best performance, the store orders should be finished after fulfilling. `Required` `Filter(multi eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### IsQuantityFulfilled

Returns true/true when the Quantity is fulfilled or only negligible (less than 0.001) sum remains. Please note, that filtering by this fields forces full scan and calculation of remaining amounts for all non-finished store orders. For best performance, the store orders should be finished after fulfilling. `Required` `Filter(multi eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MovementType

Store order movement type. R=RECEIPT, I=ISSUE. `Required` `Default("R")` `Filter(multi eq)` `Inherited from Inv_Store_Orders_Table.Movement_Type`

_Type_: **[MovementType](Logistics.Inventory.StoreOrderLinesUnfulfilledView.md#movementtype)**  
_Category_: **System**  
Specifies the movement type (direction) of a warehouse document.  
_Allowed Values (Logistics.Inventory.MovementType Enum Members)_  

| Value | Description |
| ---- | --- |
| Issue | Goods issue <br /> _Database Value:_ 'I' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Issue' |
| Receipt | Goods receive <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Receipt' |

_Inherited From_: **Inv_Store_Orders_Table.Movement_Type**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Receipt**  
_Show in UI_: **ShownByDefault**  

### OrderRemainingLineCost

The remaining (unfulfilled) line cost of the order line. `Required` `Filter(multi eq;ge;le)`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### OrderRemainingQuantityBase

The remaining (unfulfilled) quantity of the order line in base measurement unit. `Required` `Filter(multi eq;ge;le)`

_Type_: **decimal (38, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

The enterprise company which issued the document. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Documents_Table.Enterprise_Company_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Lot

If non-null, contains the specific lot to use for the movement. `Filter(multi eq)` `Inherited from Inv_Store_Order_Lines_Table.Lot_Id`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Inv_Store_Order_Lines_Table.Lot_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The product which should be received/issued. `Required` `Filter(multi eq)` `Inherited from Inv_Store_Order_Lines_Table.Product_Id`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Inherited From_: **Inv_Store_Order_Lines_Table.Product_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductVariant

If specified determines which product variant of the current product in this line is used. `Filter(multi eq)` `Inherited from Inv_Store_Order_Lines_Table.Product_Variant_Id`

_Type_: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Inv_Store_Order_Lines_Table.Product_Variant_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SerialNumber

Which serial number to receive/issue. null means that serial number is unknown or not applicable. `Filter(multi eq)` `Inherited from Inv_Store_Order_Lines_Table.Serial_Number_Id`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Inv_Store_Order_Lines_Table.Serial_Number_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Store

The designated warehouse for the operation. `Required` `Filter(multi eq)` `Inherited from Inv_Store_Orders_Table.Store_Id`

_Type_: **[Stores](Logistics.Inventory.Stores.md)**  
_Category_: **System**  
_Inherited From_: **Inv_Store_Orders_Table.Store_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### StoreOrder

Store Order. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from Inv_Store_Orders_Table.Store_Order_Id` `Introduced in version 24.1.1.78`

_Type_: **[StoreOrders](Logistics.Inventory.StoreOrders.md)**  
_Category_: **System**  
_Inherited From_: **Inv_Store_Orders_Table.Store_Order_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### StoreOrderLine

The line, containing the ordered quantity, which this execution line executes. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Parent_Store_Order_Line_Id` `FilterableReference`

_Type_: **[StoreOrderLines](Logistics.Inventory.StoreOrderLines.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Inv_Transaction_Lines_Table.Parent_Store_Order_Line_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set:
Logistics_Inventory_StoreOrderLinesUnfulfilledView

Domain API Entity Type:
Logistics_Inventory_StoreOrderLinesUnfulfilledViewEntry

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Inventory_StoreOrderLinesUnfulfilledView?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_StoreOrderLinesUnfulfilledView?$top=10>

