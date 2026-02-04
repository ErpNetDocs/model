---
uid: Logistics.Inventory.DemandManagement.AvailableToPromiseByLots
---
# Logistics.Inventory.DemandManagement.AvailableToPromiseByLots (View)


Quantities available to promise for the different date periods. Also contains the current and projected availability. The algorithm accounts for the quantities for each lot and separately for the quantities without lot.

## General
Namespace: [Logistics.Inventory.DemandManagement](Logistics.Inventory.DemandManagement.md)  
Repository: Logistics.Inventory.DemandManagement.AvailableToPromiseByLots  
Introduced In Version: 23.1.1.80  
API access:  ReadWrite  

## Visualization
Display Format: {ATPBaseValue}: {CurrentAvailabilityBaseValue}  
Search Members:   
Category:  Views  
Show in UI:  HiddenByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.DemandManagement.AvailableToPromiseByLots](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ATPBase](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#atpbase) | [Quantity (38, 3)](../data-types.md#quantity) | Indicates the quantity available to promise (in a base unit). It is valid from this date on. 
| [CurrentAvailabilityBase](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#currentavailabilitybase) | [Quantity (38, 3)](../data-types.md#quantity) | The current availability in а base measurement unit. 
| [FromDate](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#fromdate) | datetime | Тhe date from which the available to promise quantity is valid. 
| [MovementsBase](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#movementsbase) | [Quantity (38, 3)](../data-types.md#quantity) | The sum of the quantity of all planned stock movements on this date in а base measurement unit.  
| [MovementsToDateBase](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#movementstodatebase) | [Quantity (38, 3)](../data-types.md#quantity) | The sum of the quantity of all planned stock movements until this date (inclusive) in а base measurement unit. The value is cumulative. 
| [ProjectedAvailabilityBase](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#projectedavailabilitybase) | [Quantity (38, 3)](../data-types.md#quantity) | Projected Availability in а base measurement unit on the particular date. The value is cumulative and includes the sum of all planned stock movements until this date (inclusive) and the current availability. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Тhe Enterprise Company, for which the quantities are calculated. |
| [Lot](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The Lot, for which the quantities are calculated. |
| [Product](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#product) | [Products](General.Products.Products.md) | The Product, for which the quantities are calculated. |
| [Store](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#store) | [Stores](Logistics.Inventory.Stores.md) | The Store, for which the quantities are calculated. |


## Attribute Details

### ATPBase

Indicates the quantity available to promise (in a base unit). It is valid from this date on.

Type: **[Quantity (38, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CurrentAvailabilityBase

The current availability in а base measurement unit.

Type: **[Quantity (38, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FromDate

Тhe date from which the available to promise quantity is valid.

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MovementsBase

The sum of the quantity of all planned stock movements on this date in а base measurement unit.

Type: **[Quantity (38, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MovementsToDateBase

The sum of the quantity of all planned stock movements until this date (inclusive) in а base measurement unit. The value is cumulative.

Type: **[Quantity (38, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ProjectedAvailabilityBase

Projected Availability in а base measurement unit on the particular date. The value is cumulative and includes the sum of all planned stock movements until this date (inclusive) and the current availability.

Type: **[Quantity (38, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

Тhe Enterprise Company, for which the quantities are calculated.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Inherited From: **Gen_Documents_Table.Enterprise_Company_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

The Lot, for which the quantities are calculated.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Inherited From: **Inv_Store_Order_Lines_Table.Lot_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The Product, for which the quantities are calculated.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Inherited From: **Inv_Store_Order_Lines_Table.Product_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Store

The Store, for which the quantities are calculated.

Type: **[Stores](Logistics.Inventory.Stores.md)**  
Category: **System**  
Inherited From: **Inv_Store_Orders_Table.Store_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Logistics_Inventory_DemandManagement_AvailableToPromiseByLots

Domain API Entity Type: 
Logistics_Inventory_DemandManagement_AvailableToPromiseByLotsEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_DemandManagement_AvailableToPromiseByLots?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_DemandManagement_AvailableToPromiseByLots?$top=10>

