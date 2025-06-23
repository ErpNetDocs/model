---
uid: Logistics.Inventory.DemandManagement.AvailableToPromiseByLots
---
# Logistics.Inventory.DemandManagement.AvailableToPromiseByLots View

**Namespace:** [Logistics.Inventory.DemandManagement](Logistics.Inventory.DemandManagement.md)  

Quantities available to promise for the different date periods. Also contains the current and projected availability. The algorithm accounts for the quantities for each lot and separately for the quantities without lot. Entity: Inv_Demand_Management_ATP_By_Lots (Introduced in version 23.1.1.80)

## Default Visualization
Default Display Text Format:  
_{ATPBaseValue}: {CurrentAvailabilityBaseValue}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _HiddenByDefault_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.DemandManagement.AvailableToPromiseByLots](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ATPBase](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#atpbase) | [Quantity (38, 3)](../data-types.md#quantity) | Indicates the quantity available to promise (in a base unit). It is valid from this date on. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` 
| [CurrentAvailabilityBase](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#currentavailabilitybase) | [Quantity (38, 3)](../data-types.md#quantity) | The current availability in а base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` 
| [FromDate](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#fromdate) | datetime | Тhe date from which the available to promise quantity is valid. `Required` `Filter(eq;ge;le)` 
| [MovementsBase](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#movementsbase) | [Quantity (38, 3)](../data-types.md#quantity) | The sum of the quantity of all planned stock movements on this date in а base measurement unit. . `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` 
| [MovementsToDateBase](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#movementstodatebase) | [Quantity (38, 3)](../data-types.md#quantity) | The sum of the quantity of all planned stock movements until this date (inclusive) in а base measurement unit. The value is cumulative. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` 
| [ProjectedAvailabilityBase](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#projectedavailabilitybase) | [Quantity (38, 3)](../data-types.md#quantity) | Projected Availability in а base measurement unit on the particular date. The value is cumulative and includes the sum of all planned stock movements until this date (inclusive) and the current availability. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Тhe Enterprise Company, for which the quantities are calculated. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id` |
| [Lot](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The Lot, for which the quantities are calculated. `Filter(multi eq)` `Inherited from Inv_Store_Order_<br />Lines_Table.Lot_Id` |
| [Product](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#product) | [Products](General.Products.Products.md) | The Product, for which the quantities are calculated. `Required` `Filter(multi eq)` `Inherited from Inv_Store_Order_<br />Lines_Table.Product_Id` |
| [Store](Logistics.Inventory.DemandManagement.AvailableToPromiseByLots.md#store) | [Stores](Logistics.Inventory.Stores.md) | The Store, for which the quantities are calculated. `Required` `Filter(multi eq)` `Inherited from Inv_Store_Orders_Table.Store_Id` |


## Attribute Details

### ATPBase

Indicates the quantity available to promise (in a base unit). It is valid from this date on. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required`

_Type_: **[Quantity (38, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CurrentAvailabilityBase

The current availability in а base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required`

_Type_: **[Quantity (38, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### FromDate

Тhe date from which the available to promise quantity is valid. `Required` `Filter(eq;ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MovementsBase

The sum of the quantity of all planned stock movements on this date in а base measurement unit. . `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required`

_Type_: **[Quantity (38, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MovementsToDateBase

The sum of the quantity of all planned stock movements until this date (inclusive) in а base measurement unit. The value is cumulative. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required`

_Type_: **[Quantity (38, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ProjectedAvailabilityBase

Projected Availability in а base measurement unit on the particular date. The value is cumulative and includes the sum of all planned stock movements until this date (inclusive) and the current availability. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required`

_Type_: **[Quantity (38, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

Тhe Enterprise Company, for which the quantities are calculated. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Inherited From_: **Gen_Documents_Table.Enterprise_Company_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Lot

The Lot, for which the quantities are calculated. `Filter(multi eq)` `Inherited from Inv_Store_Order_Lines_Table.Lot_Id`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Inv_Store_Order_Lines_Table.Lot_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The Product, for which the quantities are calculated. `Required` `Filter(multi eq)` `Inherited from Inv_Store_Order_Lines_Table.Product_Id`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Inherited From_: **Inv_Store_Order_Lines_Table.Product_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Store

The Store, for which the quantities are calculated. `Required` `Filter(multi eq)` `Inherited from Inv_Store_Orders_Table.Store_Id`

_Type_: **[Stores](Logistics.Inventory.Stores.md)**  
_Category_: **System**  
_Inherited From_: **Inv_Store_Orders_Table.Store_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Inventory_DemandManagement_AvailableToPromiseByLots?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_DemandManagement_AvailableToPromiseByLots?$top=10>

