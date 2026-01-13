# Table Crm_Invoice_Order_Lines


## Entity

Entity: [Crm.Invoicing.InvoiceOrderLines](~/entities/Crm.Invoicing.InvoiceOrderLines.md)

Detail records (lines) of Invoice Orders. Entity: Crm_Invoice_Order_Lines

## Owner Tables Hierarchy

* [Crm_Invoice_Orders](Crm_Invoice_Orders.md)
* [Gen_Documents](Gen_Documents.md)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Business_Reason](#business_reason)|`char(1)` Allowed: `P`, `S`|Business reason for invoicing of this product or service. S=Shipment, P=Payment|
|[Invoice_Order_Id](#invoice_order_id)|`uniqueidentifier` ||
|[Invoice_Order_Line_Id](#invoice_order_line_id)|`uniqueidentifier` `PK`||
|[Line_Amount](#line_amount)|`decimal(14, 2)` |Amount for the line in the currency of the parent document. Usually equals Quantity * Unit_Price. When Quantity = 0, Unit Price is undefined and this contains the total line amount.|
|[Line_Custom_Discount_Percent](#line_custom_discount_percent)|`decimal(7, 6)` |User-defined discount for the line|
|[Line_Deal_Type_Id](#line_deal_type_id)|`uniqueidentifier` |Deal type to be passed to the invoice line. If deal type in the line is different from deal type in the header another VAT entry is created from the invoice.|
|[Line_Discount_Id](#line_discount_id)|`uniqueidentifier` |The line discount type used to form the Line_Standard_Discount_Percent|
|[Line_No](#line_no)|`int` ||
|[Line_Standard_Discount_Percent](#line_standard_discount_percent)|`decimal(7, 6)` |Standard discount for the line. This is automatically computed according to discount conditions|
|[Payment_Transaction_Id](#payment_transaction_id)|`uniqueidentifier` |The payment transaction, which is to be invoiced by this line, when Business Reason = P. Used to reconcile the invoice with the payments in the case of advance payment.|
|[Product_Description](#product_description)|`nvarchar(254)` `ML`|The description of Product. Initially copied from the name of the Product or from the generating document.|
|[Product_Id](#product_id)|`uniqueidentifier` |The product, which is ordered for invoicing|
|[Quantity](#quantity)|`decimal(12, 3)` |The quantity of the product to invoice|
|[Quantity_Base](#quantity_base)|`decimal(12, 3)` |The equivalent of Quantity in the base measurement unit of the Product|
|[Quantity_Unit_Id](#quantity_unit_id)|`uniqueidentifier` |The measurement unit of Quantity|
|[Row_Version](#row_version)|`timestamp` ||
|[Sales_Order_Id](#sales_order_id)|`uniqueidentifier` |When not NULL specifies the Sales Order that is ordered to be invoiced by this line|
|[Sales_Order_Line_Id](#sales_order_line_id)|`uniqueidentifier` |When not NULL specifies the Sales Order line that is ordered to be invoiced by this line|
|[Serial_Number_Id](#serial_number_id)|`uniqueidentifier` |Which serial number to receive/issue. NULL means that serial number is unknown or not applicable|
|[Standard_Quantity_Base](#standard_quantity_base)|`decimal(12, 3)` Readonly|The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.|
|[Transaction_Line_Id](#transaction_line_id)|`uniqueidentifier` |The store transaction line that is to be invoiced by this line, for Business Reason = S|
|[Unit_Price](#unit_price)|`decimal(14, 5)` |Unit selling price in the unit of measure, specified in Quantity Unit|

## Columns

### Business_Reason


Business reason for invoicing of this product or service. S=Shipment, P=Payment

| Property | Value |
| - | - |
|Allowed Values|`P`, `S`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|S|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|1|
|Order|19|
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
|Visible|no|

### Invoice_Order_Id

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|8|
|Ownership Reference|yes|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Crm_Invoice_Orders](Crm_Invoice_Orders.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Invoice_Order_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|

### Invoice_Order_Line_Id

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|NewGuid|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|7|
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

#### Invoice_Order_Line_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|
|GreaterThanOrLessThan|None|no|yes|

### Line_Amount


Amount for the line in the currency of the parent document. Usually equals Quantity * Unit_Price. When Quantity = 0, Unit Price is undefined and this contains the total line amount.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|0|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|6|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|Sum|
|Supports EQUALS_IN|no|
|Type|decimal(14, 2)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Line_Custom_Discount_Percent


User-defined discount for the line

| Property | Value |
| - | - |
|Attributes|IsPercent|
|Auto Complete|no|
|Data Filter|no|
|Default Value|0|
|Enter Stop|no|
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
|Type|decimal(7, 6)|
|UI Memo Editor|no|
|UI Width|Short|
|User Login|no|
|Visible|yes|

### Line_Deal_Type_Id


Deal type to be passed to the invoice line. If deal type in the line is different from deal type in the header another VAT entry is created from the invoice.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|16|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[VAT_Deal_Types](VAT_Deal_Types.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

#### Line_Deal_Type_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Line_Discount_Id


The line discount type used to form the Line_Standard_Discount_Percent

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|11|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Crm_Line_Discounts](Crm_Line_Discounts.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

#### Line_Discount_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Line_No

| Property | Value |
| - | - |
|Auto Complete|no|
|Autoincrement|10|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|0|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|int|
|UI Memo Editor|no|
|UI Width|Short|
|User Login|no|
|Visible|yes|

### Line_Standard_Discount_Percent


Standard discount for the line. This is automatically computed according to discount conditions

| Property | Value |
| - | - |
|Attributes|IsPercent|
|Auto Complete|no|
|Data Filter|no|
|Default Value|0|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|12|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(7, 6)|
|UI Memo Editor|no|
|UI Width|Short|
|User Login|no|
|Visible|no|

### Payment_Transaction_Id


The payment transaction, which is to be invoiced by this line, when Business Reason = P. Used to reconcile the invoice with the payments in the case of advance payment.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|14|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Cash_Payment_Transactions](Cash_Payment_Transactions.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

#### Payment_Transaction_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Product_Description


The description of Product. Initially copied from the name of the Product or from the generating document.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|254|
|Order|9|
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
|UI Width|Long|
|User Login|no|
|Visible|no|

### Product_Id


The product, which is ordered for invoicing

| Property | Value |
| - | - |
|Auto Complete|no|
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
|Referenced Table|[Gen_Products](Gen_Products.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Product_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Quantity


The quantity of the product to invoice

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|1|
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
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(12, 3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Quantity - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|GreaterThanOrLessThan|None|yes|no|

### Quantity_Base


The equivalent of Quantity in the base measurement unit of the Product

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|15|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(12, 3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

### Quantity_Unit_Id


The measurement unit of Quantity

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|3|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Gen_Measurement_Units](Gen_Measurement_Units.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Short|
|User Login|no|
|Visible|yes|

#### Quantity_Unit_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

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
|Order|20|
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

### Sales_Order_Id


When not NULL specifies the Sales Order that is ordered to be invoiced by this line

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|18|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Crm_Sales_Orders](Crm_Sales_Orders.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|no|

#### Sales_Order_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Sales_Order_Line_Id


When not NULL specifies the Sales Order line that is ordered to be invoiced by this line

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|17|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Crm_Sales_Order_Lines](Crm_Sales_Order_Lines.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

#### Sales_Order_Line_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Serial_Number_Id


Which serial number to receive/issue. NULL means that serial number is unknown or not applicable

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|10|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Inv_Serial_Numbers](Inv_Serial_Numbers.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

#### Serial_Number_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|yes|

### Standard_Quantity_Base


The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|21|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|yes|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(12, 3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

### Transaction_Line_Id


The store transaction line that is to be invoiced by this line, for Business Reason = S

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|13|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Inv_Transaction_Lines](Inv_Transaction_Lines.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

#### Transaction_Line_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Unit_Price


Unit selling price in the unit of measure, specified in Quantity Unit

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|0|
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
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(14, 5)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|


