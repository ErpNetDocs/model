---
uid: Logistics.Wms.WarehouseAvailability
---
# Logistics.Wms.WarehouseAvailability (View)


The availability of goods in the warehouse locations of the warehouse.

## General
Namespace: [Logistics.Wms](Logistics.Wms.md)  
Repository: Logistics.Wms.WarehouseAvailability  
Introduced In Version: 21.1.1.35  
API access:  ReadWrite  

## Visualization
Display Format: {WarehouseId}: {WarehouseLocationId}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

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

Type: **decimal (38, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StandardQuantityAvailable

Currently available theoretical quantity according to the measurement dimensions of the product. It can be used to calculate the quantity available in fixed measurement units like pieces. `Required` `Filter(eq;ge;le)` `Introduced in version 22.1.5.25`

Type: **decimal (38, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### LogisticUnit

Logistic unit, which was transacted. null when the transaction was not for a logistic unit. `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Logistic_Unit_Id`

Type: **[LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable)**  
Category: **System**  
Inherited From: **Wms_Warehouse_Transactions_Table.Logistic_Unit_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

The lot which was transacted. null when the transaction was not for a specific lot. `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Lot_Id`

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Inherited From: **Wms_Warehouse_Transactions_Table.Lot_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product, which was transacted. `Required` `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Product_Id`

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Inherited From: **Wms_Warehouse_Transactions_Table.Product_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductVariant

The product variant, which was transacted. null when the transaction was not for a product variant. `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Product_Variant_Id`

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Inherited From: **Wms_Warehouse_Transactions_Table.Product_Variant_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SerialNumber

The serial number which was transacted. null when the transaction was not for a specific serial number. `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Serial_Number_Id`

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Inherited From: **Wms_Warehouse_Transactions_Table.Serial_Number_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Warehouse

The warehouse in which the transaction occurred. `Required` `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Warehouse_Id`

Type: **[Warehouses](Logistics.Wms.Warehouses.md)**  
Category: **System**  
Inherited From: **Wms_Warehouse_Transactions_Table.Warehouse_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseLocation

The warehouse location, where the transaction occurred. `Required` `Filter(multi eq)` `Inherited from Wms_Warehouse_Transactions_Table.Warehouse_Location_Id`

Type: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md)**  
Category: **System**  
Inherited From: **Wms_Warehouse_Transactions_Table.Warehouse_Location_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Logistics_Wms_WarehouseAvailability

Domain API Entity Type: 
Logistics_Wms_WarehouseAvailabilityEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseAvailability?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseAvailability?$top=10>

