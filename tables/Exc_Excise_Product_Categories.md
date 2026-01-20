# Table Exc_Excise_Product_Categories


## Entity

Entity: [Regulatory.Excise.ExciseProductCategories](~/entities/Regulatory.Excise.ExciseProductCategories.md)

Product Category is defined by the taxation and customs authorities. Also specifies the calculation algorithm for the excise. For EU, the product category code is a single character - B,E,I,S,T or W. Entity: Exc_Excise_Product_Categories (Introduced in version 21.1.3.87)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Calculation_Algorithm](#calculation_algorithm)|`char(3)` Allowed: `NOP`, `QTY`, `QAS`, `QAP`|The calculation algorithm for Tax Base. NOP=No operation - manually set Tax Base; QTY=Qty; QAS=Qty * Alcoholic strength; QAP=Qty * Alcoholic strength / 100.|
|[Code](#code)|`nvarchar(32)` |For EU, the product category code is a single character - B,E,I,S,T or W.|
|[Excise_Product_Category_Id](#excise_product_category_id)|`uniqueidentifier` `PK`||
|[Name](#name)|`nvarchar(254)` `ML`|Multilanguage String|
|[Row_Version](#row_version)|`timestamp` ||

## Columns

### Calculation_Algorithm


The calculation algorithm for Tax Base. NOP=No operation - manually set Tax Base; QTY=Qty; QAS=Qty * Alcoholic strength; QAP=Qty * Alcoholic strength / 100.

| Property | Value |
| - | - |
|Allowed Values|`NOP`, `QTY`, `QAS`, `QAP`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|3|
|Order|3|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|char(3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Code


For EU, the product category code is a single character - B,E,I,S,T or W.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|32|
|Order|1|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|nvarchar(32)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Code - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|Like|None|no|no|

### Excise_Product_Category_Id

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

#### Excise_Product_Category_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|yes|

### Name


Multilanguage String

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|254|
|Order|2|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(254) (MultiLanguage)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Like|None|no|no|

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


