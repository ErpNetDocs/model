# Table Wms_Warehouse_Reconciliation_Lines


## Entity

Entity: [Logistics.Wms.WarehouseReconciliationLines](~/entities/Logistics.Wms.WarehouseReconciliationLines.md)

Warehouse reconciliation detail records. Each record specifies a warehouse location to be reconciled. Entity: Wms_Warehouse_Reconciliation_Lines (Introduced in version 26.1.3.87)

## Owner Tables Hierarchy

* [Wms_Warehouse_Reconciliations](Wms_Warehouse_Reconciliations.md)
* [Gen_Documents](Gen_Documents.md)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Line_No](#line_no)|`int` |Consecutive number of the line in the document.|
|[Row_Version](#row_version)|`timestamp` ||
|[Warehouse_Location_Id](#warehouse_location_id)|`uniqueidentifier` |Warehouse location to be counted.|
|[Warehouse_Reconciliation_Id](#warehouse_reconciliation_id)|`uniqueidentifier` |Reconciliation document this line belongs to.|
|[Warehouse_Reconciliation_Line_Id](#warehouse_reconciliation_line_id)|`uniqueidentifier` `PK`|Unique identifier of the line in the reconciliation document.|
|[Warehouse_Worker_Id](#warehouse_worker_id)|`uniqueidentifier` |Worker (human or robot) assigned to perform the counting.|
|[Warehouse_Zone_Id](#warehouse_zone_id)|`uniqueidentifier` |Zone used to determine which locations are included when taking availability/snapshot, and later to split the generated Warehouse Orders. The zone is maintained separately from the location and is used only for scope and splitting of orders.|

## Columns

### Line_No


Consecutive number of the line in the document.

| Property | Value |
| - | - |
|Auto Complete|no|
|Autoincrement|10|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|1|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|yes|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|int|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Line_No - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|

### Row_Version

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|5|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|timestamp|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

### Warehouse_Location_Id


Warehouse location to be counted.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|4|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Wms_Warehouse_Locations](Wms_Warehouse_Locations.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Warehouse_Location_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Warehouse_Reconciliation_Id


Reconciliation document this line belongs to.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|3|
|Ownership Reference|yes|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Wms_Warehouse_Reconciliations](Wms_Warehouse_Reconciliations.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Warehouse_Reconciliation_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Warehouse_Reconciliation_Line_Id


Unique identifier of the line in the reconciliation document.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|NewGuid|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|0|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|yes (order: 1)|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

#### Warehouse_Reconciliation_Line_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|yes|

### Warehouse_Worker_Id


Worker (human or robot) assigned to perform the counting.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Wms_Warehouse_Workers](Wms_Warehouse_Workers.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Warehouse_Worker_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Warehouse_Zone_Id


Zone used to determine which locations are included when taking availability/snapshot, and later to split the generated Warehouse Orders. The zone is maintained separately from the location and is used only for scope and splitting of orders.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|6|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Wms_Warehouse_Zones](Wms_Warehouse_Zones.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Warehouse_Zone_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|


