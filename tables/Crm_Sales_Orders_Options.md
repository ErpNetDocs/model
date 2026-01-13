# Table Crm_Sales_Orders_Options


## Entity

Entity: [Crm.Sales.SalesOrdersOptions](~/entities/Crm.Sales.SalesOrdersOptions.md)

Options for sales orders of specific user defined document type. Entity: Crm_Sales_Orders_Options

## Owner Tables Hierarchy

* [Gen_Document_Types](Gen_Document_Types.md)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Allowed_Directions](#allowed_directions)|`char(1)` Allowed: `S`, `R`, `*`, `A`|Allowed directions (return or normal sale) for the sales orders of this document type. 'S' = Normal sale, 'R' = Sales return, '*' = No limit, 'A' = Allow any, but not both (default)|
|[Available_Quantity_Only](#available_quantity_only)|`bit` |When 1 indicates that the sales order can be released only if there is sufficient available quantity (by ATP)|
|[Deal_Document_Type_Id](#deal_document_type_id)|`uniqueidentifier` |If filled then new opportunities (deals) from the specified type are created automatically by the sales orders that aren't assigned to existing opportunities.|
|[Document_Type_Id](#document_type_id)|`uniqueidentifier` |The document type for which the sales order option applies.|
|[Minimum_Amount](#minimum_amount)|`decimal(14, 2)` |When not NULL, specifies minimal total amount of the sales order, which is required for order releasing.|
|[Minimum_Amount_Currency_Id](#minimum_amount_currency_id)|`uniqueidentifier` |The currency of Minimal Amount|
|[Row_Version](#row_version)|`timestamp` ||
|[Sales_Order_Option_Id](#sales_order_option_id)|`uniqueidentifier` `PK`||
|[Shipment_Allowance](#shipment_allowance)|`char(1)` Allowed: `A`, `P`, `W`|Terms on which the shipment of the products in the sales order is allowed.|
|[VAT_Deviation_Document_Amount_Type_Id](#vat_deviation_document_amount_type_id)|`uniqueidentifier` |Document amount that contains the difference between the total amount of the sales order formed by unit prices with VAT and the amount formed by unit prices without VAT|

## Columns

### Allowed_Directions


Allowed directions (return or normal sale) for the sales orders of this document type. 'S' = Normal sale, 'R' = Sales return, '*' = No limit, 'A' = Allow any, but not both (default)

| Property | Value |
| - | - |
|Allowed Values|`S`, `R`, `*`, `A`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|A|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|char(1)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Allowed_Directions - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Available_Quantity_Only


When 1 indicates that the sales order can be released only if there is sufficient available quantity (by ATP)

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|False|
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
|Type|bit|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Available_Quantity_Only - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Deal_Document_Type_Id


If filled then new opportunities (deals) from the specified type are created automatically by the sales orders that aren't assigned to existing opportunities.

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
|Referenced Table|[Gen_Document_Types](Gen_Document_Types.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Deal_Document_Type_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Document_Type_Id


The document type for which the sales order option applies.

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
|Ownership Reference|yes|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Gen_Document_Types](Gen_Document_Types.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Document_Type_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Minimum_Amount


When not NULL, specifies minimal total amount of the sales order, which is required for order releasing.

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
|Type|decimal(14, 2) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Minimum_Amount_Currency_Id


The currency of Minimal Amount

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
|Referenced Table|[Gen_Currencies](Gen_Currencies.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Minimum_Amount_Currency_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

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
|Type|timestamp|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

### Sales_Order_Option_Id

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|NewGuid|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
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

#### Sales_Order_Option_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|
|GreaterThanOrLessThan|None|no|yes|

### Shipment_Allowance


Terms on which the shipment of the products in the sales order is allowed.

| Property | Value |
| - | - |
|Allowed Values|`A`, `P`, `W`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|A|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|1|
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
|Type|char(1)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### VAT_Deviation_Document_Amount_Type_Id


Document amount that contains the difference between the total amount of the sales order formed by unit prices with VAT and the amount formed by unit prices without VAT

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
|Referenced Table|[Gen_Document_Amount_Types](Gen_Document_Amount_Types.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### VAT_Deviation_Document_Amount_Type_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|


