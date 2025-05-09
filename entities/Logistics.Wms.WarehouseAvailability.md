---
uid: Logistics.Wms.WarehouseAvailability
---
# Logistics.Wms.WarehouseAvailability View

**Namespace:** [Logistics.Wms](Logistics.Wms.md)  

The availability of goods in the warehouse locations of the warehouse. Entity: Wms_Warehouse_Availability (Introduced in version 21.1.1.35)

## Default Visualization
Default Display Text Format:  
_{WarehouseId}: {WarehouseLocationId}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Wms.WarehouseAvailability](Logistics.Wms.WarehouseAvailability.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [QuantityBaseAvailable](Logistics.Wms.WarehouseAvailability.md#quantitybaseavailable) | decimal (38, 3) | Currently available quantity in base measurement unit. `Required` `Filter(eq;ge;le)` `Introduced in version 22.1.5.25` 
| [StandardQuantityAvailable](Logistics.Wms.WarehouseAvailability.md#standardquantityavailable) | decimal (38, 3) | Currently available theoretical quantity according to the measurement dimensions of the product. It can be used to calculate the quantity available in fixed measurement units like pieces. `Required` `Filter(eq;ge;le)` `Introduced in version 22.1.5.25` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [LogisticUnit](Logistics.Wms.WarehouseAvailability.md#logisticunit) | [LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable) | Logistic unit, which was transacted. null when the transaction was not for a logistic unit. `Filter(multi eq)` `Inherited from Wms_Warehouse_<br />Transactions_Table.Logistic_Unit_Id` |
| [Lot](Logistics.Wms.WarehouseAvailability.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot which was transacted. null when the transaction was not for a specific lot. `Filter(multi eq)` `Inherited from Wms_Warehouse_<br />Transactions_Table.Lot_Id` |
| [Product](Logistics.Wms.WarehouseAvailability.md#product) | [Products](General.Products.Products.md) | The product, which was transacted. `Required` `Filter(multi eq)` `Inherited from Wms_Warehouse_<br />Transactions_Table.Product_Id` |
| [ProductVariant](Logistics.Wms.WarehouseAvailability.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | The product variant, which was transacted. null when the transaction was not for a product variant. `Filter(multi eq)` `Inherited from Wms_Warehouse_<br />Transactions_Table.Product_Variant_Id` |
| [SerialNumber](Logistics.Wms.WarehouseAvailability.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | The serial number which was transacted. null when the transaction was not for a specific serial number. `Filter(multi eq)` `Inherited from Wms_Warehouse_<br />Transactions_Table.Serial_Number_Id` |
| [Warehouse](Logistics.Wms.WarehouseAvailability.md#warehouse) | [Warehouses](Logistics.Wms.Warehouses.md) | The warehouse in which the transaction occurred. `Required` `Filter(multi eq)` `Inherited from Wms_Warehouse_<br />Transactions_Table.Warehouse_Id` |
| [WarehouseLocation](Logistics.Wms.WarehouseAvailability.md#warehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) | The warehouse location, where the transaction occurred. `Required` `Filter(multi eq)` `Inherited from Wms_Warehouse_<br />Transactions_Table.Warehouse_Location_Id` |


## Attribute Details

### QuantityBaseAvailable

Currently available quantity in base measurement unit. `Required` `Filter(eq;ge;le)` `Introduced in version 22.1.5.25`

_Type_: **decimal (38, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StandardQuantityAvailable

Currently available theoretical quantity according to the measurement dimensions of the product. It can be used to calculate the quantity available in fixed measurement units like pieces. `Required` `Filter(eq;ge;le)` `Introduced in version 22.1.5.25`

_Type_: **decimal (38, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### LogisticUnit

Logistic unit, which was transacted. null when the transaction was not for a logistic unit. `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Logistic_Unit_Id`

_Type_: **[LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Wms_Warehouse_Transactions_Table.Logistic_Unit_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Lot

The lot which was transacted. null when the transaction was not for a specific lot. `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Lot_Id`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Wms_Warehouse_Transactions_Table.Lot_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The product, which was transacted. `Required` `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Product_Id`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Inherited From_: **Wms_Warehouse_Transactions_Table.Product_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductVariant

The product variant, which was transacted. null when the transaction was not for a product variant. `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Product_Variant_Id`

_Type_: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Wms_Warehouse_Transactions_Table.Product_Variant_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SerialNumber

The serial number which was transacted. null when the transaction was not for a specific serial number. `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Serial_Number_Id`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Wms_Warehouse_Transactions_Table.Serial_Number_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Warehouse

The warehouse in which the transaction occurred. `Required` `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Warehouse_Id`

_Type_: **[Warehouses](Logistics.Wms.Warehouses.md)**  
_Category_: **System**  
_Inherited From_: **Wms_Warehouse_Transactions_Table.Warehouse_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WarehouseLocation

The warehouse location, where the transaction occurred. `Required` `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Warehouse_Location_Id`

_Type_: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md)**  
_Category_: **System**  
_Inherited From_: **Wms_Warehouse_Transactions_Table.Warehouse_Location_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseAvailability?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseAvailability?$top=10>

