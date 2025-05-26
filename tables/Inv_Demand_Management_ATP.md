# View Inv_Demand_Management_ATP


## Entity

Entity: [Logistics.Inventory.DemandManagement.AvailableToPromise](~/entities/Logistics.Inventory.DemandManagement.AvailableToPromise.md)

Quantities available to promise for the different date periods. Also contains the current and projected availability. Entity: Inv_Demand_Management_ATP (Introduced in version 23.1.1.80)

## Summary

| Name | Type | Description |
| - | - | --- |
|[ATP_Base](#atp_base)|`decimal(38, 3)` |Indicates the quantity available to promise (in a base unit). It is valid from this date on.|
|[Current_Availability_Base](#current_availability_base)|`decimal(38, 3)` |The current availability in а base measurement unit.|
|[Enterprise_Company_Id](#enterprise_company_id)|`uniqueidentifier` |Тhe Enterprise Company, for which the quantities are calculated.|
|[From_Date](#from_date)|`datetime` |Тhe date from which the available to promise quantity is valid.|
|[Movements_Base](#movements_base)|`decimal(38, 3)` |The sum of the quantity of all planned stock movements on this date in а base measurement unit. |
|[Movements_To_Date_Base](#movements_to_date_base)|`decimal(38, 3)` |The sum of the quantity of all planned stock movements until this date (inclusive) in а base measurement unit. The value is cumulative.|
|[Product_Id](#product_id)|`uniqueidentifier` |The Product, for which the quantities are calculated.|
|[Projected_Availability_Base](#projected_availability_base)|`decimal(38, 3)` |Projected Availability in а base measurement unit on the particular date. The value is cumulative and includes the sum of all planned stock movements until this date (inclusive) and the current availability.|
|[Store_Id](#store_id)|`uniqueidentifier` |The Store, for which the quantities are calculated.|

## Columns

### ATP_Base


Indicates the quantity available to promise (in a base unit). It is valid from this date on.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(38, 3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Current_Availability_Base


The current availability in а base measurement unit.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(38, 3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Enterprise_Company_Id


Тhe Enterprise Company, for which the quantities are calculated.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Gen_Enterprise_Companies](Gen_Enterprise_Companies.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Enterprise_Company_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|

### From_Date


Тhe date from which the available to promise quantity is valid.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|yes|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|datetime|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### From_Date - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|no|

### Movements_Base


The sum of the quantity of all planned stock movements on this date in а base measurement unit. 

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(38, 3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Movements_To_Date_Base


The sum of the quantity of all planned stock movements until this date (inclusive) in а base measurement unit. The value is cumulative.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(38, 3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Product_Id


The Product, for which the quantities are calculated.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Gen_Products](Gen_Products.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Product_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|

### Projected_Availability_Base


Projected Availability in а base measurement unit on the particular date. The value is cumulative and includes the sum of all planned stock movements until this date (inclusive) and the current availability.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(38, 3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Store_Id


The Store, for which the quantities are calculated.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Inv_Stores](Inv_Stores.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Store_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|


