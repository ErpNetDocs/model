# Table Crm_Bonus_Programs


## Entity

Entity: [Crm.Pricing.BonusPrograms](~/entities/Crm.Pricing.BonusPrograms.md)

Bonus programs allow automatic adding of new line with bonus product or automatic application of discount in a sales document. Entity: Crm_Bonus_Programs

## Summary

| Name | Type | Description |
| - | - | --- |
|[Active](#active)|`bit` |General condition if the bonus is active. The other conditions are verified only for active bonus programs|
|[Bonus_Action](#bonus_action)|`char(1)` Allowed: `P`, `D`, `C`|If the bonus is a product, then Bonus Product, Bonus Product Quantity and Bonus Product Quantity Unit fields should be filled in. If the bonus is a discount, the Bonus Line Discount Percent should be filled in. Product - add product to the order, Discount – replace the standard discount, Cascade discount - apply after the standard discount.|
|[Bonus_Document_Amount_Percent](#bonus_document_amount_percent)|`decimal(7, 6)` |The percent of the document amount that is rewarded. Should be NULL if and only if the bonus document amount is NULL|
|[Bonus_Document_Amount_Type_Id](#bonus_document_amount_type_id)|`uniqueidentifier` |When not NULL specifies that a document amount should be added to the order when the bonus conditions are met. NULL means that the bonus reward is not a document amount|
|[Bonus_Line_Discount_Percent](#bonus_line_discount_percent)|`decimal(7, 6)` |The percent discount to be applied to bonus lines. Used only for bonus programs with Action = D (Discount) and Action = C (Cascade discount)|
|[Bonus_Product_Id](#bonus_product_id)|`uniqueidentifier` |The product that is rewarded if the bonus conditions are met. NULL means that the bonus reward is not product|
|[Bonus_Product_Quantity](#bonus_product_quantity)|`decimal(12, 3)` |The quantity rewarded of the bonus product. Should be not NULL if and only when the bonus product is not NULL|
|[Bonus_Product_Quantity_Multiplier_For_Each_Lot_Size](#bonus_product_quantity_multiplier_for_each_lot_size)|`decimal(12, 3)` |When not NULL, specifies that the bonus quantity should be multiplied for each of the specified lot size. Can be non-NULL only when condition product is specified|
|[Bonus_Product_Quantity_Unit_Id](#bonus_product_quantity_unit_id)|`uniqueidentifier` |The measurement unit of the quantity rewarded of the bonus product. Should be not NULL if and only when the bonus product is not NULL|
|[Bonus_Program_Id](#bonus_program_id)|`uniqueidentifier` `PK`||
|[Bonus_Program_Name](#bonus_program_name)|`nvarchar(254)` `ML`|The name of the bonus program|
|[Campaign_Id](#campaign_id)|`uniqueidentifier` |Тhe marketing campaign to which the current definition belongs.|
|[Company_Location_Id](#company_location_id)|`uniqueidentifier` |When set, specifies that the sales document must be of the specified enterprise company location.|
|[Condition_Customer_Filter_XML](#condition_customer_filter_xml)|`nvarchar(max)` |When not NULL, specifies that the bonus should be applied only to customers who meet the specified criteria. The criteria could include custom properties|
|[Condition_Customer_Id](#condition_customer_id)|`uniqueidentifier` |When not NULL, specifies that the bonus should be applied only to the specified customer|
|[Condition_Distribution_Channel_Filter_XML](#condition_distribution_channel_filter_xml)|`nvarchar(max)` |When not NULL, specifies that the bonus should be applied only when the distribution channel of the sales order has the specified characteristics|
|[Condition_Distribution_Channel_Id](#condition_distribution_channel_id)|`uniqueidentifier` |When not NULL, specifies that the bonus should be applied only when the specified channel is used|
|[Condition_Document_Currency_Id](#condition_document_currency_id)|`uniqueidentifier` |Condition for the document amount. Should be not NULL if any of the amount conditions are not NULL|
|[Condition_From_Date](#condition_from_date)|`datetime` |Starting date of the bonus. NULL means that there is no starting date restriction|
|[Condition_Max_Amount](#condition_max_amount)|`decimal(12, 2)` |If not NULL specifies the maximal amount for which the bonus is valid. NULL means that there is no maximal amount condition for the bonus|
|[Condition_Max_Quantity](#condition_max_quantity)|`decimal(12, 3)` |When not NULL, specifies condition for the bonus - maximal quantity of the condition product. If the condition product is null, this cannot be specified|
|[Condition_Min_Amount](#condition_min_amount)|`decimal(12, 2)` |If not NULL specifies the minimal amount for which the bonus is valid. NULL means that there is no minimal amount condition for the bonus|
|[Condition_Min_Quantity](#condition_min_quantity)|`decimal(12, 3)` |When not NULL, specifies condition for the bonus - minimal quantity of the condition product. If the condition product is null, this cannot be specified|
|[Condition_Price_List_Id](#condition_price_list_id)|`uniqueidentifier` |When not NULL, specifies that the bonus should be applied only when the sales order is based on the speicfied price list|
|[Condition_Product_Group_Id](#condition_product_group_id)|`uniqueidentifier` |When not NULL, specifies that the bonus should be applied only to products from the specified product group or its subgroups|
|[Condition_Product_Id](#condition_product_id)|`uniqueidentifier` |When not NULL, specifies a conditional product, which is required to exist in the sales document in order for the bonus program to be applied. If a condition with multiple products is required, additional products can be added to Bonus Program Products. If NULL the other conditions should be evaluated against the whole order.|
|[Condition_Ship_To_Customer_Filter_XML](#condition_ship_to_customer_filter_xml)|`nvarchar(max)` |When not NULL, specifies that the bonus should be applied only when shipping to customer with the specified characteristics|
|[Condition_Ship_To_Customer_Id](#condition_ship_to_customer_id)|`uniqueidentifier` |When not NULL, specifies that the bonus should be applied only when shipping to the specified customer|
|[Condition_Target_Group_Id](#condition_target_group_id)|`uniqueidentifier` |When not NULL, specifies that the bonus should be applied only to the specified target customer group|
|[Condition_To_Date](#condition_to_date)|`datetime` |Ending date (inclusive) of the bonus. NULL means that there is no ending date restriction|
|[Document_Amount_Type_Id](#document_amount_type_id)|`uniqueidentifier` |The document amount type that is used as а category. When specified, triggers the recording of the applied discount amount that comes from the bonus program in the Document Distributed Amounts panel in sales orders.|
|[Enterprise_Company_Id](#enterprise_company_id)|`uniqueidentifier` |When set, specifies that the sales document must be of the specified enterprise company.|
|[Priority](#priority)|`tinyint` Allowed: `0`, `1`, `2`, `3`, `4`|Priority (1-5) of the bonus program comparative to the other bonus programs. 1 is the lowest priority|
|[Row_Version](#row_version)|`timestamp` ||

## Columns

### Active


General condition if the bonus is active. The other conditions are verified only for active bonus programs

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|True|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|16|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|bit (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Active - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Bonus_Action


If the bonus is a product, then Bonus Product, Bonus Product Quantity and Bonus Product Quantity Unit fields should be filled in. If the bonus is a discount, the Bonus Line Discount Percent should be filled in. Product - add product to the order, Discount – replace the standard discount, Cascade discount - apply after the standard discount.

| Property | Value |
| - | - |
|Allowed Values|`P`, `D`, `C`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|D|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|1|
|Order|17|
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

#### Bonus_Action - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Bonus_Document_Amount_Percent


The percent of the document amount that is rewarded. Should be NULL if and only if the bonus document amount is NULL

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|23|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(7, 6) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

### Bonus_Document_Amount_Type_Id


When not NULL specifies that a document amount should be added to the order when the bonus conditions are met. NULL means that the bonus reward is not a document amount

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|22|
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
|Visible|no|

#### Bonus_Document_Amount_Type_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Bonus_Line_Discount_Percent


The percent discount to be applied to bonus lines. Used only for bonus programs with Action = D (Discount) and Action = C (Cascade discount)

| Property | Value |
| - | - |
|Attributes|IsPercent|
|Auto Complete|no|
|Data Filter|no|
|Default Value|0|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|24|
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
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Bonus_Product_Id


The product that is rewarded if the bonus conditions are met. NULL means that the bonus reward is not product

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|18|
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
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Bonus_Product_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Bonus_Product_Quantity


The quantity rewarded of the bonus product. Should be not NULL if and only when the bonus product is not NULL

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
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
|Type|decimal(12, 3) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

### Bonus_Product_Quantity_Multiplier_For_Each_Lot_Size


When not NULL, specifies that the bonus quantity should be multiplied for each of the specified lot size. Can be non-NULL only when condition product is specified

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
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(12, 3) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

### Bonus_Product_Quantity_Unit_Id


The measurement unit of the quantity rewarded of the bonus product. Should be not NULL if and only when the bonus product is not NULL

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
|Referenced Table|[Gen_Measurement_Units](Gen_Measurement_Units.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Bonus_Product_Quantity_Unit_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Bonus_Program_Id

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

#### Bonus_Program_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|yes|

### Bonus_Program_Name


The name of the bonus program

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|254|
|Order|1|
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
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Bonus_Program_Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|Like|None|no|no|

### Campaign_Id


Тhe marketing campaign to which the current definition belongs.

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
|Referenced Table|[Crm_Campaigns](Crm_Campaigns.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Campaign_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Company_Location_Id


When set, specifies that the sales document must be of the specified enterprise company location.

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
|Referenced Table|[Cm_Company_Locations](Cm_Company_Locations.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Company_Location_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_Customer_Filter_XML


When not NULL, specifies that the bonus should be applied only to customers who meet the specified criteria. The criteria could include custom properties

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|yes|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2147483647|
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
|Type|nvarchar(max) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

### Condition_Customer_Id


When not NULL, specifies that the bonus should be applied only to the specified customer

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|11|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Crm_Customers](Crm_Customers.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Condition_Customer_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_Distribution_Channel_Filter_XML


When not NULL, specifies that the bonus should be applied only when the distribution channel of the sales order has the specified characteristics

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|yes|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2147483647|
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
|Type|nvarchar(max) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Condition_Distribution_Channel_Id


When not NULL, specifies that the bonus should be applied only when the specified channel is used

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
|Referenced Table|[Crm_Distribution_Channels](Crm_Distribution_Channels.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Condition_Distribution_Channel_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_Document_Currency_Id


Condition for the document amount. Should be not NULL if any of the amount conditions are not NULL

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|7|
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
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Condition_Document_Currency_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_From_Date


Starting date of the bonus. NULL means that there is no starting date restriction

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|8|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|datetime (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Condition_From_Date - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|yes|
|GreaterThanOrLessThan|None|yes|no|

### Condition_Max_Amount


If not NULL specifies the maximal amount for which the bonus is valid. NULL means that there is no maximal amount condition for the bonus

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
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(12, 2) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Condition_Max_Amount - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|yes|
|GreaterThanOrLessThan|None|yes|no|

### Condition_Max_Quantity


When not NULL, specifies condition for the bonus - maximal quantity of the condition product. If the condition product is null, this cannot be specified

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
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(12, 3) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Condition_Max_Quantity - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|yes|
|GreaterThanOrLessThan|None|yes|no|

### Condition_Min_Amount


If not NULL specifies the minimal amount for which the bonus is valid. NULL means that there is no minimal amount condition for the bonus

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
|Type|decimal(12, 2) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Condition_Min_Amount - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|yes|
|GreaterThanOrLessThan|None|yes|no|

### Condition_Min_Quantity


When not NULL, specifies condition for the bonus - minimal quantity of the condition product. If the condition product is null, this cannot be specified

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
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|decimal(12, 3) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Condition_Min_Quantity - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|yes|
|GreaterThanOrLessThan|None|yes|no|

### Condition_Price_List_Id


When not NULL, specifies that the bonus should be applied only when the sales order is based on the speicfied price list

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
|Referenced Table|[Crm_Price_Lists](Crm_Price_Lists.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Condition_Price_List_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_Product_Group_Id


When not NULL, specifies that the bonus should be applied only to products from the specified product group or its subgroups

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
|Referenced Table|[Gen_Product_Groups](Gen_Product_Groups.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Condition_Product_Group_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_Product_Id


When not NULL, specifies a conditional product, which is required to exist in the sales document in order for the bonus program to be applied. If a condition with multiple products is required, additional products can be added to Bonus Program Products. If NULL the other conditions should be evaluated against the whole order.

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
|Referenced Table|[Gen_Products](Gen_Products.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Condition_Product_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_Ship_To_Customer_Filter_XML


When not NULL, specifies that the bonus should be applied only when shipping to customer with the specified characteristics

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|yes|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2147483647|
|Order|14|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(max) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

### Condition_Ship_To_Customer_Id


When not NULL, specifies that the bonus should be applied only when shipping to the specified customer

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|13|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Crm_Customers](Crm_Customers.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Condition_Ship_To_Customer_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_Target_Group_Id


When not NULL, specifies that the bonus should be applied only to the specified target customer group

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|10|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Crm_Target_Groups](Crm_Target_Groups.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Condition_Target_Group_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_To_Date


Ending date (inclusive) of the bonus. NULL means that there is no ending date restriction

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
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
|Type|datetime (Allows NULL)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Condition_To_Date - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|yes|
|GreaterThanOrLessThan|None|yes|no|

### Document_Amount_Type_Id


The document amount type that is used as а category. When specified, triggers the recording of the applied discount amount that comes from the bonus program in the Document Distributed Amounts panel in sales orders.

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

#### Document_Amount_Type_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Enterprise_Company_Id


When set, specifies that the sales document must be of the specified enterprise company.

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
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Enterprise_Company_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Priority


Priority (1-5) of the bonus program comparative to the other bonus programs. 1 is the lowest priority

| Property | Value |
| - | - |
|Allowed Values|`0`, `1`, `2`, `3`, `4`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|2|
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
|Supports EQUALS_IN|yes|
|Type|tinyint|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Priority - Supported Filters

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


